<!DOCTYPE html>
<html>
<head>
  <base target="_top">

  <meta name="viewport"
        content="width=device-width, initial-scale=1.0">

  <title>Recruitment Test</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: #f4f6f8;
      color: #222;
    }

    .container {
      width: 100%;
      max-width: 900px;
      margin: 0 auto;
      padding: 20px;
    }

    .card {
      background: #fff;
      border-radius: 14px;
      padding: 25px;
      box-shadow: 0 3px 15px rgba(0,0,0,0.08);
      margin-top: 20px;
    }

    .header {
      text-align: center;
      margin-bottom: 25px;
    }

    .header h1 {
      margin: 0 0 8px;
      font-size: 28px;
    }

    .header p {
      margin: 0;
      color: #666;
    }

    .form-group {
      margin-bottom: 18px;
    }

    label {
      display: block;
      margin-bottom: 7px;
      font-weight: bold;
    }

    input[type="email"],
    input[type="text"],
    textarea {
      width: 100%;
      padding: 13px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
      outline: none;
    }

    input:focus,
    textarea:focus {
      border-color: #555;
    }

    textarea {
      min-height: 100px;
      resize: vertical;
    }

    button {
      width: 100%;
      padding: 14px 18px;
      border: 0;
      border-radius: 8px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      background: #222;
      color: #fff;
    }

    button:hover {
      opacity: 0.9;
    }

    button:disabled {
      opacity: 0.5;
      cursor: not-allowed;
    }

    .secondary-button {
      background: #666;
      margin-top: 10px;
    }

    .hidden {
      display: none !important;
    }

    .message {
      padding: 15px;
      border-radius: 8px;
      margin-bottom: 18px;
      line-height: 1.5;
    }

    .message.info {
      background: #eef4ff;
      color: #174a9c;
    }

    .message.success {
      background: #eaf8ee;
      color: #176b32;
    }

    .message.error {
      background: #fff0f0;
      color: #a40000;
    }

    .message.warning {
      background: #fff8e6;
      color: #8a5a00;
    }

    .rules {
      background: #f7f7f7;
      padding: 18px;
      border-radius: 10px;
      margin-bottom: 20px;
      line-height: 1.7;
    }

    .rules h3 {
      margin-top: 0;
    }

    .rules ol {
      margin-bottom: 0;
    }

    .waiting-box {
      text-align: center;
      padding: 30px 15px;
    }

    .waiting-icon {
      font-size: 50px;
      margin-bottom: 15px;
    }

    .waiting-box h2 {
      margin-top: 0;
    }

    .status-text {
      color: #666;
      line-height: 1.6;
    }

    .exam-top {
      position: sticky;
      top: 0;
      z-index: 100;
      background: #fff;
      border-bottom: 1px solid #ddd;
      padding: 12px 15px;
      margin: -25px -25px 25px;
      border-radius: 14px 14px 0 0;
    }

    .exam-top-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 15px;
    }

    .participant-info {
      font-size: 14px;
      line-height: 1.4;
    }

    .timer {
      min-width: 125px;
      text-align: center;
      padding: 10px 14px;
      border-radius: 8px;
      background: #222;
      color: #fff;
      font-weight: bold;
      font-size: 18px;
    }

    .timer.warning {
      background: #b36b00;
    }

    .timer.danger {
      background: #a40000;
    }

    .question-card {
      border: 1px solid #ddd;
      border-radius: 10px;
      padding: 20px;
      margin-bottom: 18px;
      background: #fff;
    }

    .question-number {
      font-weight: bold;
      margin-bottom: 10px;
      color: #555;
    }

    .question-text {
      font-size: 17px;
      font-weight: bold;
      line-height: 1.5;
      margin-bottom: 18px;
      white-space: pre-wrap;
    }

    .choice {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      padding: 12px;
      border: 1px solid #ddd;
      border-radius: 8px;
      margin-bottom: 10px;
      cursor: pointer;
      transition: 0.15s;
    }

    .choice:hover {
      background: #f7f7f7;
    }

    .choice input {
      margin-top: 3px;
      flex-shrink: 0;
    }

    .choice span {
      line-height: 1.4;
    }

    .exam-actions {
      margin-top: 25px;
      padding-top: 20px;
      border-top: 1px solid #ddd;
    }

    .submit-button {
      background: #176b32;
    }

    .loading {
      text-align: center;
      padding: 25px;
      color: #666;
    }

    .spinner {
      width: 35px;
      height: 35px;
      border: 4px solid #ddd;
      border-top-color: #222;
      border-radius: 50%;
      animation: spin 0.8s linear infinite;
      margin: 0 auto 15px;
    }

    @keyframes spin {
      to {
        transform: rotate(360deg);
      }
    }

    .success-screen {
      text-align: center;
      padding: 30px 10px;
    }

    .success-icon {
      font-size: 55px;
      margin-bottom: 15px;
    }

    .success-screen h2 {
      margin-bottom: 10px;
    }

    .success-screen p {
      color: #666;
      line-height: 1.6;
    }

    @media (max-width: 600px) {

      .container {
        padding: 10px;
      }

      .card {
        padding: 18px;
        margin-top: 10px;
        border-radius: 10px;
      }

      .header h1 {
        font-size: 23px;
      }

      .exam-top {
        margin: -18px -18px 18px;
      }

      .exam-top-inner {
        flex-direction: column;
        align-items: stretch;
      }

      .timer {
        width: 100%;
      }

      .question-text {
        font-size: 16px;
      }
    }
  </style>
