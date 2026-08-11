<html lang="id">
<head>
  <meta charset="UTF-8">

  <meta
    name="viewport"
    content="width=device-width, initial-scale=1.0"
  >

  <title>Recruitment Test</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 20px;
      font-family: Arial, Helvetica, sans-serif;
      background: #f4f6f8;
      color: #222;
    }

    .container {
      width: 100%;
      max-width: 850px;
      margin: 0 auto;
    }

    .card {
      background: #fff;
      border-radius: 14px;
      padding: 25px;
      margin-bottom: 20px;
      box-shadow: 0 4px 18px rgba(0,0,0,.08);
    }

    h1,
    h2 {
      margin-top: 0;
    }

    .subtitle {
      color: #666;
      margin-bottom: 25px;
    }

    label {
      display: block;
      margin-top: 15px;
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
      border-color: #333;
    }

    button {
      width: 100%;
      padding: 14px;
      margin-top: 18px;
      border: 0;
      border-radius: 8px;
      background: #222;
      color: white;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
    }

    button:hover {
      opacity: .9;
    }

    button:disabled {
      opacity: .5;
      cursor: not-allowed;
    }

    .success {
      background: #16833a;
    }

    .warning {
      padding: 15px;
      background: #fff3cd;
      border: 1px solid #ffe69c;
      border-radius: 8px;
      margin: 15px 0;
    }

    .info {
      padding: 15px;
      background: #e8f1ff;
      border: 1px solid #c8dcff;
      border-radius: 8px;
      margin: 15px 0;
    }

    .error {
      padding: 15px;
      background: #f8d7da;
      border: 1px solid #f1aeb5;
      border-radius: 8px;
      margin-top: 15px;
      color: #842029;
    }

    .participant {
      margin: 15px 0;
      padding: 12px;
      background: #f5f5f5;
      border-radius: 8px;
      line-height: 1.7;
    }

    .rules {
      margin-top: 20px;
      padding: 18px;
      background: #f7f7f7;
      border-radius: 10px;
    }

    .rules li {
      margin-bottom: 8px;
    }

    .page {
      display: none;
    }

    .page.active {
      display: block;
    }

    .timer {
      position: sticky;
      top: 10px;
      z-index: 10;
      text-align: center;
      font-size: 28px;
      font-weight: bold;
      padding: 15px;
      margin-bottom: 20px;
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 3px 12px rgba(0,0,0,.1);
    }

    .warningTimer {
      background: #fff3cd;
      color: #856404;
    }

    .dangerTimer {
      background: #f8d7da;
      color: #842029;
    }

    .progress {
      width: 100%;
      height: 10px;
      background: #ddd;
      border-radius: 10px;
      overflow: hidden;
      margin: 15px 0 25px;
    }

    .progressBar {
      width: 0%;
      height: 100%;
      background: #222;
      transition: width .2s ease;
    }

    .questionBox {
      margin-bottom: 25px;
      padding: 20px;
      border: 1px solid #ddd;
      border-radius: 10px;
      background: #fff;
    }

    .questionNumber {
      font-weight: bold;
      margin-bottom: 10px;
    }

    .questionText {
      font-size: 17px;
      line-height: 1.6;
      margin-bottom: 15px;
      white-space: pre-wrap;
    }

    .choice {
      display: block;
      margin: 10px 0;
      padding: 10px;
      border-radius: 8px;
      background: #f7f7f7;
      cursor: pointer;
    }

    .choice:hover {
      background: #eee;
    }

    .choice input {
      margin-right: 8px;
    }

    .loading {
      text-align: center;
      padding: 20px;
      color: #666;
    }

    @media (max-width: 600px) {
      body {
        padding: 10px;
      }

      .card {
        padding: 18px;
      }

      .timer {
        font-size: 24px;
      }
    }
  </style>
</head>

<body>

