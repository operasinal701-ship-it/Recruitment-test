<!DOCTYPE html>
<html>
<head>
  <base target="_top">

  <meta name="viewport"
        content="width=device-width,
                 initial-scale=1.0,
                 maximum-scale=1.0,
                 user-scalable=no">

  <title>Recruitment Test</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: #f5f6f8;
      color: #222;
    }

    .container {
      width: 100%;
      max-width: 760px;
      margin: 0 auto;
      padding: 20px;
    }

    .card {
      background: #fff;
      border-radius: 14px;
      padding: 24px;
      box-shadow: 0 3px 15px rgba(0,0,0,.08);
      margin-top: 20px;
    }

    h1 {
      margin: 0 0 8px;
      text-align: center;
      font-size: 26px;
    }

    h2 {
      margin-top: 0;
    }

    .subtitle {
      text-align: center;
      color: #666;
      margin-bottom: 25px;
    }

    label {
      display: block;
      font-weight: bold;
      margin: 15px 0 7px;
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

    button {
      width: 100%;
      padding: 14px;
      margin-top: 18px;
      border: 0;
      border-radius: 8px;
      background: #222;
      color: white;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
    }

    button:disabled {
      opacity: .5;
      cursor: not-allowed;
    }

    .secondary {
      background: #666;
    }

    .danger {
      background: #b00020;
    }

    .success {
      background: #176b38;
    }

    .info {
      background: #eef3ff;
      border-radius: 8px;
      padding: 14px;
      margin-top: 15px;
      line-height: 1.5;
    }

    .warning {
      background: #fff4d6;
      border-radius: 8px;
      padding: 14px;
      margin-top: 15px;
      line-height: 1.5;
    }

    .error {
      background: #ffe8e8;
      color: #a00000;
      border-radius: 8px;
      padding: 14px;
      margin-top: 15px;
      line-height: 1.5;
    }

    .hidden {
      display: none !important;
    }

    .loading {
      text-align: center;
      padding: 25px;
      color: #555;
    }

    .rules {
      background: #f7f7f7;
      border-radius: 10px;
      padding: 15px;
      line-height: 1.6;
      margin-top: 20px;
    }

    .rules ol {
      margin-bottom: 0;
    }

    .timer {
      position: sticky;
      top: 0;
      z-index: 100;
      background: #222;
      color: white;
      padding: 13px;
      border-radius: 10px;
      text-align: center;
      font-size: 20px;
      font-weight: bold;
      margin-bottom: 18px;
    }

    .timer.warningTimer {
      background: #a35b00;
    }

    .timer.dangerTimer {
      background: #b00020;
    }

    .question {
      background: #fff;
      border: 1px solid #ddd;
      border-radius: 10px;
      padding: 18px;
      margin-bottom: 18px;
    }

    .question-number {
      font-weight: bold;
      margin-bottom: 10px;
    }

    .question-text {
      font-size: 17px;
      line-height: 1.5;
      margin-bottom: 15px;
      white-space: pre-wrap;
    }

    .choice {
      display: block;
      border: 1px solid #ddd;
      border-radius: 8px;
      padding: 12px;
      margin: 8px 0;
      cursor: pointer;
      font-weight: normal;
    }

    .choice:hover {
      background: #f5f5f5;
    }

    .choice input {
      margin-right: 8px;
    }

    textarea.answer-text {
      min-height: 110px;
      resize: vertical;
    }

    .progress {
      height: 8px;
      background: #ddd;
      border-radius: 10px;
      overflow: hidden;
      margin-bottom: 18px;
    }

    .progressBar {
      height: 100%;
      width: 0%;
      background: #333;
      transition: width .2s;
    }

    .participant {
      background: #f2f2f2;
      padding: 12px;
      border-radius: 8px;
      margin-bottom: 15px;
      line-height: 1.5;
    }

    .statusText {
      text-align: center;
      font-weight: bold;
      margin-top: 15px;
    }

    @media(max-width:600px) {
      .container {
        padding: 10px;
      }

      .card {
        padding: 17px;
        margin-top: 10px;
      }

      h1 {
        font-size: 22px;
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
       HALAMAN AWAL
       ===================================================== -->

  <div id="homePage" class="card">

    <h1>Recruitment Test</h1>

    <div class="subtitle">
      Silakan isi data untuk mengikuti tes.
    </div>

    <label for="email">
      Email
    </label>

    <input
      type="email"
      id="email"
      placeholder="Masukkan email"
      autocomplete="email"
    >

    <label for="name">
      Nama Lengkap
    </label>

    <input
      type="text"
      id="name"
      placeholder="Masukkan nama lengkap"
      autocomplete="name"
    >

    <div class="rules">

      <strong>Tata Tertib Tes</strong>

      <ol>
        <li>Gunakan email yang didaftarkan.</li>
        <li>Isi nama lengkap dengan benar.</li>
        <li>Kerjakan tes secara mandiri.</li>
        <li>Waktu pengerjaan adalah 30 menit.</li>
        <li>Jawaban akan tersimpan selama tes berlangsung.</li>
        <li>Setelah waktu habis, tes akan otomatis dikirim.</li>
        <li>Setelah tes dikirim, peserta tidak dapat mengulang.</li>
      </ol>

    </div>

    <button
      id="checkButton"
      onclick="checkParticipant()">
      PERIKSA DATA
    </button>

    <div id="homeMessage"></div>

  </div>


  <!-- =====================================================
       MENUNGGU ADMIN
       ===================================================== -->

  <div id="waitingPage"
       class="card hidden">

    <h2>Menunggu Verifikasi</h2>

    <div class="warning">
      Data Anda sudah terdaftar.
      Silakan menunggu admin memberikan akses untuk memulai tes.
    </div>

    <div id="waitingInfo"
         class="participant">
    </div>

    <button
      onclick="checkStatusAgain()">
      PERIKSA STATUS LAGI
    </button>

  </div>


  <!-- =====================================================
       SUDAH DISETUJUI
       ===================================================== -->

  <div id="approvedPage"
       class="card hidden">

    <h2>Akses Disetujui</h2>

    <div class="success info">
      Akses tes Anda sudah disetujui oleh admin.
    </div>

    <div id="approvedInfo"
         class="participant">
    </div>

    <button
      id="startButton"
      onclick="startTest()">
      MULAI TES
    </button>

  </div>


  <!-- =====================================================
       UJIAN
       ===================================================== -->

  <div id="examPage"
       class="hidden">

    <div class="card">

      <div id="timer"
           class="timer">
        30:00
      </div>

      <div id="examParticipant"
           class="participant">
      </div>

      <div class="progress">
        <div
          id="progressBar"
          class="progressBar">
        </div>
      </div>

      <div id="questionsContainer">
      </div>

      <button
        id="submitButton"
        class="success"
        onclick="submitTest()">
        KIRIM JAWABAN
      </button>

      <div id="examMessage"></div>

    </div>

  </div>


  <!-- =====================================================
       SELESAI
       ===================================================== -->

  <div id="finishedPage"
       class="card hidden">

    <h2>Ujian Selesai</h2>

    <div id="finishedMessage"
         class="success info">
      Jawaban Anda telah diterima.
    </div>

  </div>

</div>


<script>

  /* =====================================================
     GLOBAL
     ===================================================== */

  let currentEmail = '';
  let currentName = '';

  let currentSessionId = '';

  let questions = [];

  let answers = {};

  let endTime = 0;

  let timerInterval = null;

  let saveTimeout = null;

  let isSubmitting = false;


  /* =====================================================
     HELPER
     ===================================================== */

  function $(id) {
    return document.getElementById(id);
  }


  function escapeHtml(value) {

    return String(value || '')
      .replace(/&/g, '&amp;')
      .replace(/</g, '&lt;')
      .replace(/>/g, '&gt;')
      .replace(/"/g, '&quot;')
      .replace(/'/g, '&#039;');

  }


  function showOnly(pageId) {

    const pages = [
      'homePage',
      'waitingPage',
      'approvedPage',
      'examPage',
      'finishedPage'
    ];

    pages.forEach(function(id) {

      $(id).classList.add('hidden');

    });

    $(pageId).classList.remove('hidden');

    window.scrollTo(0, 0);

  }


  function showError(elementId, message) {

    $(elementId).innerHTML =
      '<div class="error">' +
      escapeHtml(message) +
      '</div>';

  }


  function clearMessage(elementId) {

    $(elementId).innerHTML = '';

  }


  function normalizeEmail(email) {

    return String(email || '')
      .trim()
      .toLowerCase();

  }


  /* =====================================================
     PEMERIKSAAN DATA PESERTA
     ===================================================== */

  function checkParticipant() {

    const email =
      normalizeEmail(
        $('email').value
      );

    const name =
      String(
        $('name').value || ''
      ).trim();


    if (!email) {

      showError(
        'homeMessage',
        'Email wajib diisi.'
      );

      return;

    }


    if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) {

      showError(
        'homeMessage',
        'Format email tidak valid.'
      );

      return;

    }


    if (!name) {

      showError(
        'homeMessage',
        'Nama lengkap wajib diisi.'
      );

      return;

    }


    currentEmail = email;
    currentName = name;


    $('checkButton').disabled = true;

    $('checkButton').innerText =
      'MEMERIKSA...';

    clearMessage('homeMessage');


    google.script.run

      .withSuccessHandler(
        handleParticipantStatus
      )

      .withFailureHandler(
        function(error) {

          $('checkButton').disabled = false;

          $('checkButton').innerText =
            'PERIKSA DATA';

          showError(
            'homeMessage',
            error.message ||
            'Terjadi kesalahan saat memeriksa data.'
          );

        }
      )

      .getParticipantStatus(
        currentEmail
      );

  }


  /* =====================================================
     HASIL PEMERIKSAAN
     ===================================================== */

  function handleParticipantStatus(data) {

    $('checkButton').disabled = false;

    $('checkButton').innerText =
      'PERIKSA DATA';


    if (!data) {

      showError(
        'homeMessage',
        'Tidak ada respons dari server.'
      );

      return;

    }


    if (data.hasHistory) {

      showOnly('finishedPage');

      $('finishedMessage').innerHTML =
        'Email ini sudah memiliki riwayat tes. ' +
        'Tes tidak dapat diulang.';

      return;

    }


    /*
     * BELUM TERDAFTAR
     */

    if (
      data.registered === false
    ) {

      registerNewParticipant();

      return;

    }


    /*
     * SESSION MASIH AKTIF
     */

    if (
      data.activeSession === true
    ) {

      currentEmail =
        data.email ||
        currentEmail;

      currentName =
        data.nama ||
        currentName;

      currentSessionId =
        data.sessionId;

      endTime =
        Number(data.endTime);

      questions =
        data.questions || [];

      answers =
        data.answers || {};

      showExam();

      return;

    }


    /*
     * BELUM DISETUJUI ADMIN
     */

    if (
      data.approved !== true
    ) {

      $('waitingInfo').innerHTML =
        '<strong>Nama:</strong> ' +
        escapeHtml(
          data.nama || currentName
        ) +
        '<br>' +
        '<strong>Email:</strong> ' +
        escapeHtml(
          data.email || currentEmail
        );

      showOnly('waitingPage');

      return;

    }


    /*
     * SUDAH DISETUJUI ADMIN
     */

    currentName =
      data.nama ||
      currentName;

    currentEmail =
      data.email ||
      currentEmail;


    $('approvedInfo').innerHTML =
      '<strong>Nama:</strong> ' +
      escapeHtml(currentName) +
      '<br>' +
      '<strong>Email:</strong> ' +
      escapeHtml(currentEmail);


    showOnly('approvedPage');

  }


  /* =====================================================
     PESERTA BARU
     ===================================================== */

  function registerNewParticipant() {

    $('checkButton').disabled = true;

    $('checkButton').innerText =
      'MENDAFTARKAN...';


    google.script.run

      .withSuccessHandler(
        function(data) {

          $('checkButton').disabled = false;

          $('checkButton').innerText =
            'PERIKSA DATA';


          if (!data) {

            showError(
              'homeMessage',
              'Tidak ada respons dari server.'
            );

            return;

          }


          if (data.hasHistory) {

            showOnly('finishedPage');

            $('finishedMessage').innerHTML =
              escapeHtml(
                data.message ||
                'Tes tidak dapat diulang.'
              );

            return;

          }


          if (data.approved === true) {

            $('approvedInfo').innerHTML =
              '<strong>Nama:</strong> ' +
              escapeHtml(
                data.nama ||
                currentName
              ) +
              '<br>' +
              '<strong>Email:</strong> ' +
              escapeHtml(
                data.email ||
                currentEmail
              );

            showOnly('approvedPage');

            return;

          }


          $('waitingInfo').innerHTML =
            '<strong>Nama:</strong> ' +
            escapeHtml(
              data.nama ||
              currentName
            ) +
            '<br>' +
            '<strong>Email:</strong> ' +
            escapeHtml(
              data.email ||
              currentEmail
            );

          showOnly('waitingPage');

        }
      )

      .withFailureHandler(
        function(error) {

          $('checkButton').disabled = false;

          $('checkButton').innerText =
            'PERIKSA DATA';

          showError(
            'homeMessage',
            error.message ||
            'Gagal mendaftarkan peserta.'
          );

        }
      )

      .registerParticipant(
        currentEmail,
        currentName
      );

  }


  /* =====================================================
     CEK STATUS LAGI
     ===================================================== */

  function checkStatusAgain() {

    if (!currentEmail) {

      showOnly('homePage');

      return;

    }


    google.script.run

      .withSuccessHandler(
        handleParticipantStatus
      )

      .withFailureHandler(
        function(error) {

          alert(
            error.message ||
            'Gagal memeriksa status.'
          );

        }
      )

      .getParticipantStatus(
        currentEmail
      );

  }


  /* =====================================================
     MULAI TES
     ===================================================== */

  function startTest() {

    if (!currentEmail) {

      alert(
        'Email peserta tidak ditemukan.'
      );

      return;

    }


    $('startButton').disabled = true;

    $('startButton').innerText =
      'MEMULAI TES...';


    google.script.run

      .withSuccessHandler(
        function(data) {

          $('startButton').disabled = false;

          $('startButton').innerText =
            'MULAI TES';


          if (!data) {

            alert(
              'Tidak ada respons dari server.'
            );

            return;

          }


          if (data.waiting) {

            showOnly('waitingPage');

            return;

          }


          if (!data.success) {

            alert(
              data.message ||
              'Tes belum dapat dimulai.'
            );

            return;

          }


          currentEmail =
            data.email ||
            currentEmail;

          currentName =
            data.nama ||
            currentName;

          currentSessionId =
            data.sessionId;

          endTime =
            Number(data.endTime);

          questions =
            data.questions || [];

          answers =
            data.answers || {};


          showExam();

        }
      )

      .withFailureHandler(
        function(error) {

          $('startButton').disabled = false;

          $('startButton').innerText =
            'MULAI TES';

          alert(
            error.message ||
            'Gagal memulai tes.'
          );

        }
      )

      .startExam(
        currentEmail
      );

  }


  /* =====================================================
     TAMPILKAN SOAL
     ===================================================== */

  function showExam() {

    if (!questions || !questions.length) {

      showError(
        'examMessage',
        'Soal tidak ditemukan. Periksa sheet SOAL dan kolom AKTIF.'
      );

      showOnly('examPage');

      return;

    }


    $('examParticipant').innerHTML =
      '<strong>Nama:</strong> ' +
      escapeHtml(currentName) +
      '<br>' +
      '<strong>Email:</strong> ' +
      escapeHtml(currentEmail);


    renderQuestions();

    showOnly('examPage');

    startTimer();

    updateProgress();

  }


  /* =====================================================
     RENDER SOAL
     ===================================================== */

  function renderQuestions() {

    const container =
      $('questionsContainer');

    container.innerHTML = '';


    questions.forEach(
      function(q, index) {

        const number =
          index + 1;

        const type =
          String(
            q.type || 'TEXT'
          ).toUpperCase();

        const saved =
          answers[String(number)];


        const box =
          document.createElement('div');

        box.className =
          'question';


        let html =
          '<div class="question-number">' +
          'Soal ' +
          number +
          '</div>';


        html +=
          '<div class="question-text">' +
          escapeHtml(
            q.question
          ) +
          '</div>';


        /*
         * PILIHAN
         */

        if (
          q.choices &&
          q.choices.length
        ) {

          q.choices.forEach(
            function(choice, choiceIndex) {

              const checked =
                String(saved || '') ===
                String(choice)
                  ? 'checked'
                  : '';


              html +=
                '<label class="choice">' +
                '<input ' +
                'type="radio" ' +
                'name="question_' +
                number +
                '" ' +
                'value="' +
                escapeHtml(choice) +
                '" ' +
                checked +
                ' onchange="answerChanged(' +
                number +
                ', this.value)">' +
                escapeHtml(choice) +
                '</label>';

            }
          );

        }

        /*
         * YA / TIDAK
         */

        else if (
          type === 'YA_TIDAK' ||
          type === 'YES_NO' ||
          type === 'BOOLEAN'
        ) {

          [
            'YA',
            'TIDAK'
          ].forEach(
            function(choice) {

              const checked =
                String(saved || '') ===
                choice
                  ? 'checked'
                  : '';


              html +=
                '<label class="choice">' +
                '<input ' +
                'type="radio" ' +
                'name="question_' +
                number +
                '" ' +
                'value="' +
                choice +
                '" ' +
                checked +
                ' onchange="answerChanged(' +
                number +
                ', this.value)">' +
                choice +
                '</label>';

            }
          );

        }

        /*
         * TEXT
         */

        else {

          html +=
            '<textarea ' +
            'class="answer-text" ' +
            'id="answer_' +
            number +
            '" ' +
            'placeholder="Tulis jawaban Anda..." ' +
            'oninput="answerChanged(' +
            number +
            ', this.value)">' +
            escapeHtml(
              saved || ''
            ) +
            '</textarea>';

        }


        box.innerHTML =
          html;

        container.appendChild(
          box
        );

      }
    );

  }


  /* =====================================================
     JAWABAN BERUBAH
     ===================================================== */

  function answerChanged(
    number,
    value
  ) {

    answers[String(number)] =
      value;


    updateProgress();


    /*
     * SIMPAN OTOMATIS
     */

    if (saveTimeout) {

      clearTimeout(
        saveTimeout
      );

    }


    saveTimeout =
      setTimeout(
        saveCurrentAnswers,
        700
      );

  }


  /* =====================================================
     PROGRESS
     ===================================================== */

  function updateProgress() {

    if (!questions.length) {

      return;

    }


    let answered = 0;


    questions.forEach(
      function(q, index) {

        const value =
          answers[
            String(index + 1)
          ];


        if (
          value !== undefined &&
          value !== null &&
          String(value).trim() !== ''
        ) {

          answered++;

        }

      }
    );


    const percent =
      Math.round(
        (answered /
          questions.length) *
        100
      );


    $('progressBar').style.width =
      percent + '%';

  }


  /* =====================================================
     SIMPAN JAWABAN
     ===================================================== */

  function saveCurrentAnswers() {

    if (
      !currentSessionId ||
      !currentEmail ||
      isSubmitting
    ) {

      return;

    }


    google.script.run

      .withFailureHandler(
        function(error) {

          /*
           * Jangan mengganggu peserta.
           * Jika gagal, jawaban lokal tetap berada
           * di halaman selama sesi berjalan.
           */

          console.log(
            'Gagal menyimpan:',
            error
          );

        }
      )

      .saveAnswers(
        currentSessionId,
        currentEmail,
        answers
      );

  }


  /* =====================================================
     TIMER
     ===================================================== */

  function startTimer() {

    if (timerInterval) {

      clearInterval(
        timerInterval
      );

    }


    updateTimer();


    timerInterval =
      setInterval(
        updateTimer,
        1000
      );

  }


  function updateTimer() {

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


    $('timer').innerText =
      String(minutes)
        .padStart(2, '0') +
      ':' +
      String(seconds)
        .padStart(2, '0');


    if (
      remaining <= 5 * 60 * 1000 &&
      remaining > 60 * 1000
    ) {

      $('timer')
        .classList.add(
          'warningTimer'
        );

    }


    if (
      remaining <= 60 * 1000
    ) {

      $('timer')
        .classList.remove(
          'warningTimer'
        );

      $('timer')
        .classList.add(
          'dangerTimer'
        );

    }


    if (remaining <= 0) {

      clearInterval(
        timerInterval
      );

      autoSubmitTest();

    }

  }


  /* =====================================================
     AUTO SUBMIT
     ===================================================== */

  function autoSubmitTest() {

    if (isSubmitting) {

      return;

    }


    isSubmitting = true;

    $('submitButton').disabled =
      true;


    $('submitButton').innerText =
      'WAKTU HABIS - MENGIRIM...';


    google.script.run

      .withSuccessHandler(
        finishExam
      )

      .withFailureHandler(
        function(error) {

          isSubmitting = false;

          /*
           * Jika server menolak karena sesi sudah
           * expired, tetap tampilkan selesai.
           */

          finishExam({
            success: true,
            autoSubmit: true
          });

        }
      )

      .submitExam(
        currentSessionId,
        currentEmail,
        answers
      );

  }


  /* =====================================================
     SUBMIT MANUAL
     ===================================================== */

  function submitTest() {

    if (isSubmitting) {

      return;

    }


    const confirmed =
      confirm(
        'Yakin ingin mengirim jawaban? Setelah dikirim, tes tidak dapat diulang.'
      );


    if (!confirmed) {

      return;

    }


    isSubmitting = true;

    $('submitButton').disabled =
      true;

    $('submitButton').innerText =
      'MENGIRIM...';


    /*
     * Simpan jawaban terakhir dulu
     */

    google.script.run

      .withSuccessHandler(
        function() {

          sendFinalSubmit();

        }
      )

      .withFailureHandler(
        function() {

          /*
           * Tetap kirim final karena submitExam
           * juga menyimpan answers.
           */

          sendFinalSubmit();

        }
      )

      .saveAnswers(
        currentSessionId,
        currentEmail,
        answers
      );

  }


  /* =====================================================
     KIRIM FINAL
     ===================================================== */

  function sendFinalSubmit() {

    google.script.run

      .withSuccessHandler(
        finishExam
      )

      .withFailureHandler(
        function(error) {

          isSubmitting = false;

          $('submitButton').disabled =
            false;

          $('submitButton').innerText =
            'KIRIM JAWABAN';


          showError(
            'examMessage',
            error.message ||
            'Gagal mengirim jawaban.'
          );

        }
      )

      .submitExam(
        currentSessionId,
        currentEmail,
        answers
      );

  }


  /* =====================================================
     SELESAI
     ===================================================== */

  function finishExam(data) {

    if (timerInterval) {

      clearInterval(
        timerInterval
      );

    }


    isSubmitting = false;


    showOnly(
      'finishedPage'
    );


    if (
      data &&
      data.autoSubmit
    ) {

      $('finishedMessage').innerHTML =
        'Waktu ujian telah habis. ' +
        'Jawaban Anda otomatis telah dikirim.';

    } else {

      $('finishedMessage').innerHTML =
        'Jawaban Anda telah berhasil dikirim. ' +
        'Terima kasih telah mengikuti tes.';

    }


    /*
     * Hapus data sesi dari browser
     */

    currentSessionId = '';

    questions = [];

    answers = {};

    endTime = 0;

  }


  /* =====================================================
     CEK OTOMATIS SAAT HALAMAN DIBUKA
     ===================================================== */

  window.addEventListener(
    'load',
    function() {

      /*
       * Tidak menggunakan login Google.
       * Peserta cukup memasukkan email dan nama.
       */

      $('email').focus();

    }
  );


  /* =====================================================
     ENTER = PERIKSA DATA
     ===================================================== */

  $('email').addEventListener(
    'keydown',
    function(event) {

      if (
        event.key === 'Enter'
      ) {

        event.preventDefault();

        checkParticipant();

      }

    }
  );


  $('name').addEventListener(
    'keydown',
    function(event) {

      if (
        event.key === 'Enter'
      ) {

        event.preventDefault();

        checkParticipant();

      }

    }
  );

</script>

</body>
</html>