</head>

<body>

<div class="container">

  <!-- =====================================================
       HALAMAN PENDAFTARAN
       ===================================================== -->

  <div id="registrationCard" class="card">

    <div class="header">
      <h1>Recruitment Test</h1>
      <p>Silakan isi data peserta sebelum memulai.</p>
    </div>

    <div id="registrationMessage"></div>

    <div class="rules">

      <h3>Tata Tertib</h3>

      <ol>
        <li>Pastikan nama dan email yang digunakan sudah benar.</li>
        <li>Peserta hanya dapat mengikuti tes sesuai akses yang diberikan.</li>
        <li>Waktu pengerjaan adalah 30 menit.</li>
        <li>Jawaban dapat tersimpan selama ujian berlangsung.</li>
        <li>Jangan menutup halaman selama ujian berlangsung.</li>
        <li>Setelah ujian dikirim, peserta tidak dapat mengulang tes.</li>
      </ol>

    </div>

    <div class="form-group">

      <label for="email">
        Email
      </label>

      <input
        type="email"
        id="email"
        placeholder="Masukkan email"
        autocomplete="email"
      >

    </div>

    <div class="form-group">

      <label for="name">
        Nama Lengkap
      </label>

      <input
        type="text"
        id="name"
        placeholder="Masukkan nama lengkap"
        autocomplete="name"
      >

    </div>

    <button
      id="registerButton"
      onclick="registerParticipant()">
      MASUK
    </button>

  </div>


  <!-- =====================================================
       HALAMAN MENUNGGU ADMIN
       ===================================================== -->

  <div id="waitingCard" class="card hidden">

    <div class="waiting-box">

      <div class="waiting-icon">
        ⏳
      </div>

      <h2>Menunggu Verifikasi</h2>

      <p id="waitingMessage" class="status-text">
        Data peserta sudah diterima.
      </p>

      <p class="status-text">
        Setelah admin memberikan akses,
        halaman ini akan otomatis memeriksa kembali.
      </p>

      <button
        class="secondary-button"
        onclick="checkStatus()">
        CEK STATUS
      </button>

    </div>

  </div>


  <!-- =====================================================
       HALAMAN LOADING
       ===================================================== -->

  <div id="loadingCard" class="card hidden">

    <div class="loading">

      <div class="spinner"></div>

      <div id="loadingText">
        Memproses...
      </div>

    </div>

  </div>


  <!-- =====================================================
       HALAMAN UJIAN
       ===================================================== -->

  <div id="examCard" class="card hidden">

    <div class="exam-top">

      <div class="exam-top-inner">

        <div class="participant-info">

          <strong id="examName">
            Peserta
          </strong>

          <br>

          <span id="examEmail">
            -
          </span>

        </div>

        <div
          id="timer"
          class="timer">
          30:00
        </div>

      </div>

    </div>

    <div id="examMessage"></div>

    <div id="questionsContainer"></div>

    <div class="exam-actions">

      <button
        id="submitButton"
        class="submit-button"
        onclick="submitExamNow()">
        KIRIM JAWABAN
      </button>

    </div>

  </div>


  <!-- =====================================================
       HALAMAN SELESAI
       ===================================================== -->

  <div id="successCard" class="card hidden">

    <div class="success-screen">

      <div class="success-icon">
        ✅
      </div>

      <h2>Ujian Selesai</h2>

      <p id="successMessage">
        Jawaban Anda telah diterima.
      </p>

    </div>

  </div>