<div class="container">

  <!-- =====================================================
       HALAMAN HOME
       ===================================================== -->

  <div id="homePage" class="page active">

    <div class="card">

      <h1>
        Recruitment Test
      </h1>

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

        <strong>
          Tata Tertib Tes
        </strong>

        <ol>

          <li>
            Gunakan email yang didaftarkan.
          </li>

          <li>
            Isi nama lengkap dengan benar.
          </li>

          <li>
            Kerjakan tes secara mandiri.
          </li>

          <li>
            Waktu pengerjaan adalah 30 menit.
          </li>

          <li>
            Jawaban tersimpan selama tes berlangsung.
          </li>

          <li>
            Setelah waktu habis, tes otomatis dikirim.
          </li>

          <li>
            Setelah tes dikirim, peserta tidak dapat mengulang.
          </li>

        </ol>

      </div>

      <button
        id="checkButton"
        onclick="checkParticipant()"
      >
        PERIKSA DATA
      </button>

      <div id="homeMessage"></div>

    </div>

  </div>


  <!-- =====================================================
       MENUNGGU VERIFIKASI
       ===================================================== -->

  <div id="waitingPage" class="page">

    <div class="card">

      <h2>
        Menunggu Verifikasi
      </h2>

      <div class="warning">

        Data Anda sudah terdaftar.

        <br><br>

        Silakan menunggu admin memberikan akses
        untuk memulai tes.

      </div>

      <div
        id="waitingInfo"
        class="participant"
      ></div>

      <button
        onclick="checkStatusAgain()"
      >
        PERIKSA STATUS LAGI
      </button>

    </div>

  </div>


  <!-- =====================================================
       AKSES DISETUJUI
       ===================================================== -->

  <div id="approvedPage" class="page">

    <div class="card">

      <h2>
        Akses Disetujui
      </h2>

      <div class="info">

        Akses tes Anda sudah disetujui oleh admin.

      </div>

      <div
        id="approvedInfo"
        class="participant"
      ></div>

      <button
        id="startButton"
        onclick="startTest()"
      >
        MULAI TES
      </button>

    </div>

  </div>


  <!-- =====================================================
       HALAMAN UJIAN
       ===================================================== -->

  <div id="examPage" class="page">

    <div class="card">

      <div
        id="timer"
        class="timer"
      >
        30:00
      </div>

      <div
        id="examParticipant"
        class="participant"
      ></div>

      <div class="progress">

        <div
          id="progressBar"
          class="progressBar"
        ></div>

      </div>

      <div
        id="questionsContainer"
      ></div>

      <button
        id="submitButton"
        class="success"
        onclick="submitTest()"
      >
        KIRIM JAWABAN
      </button>

      <div id="examMessage"></div>

    </div>

  </div>


  <!-- =====================================================
       SELESAI
       ===================================================== -->

  <div id="finishedPage" class="page">

    <div class="card">

      <h2>
        Ujian Selesai
      </h2>

      <div
        id="finishedMessage"
        class="info"
      >
        Jawaban Anda telah diterima.
      </div>

    </div>

  </div>

</div>


<script>

/* =========================================================
   URL WEB APP APPS SCRIPT
   ========================================================= */

const WEB_APP_URL =
  'https://script.google.com/macros/s/AKfycbwF-IzqUDYnpuQXbCrAwi4f_dKGNtRO3xK2qc2akf2ylRYwiHEEnunIrDSDXElzP5gZ/exec';


/* =========================================================
   VARIABEL SISTEM
   ========================================================= */

let currentEmail = '';

let currentName = '';

let currentSessionId = '';

let questions = [];

let answers = {};

let endTime = 0;

let timerInterval = null;

let saveTimeout = null;

let isSubmitting = false;


/* =========================================================
   HELPER DOM
   ========================================================= */

function $(id) {

  return document.getElementById(id);

}


/* =========================================================
   TAMPILKAN HALAMAN
   ========================================================= */

function showOnly(pageId) {

  document
    .querySelectorAll('.page')
    .forEach(function(page) {

      page.classList.remove('active');

    });

  $(pageId)
    .classList
    .add('active');

  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  });

}


/* =========================================================
   ERROR
   ========================================================= */

function showError(
  elementId,
  message
) {

  $(elementId)
    .innerHTML =
      '<div class="error">' +
      escapeHtml(message) +
      '</div>';

}


/* =========================================================
   ESCAPE HTML
   ========================================================= */

function escapeHtml(value) {

  return String(value || '')
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/"/g, '&quot;')
    .replace(/'/g, '&#039;');

}


/* =========================================================
   PANGGIL WEB APP
   ========================================================= */

async function callWebApp(
  action,
  payload
) {

  const body = {

    action: action,

    payload: payload || {}

  };


  const response =
    await fetch(
      WEB_APP_URL,
      {

        method: 'POST',

        headers: {
          'Content-Type':
            'text/plain;charset=utf-8'
        },

        body:
          JSON.stringify(body)

      }
    );


  if (!response.ok) {

    throw new Error(
      'Server mengembalikan HTTP ' +
      response.status
    );

  }


  const text =
    await response.text();


  let data;


  try {

    data =
      JSON.parse(text);

  }

  catch (error) {

    console.error(
      'Response server:',
      text
    );

    throw new Error(
      'Response Web App bukan JSON.'
    );

  }


  if (
    data &&
    data.success === false &&
    data.message
  ) {

    throw new Error(
      data.message
    );

  }


  return data;

}


/* =========================================================
   PERIKSA DATA
   ========================================================= */

async function checkParticipant() {

  const email =
    $('email')
      .value
      .trim()
      .toLowerCase();


  const name =
    $('name')
      .value
      .trim();


  if (!email) {

    showError(
      'homeMessage',
      'Email wajib diisi.'
    );

    return;

  }


  if (!isValidEmail(email)) {

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


  const button =
    $('checkButton');


  button.disabled = true;

  button.innerText =
    'MEMERIKSA...';


  $('homeMessage')
    .innerHTML =
      '<div class="loading">' +
      'Memeriksa data...' +
      '</div>';


  try {

    /*
     * DAFTARKAN DATA TERLEBIH DAHULU
     */

    const register =
      await callWebApp(
        'registerParticipant',
        {

          email: email,

          name: name

        }
      );


    if (
      register &&
      register.hasHistory
    ) {

      showError(
        'homeMessage',
        register.message ||
        'Email ini sudah pernah mengikuti tes.'
      );

      return;

    }


    currentEmail =
      email;

    currentName =
      name;


    /*
     * CEK STATUS ADMIN
     */

    await checkStatusInternal();

  }

  catch (error) {

    console.error(error);

    showError(
      'homeMessage',
      error.message ||
      'Gagal terhubung ke server.'
    );

  }

  finally {

    button.disabled = false;

    button.innerText =
      'PERIKSA DATA';

  }

}


/* =========================================================
   CEK STATUS
   ========================================================= */

async function checkStatusAgain() {

  if (!currentEmail) {

    return;

  }


  const button =
    event &&
    event.target
      ? event.target
      : null;


  if (button) {

    button.disabled = true;

  }


  try {

    await checkStatusInternal();

  }

  catch (error) {

    showError(
      'waitingInfo',
      error.message ||
      'Gagal memeriksa status.'
    );

  }

  finally {

    if (button) {

      button.disabled = false;

    }

  }

}


/* =========================================================
   CEK STATUS INTERNAL
   ========================================================= */

async function checkStatusInternal() {

  const result =
    await callWebApp(
      'getParticipantStatus',
      {

        email:
          currentEmail

      }
    );


  if (
    result.hasHistory
  ) {

    showError(
      'homeMessage',
      result.message
    );

    showOnly(
      'homePage'
    );

    return;

  }


  /*
   * SESSION SUDAH AKTIF
   */

  if (
    result.activeSession
  ) {

    currentSessionId =
      result.sessionId;

    currentEmail =
      result.email ||
      currentEmail;

    currentName =
      result.nama ||
      currentName;

    questions =
      result.questions ||
      [];

    answers =
      result.answers ||
      {};

    endTime =
      Number(
        result.endTime
      );


    renderExamParticipant();

    renderQuestions();

    showOnly(
      'examPage'
    );

    startTimer();

    return;

  }


  /*
   * BELUM DISETUJUI
   */

  if (
    result.registered &&
    !result.approved
  ) {

    $('waitingInfo')
      .innerHTML =
        '<strong>Email:</strong> ' +
        escapeHtml(
          result.email ||
          currentEmail
        ) +
        '<br>' +

        '<strong>Nama:</strong> ' +
        escapeHtml(
          result.nama ||
          currentName
        ) +

        '<br><br>' +

        'Status: <strong>MENUNGGU VERIFIKASI</strong>';


    showOnly(
      'waitingPage'
    );

    return;

  }


  /*
   * SUDAH DISETUJUI
   */

  if (
    result.registered &&
    result.approved
  ) {

    currentEmail =
      result.email ||
      currentEmail;

    currentName =
      result.nama ||
      currentName;


    $('approvedInfo')
      .innerHTML =
        '<strong>Email:</strong> ' +
        escapeHtml(
          currentEmail
        ) +
        '<br>' +

        '<strong>Nama:</strong> ' +
        escapeHtml(
          currentName
        );


    showOnly(
      'approvedPage'
    );

    return;

  }


  /*
   * TIDAK TERDAFTAR
   */

  if (
    result.registered === false
  ) {

    /*
     * REGISTER SEHARUSNYA SUDAH MEMASUKKAN
     * PESERTA KE SHEET.
     */

    $('waitingInfo')
      .innerHTML =
        '<strong>Email:</strong> ' +
        escapeHtml(
          currentEmail
        ) +
        '<br>' +

        '<strong>Nama:</strong> ' +
        escapeHtml(
          currentName
        );


    showOnly(
      'waitingPage'
    );

    return;

  }


  throw new Error(
    result.message ||
    'Status peserta tidak dapat ditentukan.'
  );

}


/* =========================================================
   MULAI TES
   ========================================================= */

async function startTest() {

  if (!currentEmail) {

    showOnly(
      'homePage'
    );

    return;

  }


  const button =
    $('startButton');


  button.disabled = true;

  button.innerText =
    'MEMULAI...';


  try {

    const result =
      await callWebApp(
        'startExam',
        {

          email:
            currentEmail

        }
      );


    if (
      result.waiting
    ) {

      showOnly(
        'waitingPage'
      );

      return;

    }


    if (
      result.success === false
    ) {

      throw new Error(
        result.message ||
        'Tes belum dapat dimulai.'
      );

    }


    currentSessionId =
      result.sessionId;

    currentEmail =
      result.email ||
      currentEmail;

    currentName =
      result.nama ||
      currentName;

    questions =
      result.questions ||
      [];

    answers =
      result.answers ||
      {};

    endTime =
      Number(
        result.endTime
      );


    if (
      !currentSessionId
    ) {

      throw new Error(
        'Session ujian tidak diterima.'
      );

    }


    if (
      !questions.length
    ) {

      throw new Error(
        'Soal ujian tidak tersedia.'
      );

    }


    renderExamParticipant();

    renderQuestions();

    showOnly(
      'examPage'
    );

    startTimer();

  }

  catch (error) {

    console.error(error);

    showError(
      'approvedInfo',
      error.message ||
      'Gagal memulai tes.'
    );

  }

  finally {

    button.disabled = false;

    button.innerText =
      'MULAI TES';

  }

}


/* =========================================================
   INFO PESERTA
   ========================================================= */

function renderExamParticipant() {

  $('examParticipant')
    .innerHTML =

      '<strong>Nama:</strong> ' +
      escapeHtml(
        currentName
      ) +

      '<br>' +

      '<strong>Email:</strong> ' +
      escapeHtml(
        currentEmail
      );

}


/* =========================================================
   RENDER SOAL
   ========================================================= */

function renderQuestions() {

  const container =
    $('questionsContainer');


  container.innerHTML =
    '';


  questions.forEach(
    function(q, index) {

      const number =
        index + 1;


      const box =
        document.createElement(
          'div'
        );


      box.className =
        'questionBox';


      const question =
        q.question ||
        '';


      const type =
        String(
          q.type ||
          'TEXT'
        )
        .toUpperCase();


      let html =

        '<div class="questionNumber">' +

        'Soal ' +
        number +

        '</div>' +

        '<div class="questionText">' +

        escapeHtml(
          question
        ) +

        '</div>';


      /*
       * PILIHAN
       */

      if (
        q.choices &&
        Array.isArray(
          q.choices
        ) &&
        q.choices.length
      ) {

        q.choices.forEach(
          function(choice) {

            const value =
              String(
                choice
              );


            const checked =
              String(
                answers[
                  String(number)
                ] ||
                ''
              ) ===
              value
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
              escapeHtml(
                value
              ) +
              '" ' +

              checked +

              ' onchange="answerChanged(' +
              number +
              ', this.value)">' +

              escapeHtml(
                value
              ) +

              '</label>';

          }
        );

      }

      /*
       * CHECKBOX
       */

      else if (
        type === 'CHECKBOX'
      ) {

        const current =
          Array.isArray(
            answers[
              String(number)
            ]
          )
            ? answers[
                String(number)
              ]
            : [];


        (q.choices || [])
          .forEach(
            function(choice) {

              const value =
                String(
                  choice
                );


              const checked =
                current.includes(
                  value
                )
                  ? 'checked'
                  : '';


              html +=

                '<label class="choice">' +

                '<input ' +

                'type="checkbox" ' +

                'name="question_' +
                number +
                '" ' +

                'value="' +
                escapeHtml(
                  value
                ) +
                '" ' +

                checked +

                ' onchange="checkboxChanged(' +
                number +
                ', this)">' +

                escapeHtml(
                  value
                ) +

                '</label>';

            }
          );

      }

      /*
       * TEXT / ESSAY
       */

      else {

        html +=

          '<textarea ' +

          'rows="5" ' +

          'placeholder="Tulis jawaban Anda..." ' +

          'oninput="answerChanged(' +
          number +
          ', this.value)">' +

          escapeHtml(
            answers[
              String(number)
            ] ||
            ''
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


  updateProgress();

}


/* =========================================================
   JAWABAN BERUBAH
   ========================================================= */

function answerChanged(
  number,
  value
) {

  answers[
    String(number)
  ] =
    value;


  updateProgress();


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


/* =========================================================
   CHECKBOX BERUBAH
   ========================================================= */

function checkboxChanged(
  number,
  checkbox
) {

  const key =
    String(number);


  let values =
    Array.isArray(
      answers[key]
    )
      ? answers[key]
      : [];


  const value =
    checkbox.value;


  if (
    checkbox.checked
  ) {

    if (
      !values.includes(
        value
      )
    ) {

      values.push(
        value
      );

    }

  }

  else {

    values =
      values.filter(
        function(item) {

          return item !==
            value;

        }
      );

  }


  answers[key] =
    values;


  updateProgress();


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


/* =========================================================
   PROGRESS
   ========================================================= */

function updateProgress() {

  if (
    !questions.length
  ) {

    return;

  }


  let answered =
    0;


  questions.forEach(
    function(q, index) {

      const value =
        answers[
          String(
            index + 1
          )
        ];


      if (
        value !== undefined &&
        value !== null &&
        (
          Array.isArray(value)
            ? value.length > 0
            : String(value).trim() !== ''
        )
      ) {

        answered++;

      }

    }
  );


  const percent =
    Math.round(

      (
        answered /
        questions.length
      ) * 100

    );


  $('progressBar')
    .style
    .width =
      percent +
      '%';

}


/* =========================================================
   SIMPAN JAWABAN
   ========================================================= */

async function saveCurrentAnswers() {

  if (
    !currentSessionId ||
    !currentEmail ||
    isSubmitting
  ) {

    return;

  }


  try {

    await callWebApp(
      'saveAnswers',
      {

        sessionId:
          currentSessionId,

        email:
          currentEmail,

        answers:
          answers

      }
    );

  }

  catch (error) {

    console.log(
      'Gagal menyimpan:',
      error
    );

  }

}


/* =========================================================
   TIMER
   ========================================================= */

function startTimer() {

  if (
    timerInterval
  ) {

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


/* =========================================================
   UPDATE TIMER
   ========================================================= */

function updateTimer() {

  const remaining =
    Math.max(
      0,
      endTime -
      Date.now()
    );


  const totalSeconds =
    Math.floor(
      remaining /
      1000
    );


  const minutes =
    Math.floor(
      totalSeconds /
      60
    );


  const seconds =
    totalSeconds %
    60;


  $('timer')
    .innerText =

      String(minutes)
        .padStart(
          2,
          '0'
        ) +

      ':' +

      String(seconds)
        .padStart(
          2,
          '0'
        );


  if (
    remaining <=
    5 * 60 * 1000 &&

    remaining >
    60 * 1000
  ) {

    $('timer')
      .classList
      .add(
        'warningTimer'
      );

  }


  if (
    remaining <=
    60 * 1000
  ) {

    $('timer')
      .classList
      .remove(
        'warningTimer'
      );


    $('timer')
      .classList
      .add(
        'dangerTimer'
      );

  }


  if (
    remaining <= 0
  ) {

    clearInterval(
      timerInterval
    );


    autoSubmitTest();

  }

}


/* =========================================================
   AUTO SUBMIT
   ========================================================= */

async function autoSubmitTest() {

  if (
    isSubmitting
  ) {

    return;

  }


  isSubmitting =
    true;


  $('submitButton')
    .disabled =
      true;


  $('submitButton')
    .innerText =
      'WAKTU HABIS - MENGIRIM...';


  try {

    await callWebApp(
      'submitExam',
      {

        sessionId:
          currentSessionId,

        email:
          currentEmail,

        answers:
          answers

      }
    );


    finishExam({
      autoSubmit:
        true
    });

  }

  catch (error) {

    /*
     * Walaupun request gagal,
     * tampilkan selesai agar peserta
     * tidak dapat mengerjakan lagi.
     */

    console.error(
      error
    );


    finishExam({
      autoSubmit:
        true
    });

  }

}


/* =========================================================
   SUBMIT MANUAL
   ========================================================= */

async function submitTest() {

  if (
    isSubmitting
  ) {

    return;

  }


  const confirmed =
    confirm(
      'Yakin ingin mengirim jawaban? Setelah dikirim, tes tidak dapat diulang.'
    );


  if (!confirmed) {

    return;

  }


  isSubmitting =
    true;


  $('submitButton')
    .disabled =
      true;


  $('submitButton')
    .innerText =
      'MENGIRIM...';


  try {

    /*
     * SIMPAN JAWABAN TERAKHIR
     */

    await callWebApp(
      'saveAnswers',
      {

        sessionId:
          currentSessionId,

        email:
          currentEmail,

        answers:
          answers

      }
    );


    /*
     * SUBMIT
     */

    const result =
      await callWebApp(
        'submitExam',
        {

          sessionId:
            currentSessionId,

          email:
            currentEmail,

          answers:
            answers

        }
      );


    finishExam(
      result
    );

  }

  catch (error) {

    isSubmitting =
      false;


    $('submitButton')
      .disabled =
        false;


    $('submitButton')
      .innerText =
        'KIRIM JAWABAN';


    showError(
      'examMessage',
      error.message ||
      'Gagal mengirim jawaban.'
    );

  }

}


/* =========================================================
   SELESAI
   ========================================================= */

function finishExam(
  data
) {

  if (
    timerInterval
  ) {

    clearInterval(
      timerInterval
    );

  }


  isSubmitting =
    false;


  showOnly(
    'finishedPage'
  );


  if (
    data &&
    data.autoSubmit
  ) {

    $('finishedMessage')
      .innerHTML =

        'Waktu ujian telah habis. ' +
        'Jawaban Anda otomatis telah dikirim.';

  }

  else {

    $('finishedMessage')
      .innerHTML =

        'Jawaban Anda telah berhasil dikirim. ' +
        'Terima kasih telah mengikuti tes.';

  }


  currentSessionId =
    '';

  questions =
    [];

  answers =
    {};

  endTime =
    0;

}


/* =========================================================
   VALIDASI EMAIL
   ========================================================= */

function isValidEmail(
  email
) {

  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/
    .test(
      email
    );

}


/* =========================================================
   LOAD
   ========================================================= */

window.addEventListener(
  'load',
  function() {

    $('email')
      .focus();

  }
);


/* =========================================================
   ENTER EMAIL
   ========================================================= */

$('email')
  .addEventListener(
    'keydown',
    function(event) {

      if (
        event.key ===
        'Enter'
      ) {

        event.preventDefault();

        checkParticipant();

      }

    }
  );


/* =========================================================
   ENTER NAMA
   ========================================================= */

$('name')
  .addEventListener(
    'keydown',
    function(event) {

      if (
        event.key ===
        'Enter'
      ) {

        event.preventDefault();

        checkParticipant();

      }

    }
  );

</script>

</body>
</html>
```