</div>


<script>

  /*
   * ========================================================
   * STATE
   * ========================================================
   */

  let currentEmail = '';
  let currentName = '';
  let currentSessionId = '';

  let examQuestions = [];
  let examAnswers = {};

  let startTime = 0;
  let endTime = 0;

  let timerInterval = null;
  let autosaveInterval = null;
  let statusInterval = null;

  let submitting = false;


  /*
   * ========================================================
   * INIT
   * ========================================================
   */

  document.addEventListener(
    'DOMContentLoaded',
    function() {

      loadSavedParticipant();

    }
  );


  /*
   * ========================================================
   * LOCAL STORAGE
   * ========================================================
   */

  function loadSavedParticipant() {

    try {

      const savedEmail =
        localStorage.getItem(
          'recruitment_email'
        );

      const savedName =
        localStorage.getItem(
          'recruitment_name'
        );

      if (savedEmail) {

        document.getElementById(
          'email'
        ).value = savedEmail;

      }

      if (savedName) {

        document.getElementById(
          'name'
        ).value = savedName;

      }

      if (savedEmail) {

        currentEmail =
          savedEmail;

        checkStatusSilently(
          savedEmail
        );

      }

    } catch (error) {

      console.log(error);

    }

  }


  function saveParticipantLocal(
    email,
    name
  ) {

    try {

      localStorage.setItem(
        'recruitment_email',
        email
      );

      localStorage.setItem(
        'recruitment_name',
        name
      );

    } catch (error) {

      console.log(error);

    }

  }


  /*
   * ========================================================
   * UI
   * ========================================================
   */

  function hideAllCards() {

    document
      .getElementById(
        'registrationCard'
      )
      .classList.add('hidden');

    document
      .getElementById(
        'waitingCard'
      )
      .classList.add('hidden');

    document
      .getElementById(
        'loadingCard'
      )
      .classList.add('hidden');

    document
      .getElementById(
        'examCard'
      )
      .classList.add('hidden');

    document
      .getElementById(
        'successCard'
      )
      .classList.add('hidden');

  }


  function showRegistration() {

    hideAllCards();

    document
      .getElementById(
        'registrationCard'
      )
      .classList.remove('hidden');

  }


  function showWaiting(
    message
  ) {

    hideAllCards();

    document
      .getElementById(
        'waitingCard'
      )
      .classList.remove('hidden');

    document
      .getElementById(
        'waitingMessage'
      )
      .textContent =
      message ||
      'Data peserta sudah diterima.';

  }


  function showLoading(
    text
  ) {

    hideAllCards();

    document
      .getElementById(
        'loadingCard'
      )
      .classList.remove('hidden');

    document
      .getElementById(
        'loadingText'
      )
      .textContent =
      text ||
      'Memproses...';

  }


  function showExam() {

    hideAllCards();

    document
      .getElementById(
        'examCard'
      )
      .classList.remove('hidden');

  }


  function showSuccess(
    message
  ) {

    hideAllCards();

    document
      .getElementById(
        'successCard'
      )
      .classList.remove('hidden');

    document
      .getElementById(
        'successMessage'
      )
      .textContent =
      message ||
      'Jawaban Anda telah diterima.';

  }


  function showMessage(
    elementId,
    message,
    type
  ) {

    const element =
      document.getElementById(
        elementId
      );

    if (!element) {
      return;
    }

    element.innerHTML =
      '';

    if (!message) {
      return;
    }

    const div =
      document.createElement(
        'div'
      );

    div.className =
      'message ' +
      (
        type ||
        'info'
      );

    div.textContent =
      message;

    element.appendChild(
      div
    );

  }


  /*
   * ========================================================
   * REGISTER
   * ========================================================
   */

  function registerParticipant() {

    const email =
      document
        .getElementById(
          'email'
        )
        .value
        .trim()
        .toLowerCase();

    const name =
      document
        .getElementById(
          'name'
        )
        .value
        .trim();

    if (!email) {

      showMessage(
        'registrationMessage',
        'Email wajib diisi.',
        'error'
      );

      return;

    }

    if (!isValidEmail(email)) {

      showMessage(
        'registrationMessage',
        'Format email tidak valid.',
        'error'
      );

      return;

    }

    if (!name) {

      showMessage(
        'registrationMessage',
        'Nama wajib diisi.',
        'error'
      );

      return;

    }

    currentEmail =
      email;

    currentName =
      name;

    saveParticipantLocal(
      email,
      name
    );

    const button =
      document.getElementById(
        'registerButton'
      );

    button.disabled =
      true;

    button.textContent =
      'MEMPROSES...';

    showMessage(
      'registrationMessage',
      'Memeriksa data peserta...',
      'info'
    );


    google.script.run

      .withSuccessHandler(
        function(result) {

          button.disabled =
            false;

          button.textContent =
            'MASUK';

          handleRegistrationResult(
            result
          );

        }
      )

      .withFailureHandler(
        function(error) {

          button.disabled =
            false;

          button.textContent =
            'MASUK';

          showMessage(
            'registrationMessage',
            getErrorMessage(
              error
            ),
            'error'
          );

        }
      )

      .registerParticipant(
        email,
        name
      );

  }


  /*
   * ========================================================
   * HANDLE REGISTER RESULT
   * ========================================================
   */

  function handleRegistrationResult(
    result
  ) {

    if (!result) {

      showMessage(
        'registrationMessage',
        'Tidak ada respons dari server.',
        'error'
      );

      return;

    }

    if (
      result.hasHistory
    ) {

      showMessage(
        'registrationMessage',
        result.message ||
        'Email ini sudah pernah mengikuti tes.',
        'warning'
      );

      return;

    }

    if (
      result.waiting
    ) {

      currentEmail =
        result.email ||
        currentEmail;

      currentName =
        result.nama ||
        currentName;

      showWaiting(
        result.message ||
        'Menunggu verifikasi admin.'
      );

      startStatusPolling();

      return;

    }

    if (
      result.approved
    ) {

      checkStatus();

      return;

    }

    showMessage(
      'registrationMessage',
      result.message ||
      'Data berhasil diproses.',
      'info'
    );

  }


  /*
   * ========================================================
   * CHECK STATUS
   * ========================================================
   */

  function checkStatus() {

    let email =
      currentEmail;

    if (!email) {

      email =
        document
          .getElementById(
            'email'
          )
          .value
          .trim()
          .toLowerCase();

    }

    if (!email) {

      showRegistration();

      showMessage(
        'registrationMessage',
        'Masukkan email terlebih dahulu.',
        'error'
      );

      return;

    }

    currentEmail =
      email;

    showLoading(
      'Memeriksa status akses...'
    );

    checkStatusWithEmail(
      email
    );

  }


  function checkStatusSilently(
    email
  ) {

    if (!email) {
      return;
    }

    checkStatusWithEmail(
      email,
      true
    );

  }


  function checkStatusWithEmail(
    email,
    silent
  ) {

    google.script.run

      .withSuccessHandler(
        function(result) {

          handleStatusResult(
            result,
            !!silent
          );

        }
      )

      .withFailureHandler(
        function(error) {

          if (!silent) {

            showRegistration();

            showMessage(
              'registrationMessage',
              getErrorMessage(
                error
              ),
              'error'
            );

          }

        }
      )

      .getParticipantStatus(
        email
      );

  }


  /*
   * ========================================================
   * HANDLE STATUS
   * ========================================================
   */

  function handleStatusResult(
    result,
    silent
  ) {

    if (!result) {

      if (!silent) {

        showRegistration();

        showMessage(
          'registrationMessage',
          'Server tidak memberikan respons.',
          'error'
        );

      }

      return;

    }

    if (
      result.hasHistory
    ) {

      stopStatusPolling();

      showRegistration();

      showMessage(
        'registrationMessage',
        result.message ||
        'Email ini sudah memiliki riwayat tes.',
        'warning'
      );

      return;

    }

    if (
      result.activeSession
    ) {

      stopStatusPolling();

      currentEmail =
        result.email ||
        currentEmail;

      currentName =
        result.nama ||
        currentName;

      startExamFromSession(
        result
      );

      return;

    }

    if (
      result.approved
    ) {

      stopStatusPolling();

      currentEmail =
        result.email ||
        currentEmail;

      currentName =
        result.nama ||
        currentName;

      showLoading(
        'Akses disetujui. Menyiapkan ujian...'
      );

      startExam();

      return;

    }

    if (
      result.registered &&
      !result.approved
    ) {

      showWaiting(
        result.message ||
        'Menunggu verifikasi admin.'
      );

      startStatusPolling();

      return;

    }

    if (
      result.registered === false
    ) {

      stopStatusPolling();

      showRegistration();

      showMessage(
        'registrationMessage',
        result.message ||
        'Email belum terdaftar.',
        'warning'
      );

      return;

    }

    if (!silent) {

      showRegistration();

    }

  }


  /*
   * ========================================================
   * POLLING STATUS ADMIN
   * ========================================================
   */

  function startStatusPolling() {

    stopStatusPolling();

    statusInterval =
      setInterval(
        function() {

          if (!currentEmail) {
            return;
          }

          checkStatusWithEmail(
            currentEmail,
            true
          );

        },
        5000
      );

  }


  function stopStatusPolling() {

    if (
      statusInterval
    ) {

      clearInterval(
        statusInterval
      );

      statusInterval =
        null;

    }

  }


  /*
   * ========================================================
   * START EXAM
   * ========================================================
   */

  function startExam() {

    if (!currentEmail) {

      showRegistration();

      return;

    }

    google.script.run

      .withSuccessHandler(
        function(result) {

          if (!result) {

            showRegistration();

            showMessage(
              'registrationMessage',
              'Tidak ada respons dari server.',
              'error'
            );

            return;

          }

          if (
            result.waiting
          ) {

            showWaiting(
              result.message
            );

            startStatusPolling();

            return;

          }

          if (
            result.success
          ) {

            startExamFromSession(
              result
            );

            return;

          }

          showRegistration();

          showMessage(
            'registrationMessage',
            result.message ||
            'Ujian belum dapat dimulai.',
            'warning'
          );

        }
      )

      .withFailureHandler(
        function(error) {

          showRegistration();

          showMessage(
            'registrationMessage',
            getErrorMessage(
              error
            ),
            'error'
          );

        }
      )

      .startExam(
        currentEmail
      );

  }


  /*
   * ========================================================
   * START / RESUME SESSION
   * ========================================================
   */

  function startExamFromSession(
    result
  ) {

    if (
      !result ||
      !result.sessionId
    ) {

      showRegistration();

      showMessage(
        'registrationMessage',
        'Session ujian tidak ditemukan.',
        'error'
      );

      return;

    }

    currentSessionId =
      result.sessionId;

    currentEmail =
      result.email ||
      currentEmail;

    currentName =
      result.nama ||
      currentName;

    startTime =
      Number(
        result.startTime || 0
      );

    endTime =
      Number(
        result.endTime || 0
      );

    examQuestions =
      Array.isArray(
        result.questions
      )
        ? result.questions
        : [];

    examAnswers =
      result.answers ||
      {};

    if (
      !examQuestions.length
    ) {

      showRegistration();

      showMessage(
        'registrationMessage',
        'Soal tidak ditemukan. Pastikan sheet SOAL memiliki soal aktif.',
        'error'
      );

      return;

    }

    document
      .getElementById(
        'examName'
      )
      .textContent =
      currentName ||
      'Peserta';

    document
      .getElementById(
        'examEmail'
      )
      .textContent =
      currentEmail ||
      '';

    renderQuestions();

    showExam();

    startTimer();

    startAutosave();

  }


  /*
   * ========================================================
   * RENDER SOAL
   * ========================================================
   */

  function renderQuestions() {

    const container =
      document.getElementById(
        'questionsContainer'
      );

    container.innerHTML =
      '';

    examQuestions.forEach(
      function(q, index) {

        const card =
          document.createElement(
            'div'
          );

        card.className =
          'question-card';

        const number =
          document.createElement(
            'div'
          );

        number.className =
          'question-number';

        number.textContent =
          'Soal ' +
          (
            q.no ||
            index + 1
          );

        card.appendChild(
          number
        );


        const question =
          document.createElement(
            'div'
          );

        question.className =
          'question-text';

        question.textContent =
          q.question ||
          '';

        card.appendChild(
          question
        );


        const type =
          String(
            q.type ||
            'TEXT'
          )
          .trim()
          .toUpperCase();

        const choices =
          Array.isArray(
            q.choices
          )
            ? q.choices
            : [];


        if (
          choices.length &&
          (
            type === 'RADIO' ||
            type === 'SINGLE' ||
            type === 'PILIHAN' ||
            type === 'CHOICE' ||
            type === 'MULTIPLE_CHOICE'
          )
        ) {

          renderRadioChoices(
            card,
            q,
            index,
            choices
          );

        }

        else if (
          choices.length &&
          (
            type === 'CHECKBOX' ||
            type === 'MULTI' ||
            type === 'MULTIPLE'
          )
        ) {

          renderCheckboxChoices(
            card,
            q,
            index,
            choices
          );

        }

        else {

          renderTextAnswer(
            card,
            q,
            index
          );

        }


        container.appendChild(
          card
        );

      }
    );

  }


  /*
   * ========================================================
   * RADIO
   * ========================================================
   */

  function renderRadioChoices(
    card,
    question,
    index,
    choices
  ) {

    const saved =
      examAnswers[
        String(
          index + 1
        )
      ];

    choices.forEach(
      function(choice, choiceIndex) {

        const label =
          document.createElement(
            'label'
          );

        label.className =
          'choice';

        const input =
          document.createElement(
            'input'
          );

        input.type =
          'radio';

        input.name =
          'question_' +
          index;

        input.value =
          choice;

        if (
          saved === choice
        ) {

          input.checked =
            true;

        }

        input.addEventListener(
          'change',
          function() {

            examAnswers[
              String(
                index + 1
              )
            ] =
              input.value;

          }
        );

        const span =
          document.createElement(
            'span'
          );

        span.textContent =
          choice;

        label.appendChild(
          input
        );

        label.appendChild(
          span
        );

        card.appendChild(
          label
        );

      }
    );

  }


  /*
   * ========================================================
   * CHECKBOX
   * ========================================================
   */

  function renderCheckboxChoices(
    card,
    question,
    index,
    choices
  ) {

    let saved =
      examAnswers[
        String(
          index + 1
        )
      ];

    if (
      !Array.isArray(saved)
    ) {

      saved =
        [];

    }

    choices.forEach(
      function(choice) {

        const label =
          document.createElement(
            'label'
          );

        label.className =
          'choice';

        const input =
          document.createElement(
            'input'
          );

        input.type =
          'checkbox';

        input.value =
          choice;

        input.checked =
          saved.includes(
            choice
          );

        input.addEventListener(
          'change',
          function() {

            const selected =
              Array.from(
                card.querySelectorAll(
                  'input[type="checkbox"]'
                )
              )
              .filter(
                function(item) {
                  return item.checked;
                }
              )
              .map(
                function(item) {
                  return item.value;
                }
              );

            examAnswers[
              String(
                index + 1
              )
            ] =
              selected;

          }
        );

        const span =
          document.createElement(
            'span'
          );

        span.textContent =
          choice;

        label.appendChild(
          input
        );

        label.appendChild(
          span
        );

        card.appendChild(
          label
        );

      }
    );

  }


  /*
   * ========================================================
   * TEXT ANSWER
   * ========================================================
   */

  function renderTextAnswer(
    card,
    question,
    index
  ) {

    const textarea =
      document.createElement(
        'textarea'
      );

    textarea.placeholder =
      'Ketik jawaban Anda di sini...';

    const saved =
      examAnswers[
        String(
          index + 1
        )
      ];

    textarea.value =
      saved ||
      '';

    textarea.addEventListener(
      'input',
      function() {

        examAnswers[
          String(
            index + 1
          )
        ] =
          textarea.value;

      }
    );

    card.appendChild(
      textarea
    );

  }


  /*
   * ========================================================
   * TIMER
   * ========================================================
   */

  function startTimer() {

    stopTimer();

    updateTimer();

    timerInterval =
      setInterval(
        updateTimer,
        1000
      );

  }


  function stopTimer() {

    if (
      timerInterval
    ) {

      clearInterval(
        timerInterval
      );

      timerInterval =
        null;

    }

  }


  function updateTimer() {

    if (!endTime) {
      return;
    }

    const remaining =
      Math.max(
        0,
        endTime -
        Date.now()
      );

    const totalSeconds =
      Math.floor(
        remaining / 1000
      );

    const minutes =
      Math.floor(
        totalSeconds / 60
      );

    const seconds =
      totalSeconds % 60;

    const timer =
      document.getElementById(
        'timer'
      );

    timer.textContent =
      String(
        minutes
      ).padStart(
        2,
        '0'
      ) +
      ':' +
      String(
        seconds
      ).padStart(
        2,
        '0'
      );

    timer.classList.remove(
      'warning',
      'danger'
    );

    if (
      totalSeconds <= 300
    ) {

      timer.classList.add(
        'danger'
      );

    }
    else if (
      totalSeconds <= 600
    ) {

      timer.classList.add(
        'warning'
      );

    }

    if (
      remaining <= 0
    ) {

      stopTimer();

      stopAutosave();

      autoSubmitExam();

    }

  }


  /*
   * ========================================================
   * AUTO SAVE
   * ========================================================
   */

  function startAutosave() {

    stopAutosave();

    autosaveInterval =
      setInterval(
        function() {

          if (
            !currentSessionId ||
            !currentEmail ||
            submitting
          ) {

            return;

          }

          saveAnswersToServer(
            false
          );

        },
        10000
      );

  }


  function stopAutosave() {

    if (
      autosaveInterval
    ) {

      clearInterval(
        autosaveInterval
      );

      autosaveInterval =
        null;

    }

  }


  function saveAnswersToServer(
    showResult
  ) {

    if (
      !currentSessionId ||
      !currentEmail
    ) {

      return;

    }

    google.script.run

      .withSuccessHandler(
        function(result) {

          if (
            showResult &&
            result
          ) {

            showMessage(
              'examMessage',
              'Jawaban berhasil disimpan.',
              'success'
            );

          }

        }
      )

      .withFailureHandler(
        function(error) {

          if (
            showResult
          ) {

            showMessage(
              'examMessage',
              getErrorMessage(
                error
              ),
              'error'
            );

          }

        }
      )

      .saveAnswers(
        currentSessionId,
        currentEmail,
        examAnswers
      );

  }


  /*
   * ========================================================
   * SUBMIT MANUAL
   * ========================================================
   */

  function submitExamNow() {

    if (submitting) {
      return;
    }

    const confirmed =
      window.confirm(
        'Apakah Anda yakin ingin mengirim jawaban? Setelah dikirim, ujian tidak dapat diulang.'
      );

    if (!confirmed) {
      return;
    }

    submitExamToServer(
      false
    );

  }


  /*
   * ========================================================
   * AUTO SUBMIT
   * ========================================================
   */

  function autoSubmitExam() {

    if (submitting) {
      return;
    }

    submitExamToServer(
      true
    );

  }


  /*
   * ========================================================
   * SUBMIT KE SERVER
   * ========================================================
   */

  function submitExamToServer(
    automatic
  ) {

    if (
      !currentSessionId ||
      !currentEmail
    ) {

      return;

    }

    submitting =
      true;

    stopTimer();

    stopAutosave();

    const button =
      document.getElementById(
        'submitButton'
      );

    if (button) {

      button.disabled =
        true;

      button.textContent =
        automatic
          ? 'WAKTU HABIS...'
          : 'MENGIRIM...';

    }

    showMessage(
      'examMessage',
      automatic
        ? 'Waktu habis. Jawaban sedang dikirim otomatis...'
        : 'Jawaban sedang dikirim...',
      automatic
        ? 'warning'
        : 'info'
    );


    google.script.run

      .withSuccessHandler(
        function(result) {

          submitting =
            false;

          if (
            result &&
            result.success
          ) {

            showSuccess(
              result.message ||
              (
                automatic
                  ? 'Waktu habis. Jawaban otomatis telah dikirim.'
                  : 'Jawaban Anda telah diterima.'
              )
            );

            return;

          }

          if (button) {

            button.disabled =
              false;

            button.textContent =
              'KIRIM JAWABAN';

          }

          showMessage(
            'examMessage',
            'Jawaban belum berhasil dikirim.',
            'error'
          );

        }
      )

      .withFailureHandler(
        function(error) {

          submitting =
            false;

          if (button) {

            button.disabled =
              false;

            button.textContent =
              'KIRIM JAWABAN';

          }

          showMessage(
            'examMessage',
            getErrorMessage(
              error
            ),
            'error'
          );

        }
      )

      .submitExam(
        currentSessionId,
        currentEmail,
        examAnswers
      );

  }


  /*
   * ========================================================
   * VALIDASI EMAIL
   * ========================================================
   */

  function isValidEmail(
    email
  ) {

    return /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      .test(email);

  }


  /*
   * ========================================================
   * ERROR MESSAGE
   * ========================================================
   */

  function getErrorMessage(
    error
  ) {

    if (!error) {

      return 'Terjadi kesalahan.';

    }

    if (
      typeof error === 'string'
    ) {

      return error;

    }

    if (
      error.message
    ) {

      return error.message;

    }

    return String(
      error
    );

  }


  /*
   * ========================================================
   * CEGAH REFRESH / MENUTUP SAAT UJIAN
   * ========================================================
   */

  window.addEventListener(
    'beforeunload',
    function(event) {

      if (
        currentSessionId &&
        !submitting &&
        !document
          .getElementById(
            'examCard'
          )
          .classList
          .contains('hidden')
      ) {

        saveAnswersToServer(
          false
        );

        event.preventDefault();

        event.returnValue =
          '';

      }

    }
  );

</script>

</body>
</html>
