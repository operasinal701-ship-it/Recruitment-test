<!DOCTYPE html>
<html lang="id">

<head>

<meta charset="UTF-8">

<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0">

<title>Recruitment Test</title>

<style>

* {
  box-sizing: border-box;
}

body {

  margin: 0;

  padding: 20px;

  background:
    #f4f7fb;

  font-family:
    Arial,
    Helvetica,
    sans-serif;

  color:
    #1f2937;
}

.container {

  width: 100%;

  max-width: 800px;

  margin:
    0 auto;

}

.card {

  background:
    white;

  border-radius:
    16px;

  padding:
    25px;

  box-shadow:
    0 5px 25px
    rgba(0,0,0,.08);

  margin-bottom:
    20px;

}

h1,
h2 {

  margin-top:
    0;

}

.subtitle {

  color:
    #6b7280;

  margin-bottom:
    25px;

}

label {

  display:
    block;

  font-weight:
    bold;

  margin-top:
    15px;

  margin-bottom:
    7px;

}

input,
textarea,
select {

  width:
    100%;

  padding:
    13px;

  border:
    1px solid #d1d5db;

  border-radius:
    9px;

  font-size:
    16px;

}

textarea {

  min-height:
    110px;

  resize:
    vertical;

}

button {

  width:
    100%;

  padding:
    14px;

  margin-top:
    18px;

  border:
    none;

  border-radius:
    9px;

  background:
    #2563eb;

  color:
    white;

  font-size:
    15px;

  font-weight:
    bold;

  cursor:
    pointer;

}

button:hover {

  opacity:
    .92;

}

button:disabled {

  opacity:
    .55;

  cursor:
    not-allowed;

}

.success {

  background:
    #16a34a;

}

.warning {

  background:
    #fff7ed;

  border:
    1px solid #fed7aa;

  color:
    #9a3412;

  padding:
    15px;

  border-radius:
    9px;

}

.info {

  background:
    #eff6ff;

  border:
    1px solid #bfdbfe;

  color:
    #1d4ed8;

  padding:
    15px;

  border-radius:
    9px;

}

.error {

  background:
    #fef2f2;

  border:
    1px solid #fecaca;

  color:
    #b91c1c;

  padding:
    15px;

  border-radius:
    9px;

}

.rules {

  margin-top:
    20px;

  padding:
    18px;

  background:
    #f9fafb;

  border-radius:
    10px;

}

.rules li {

  margin-bottom:
    8px;

}

.participant {

  margin-top:
    15px;

  padding:
    14px;

  background:
    #f9fafb;

  border-radius:
    9px;

  line-height:
    1.7;

}

.timer {

  text-align:
    center;

  font-size:
    32px;

  font-weight:
    bold;

  padding:
    12px;

  margin-bottom:
    15px;

  border-radius:
    10px;

  background:
    #111827;

  color:
    white;

}

.warningTimer {

  background:
    #d97706;

}

.dangerTimer {

  background:
    #dc2626;

}

.progress {

  width:
    100%;

  height:
    10px;

  background:
    #e5e7eb;

  border-radius:
    20px;

  overflow:
    hidden;

  margin-bottom:
    25px;

}

.progressBar {

  height:
    100%;

  width:
    0%;

  background:
    #2563eb;

  transition:
    width .2s;

}

.question {

  border:
    1px solid #e5e7eb;

  border-radius:
    12px;

  padding:
    18px;

  margin-bottom:
    18px;

}

.questionTitle {

  font-weight:
    bold;

  margin-bottom:
    15px;

  line-height:
    1.6;

}

.option {

  display:
    block;

  padding:
    10px;

  margin:
    7px 0;

  background:
    #f9fafb;

  border-radius:
    8px;

}

.option input {

  width:
    auto;

  margin-right:
    8px;

}

.hidden {

  display:
    none !important;

}

.loading {

  text-align:
    center;

  padding:
    25px;

  color:
    #6b7280;

}

</style>

</head>


<body>


<div class="container">


<!-- ======================================================
     HOME
     ====================================================== -->

<div
  id="homePage"
  class="card">

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
    autocomplete="email">


  <label for="name">
    Nama Lengkap
  </label>

  <input
    type="text"
    id="name"
    placeholder="Masukkan nama lengkap"
    autocomplete="name">


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
    onclick="checkParticipant()">

    PERIKSA DATA

  </button>


  <div id="homeMessage"></div>

</div>


<!-- ======================================================
     WAITING
     ====================================================== -->

<div
  id="waitingPage"
  class="card hidden">

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
    class="participant">
  </div>


  <button
    onclick="checkStatusAgain()">

    PERIKSA STATUS LAGI

  </button>

</div>


<!-- ======================================================
     APPROVED
     ====================================================== -->

<div
  id="approvedPage"
  class="card hidden">

  <h2>
    Akses Disetujui
  </h2>


  <div class="info">

    Akses tes Anda sudah disetujui oleh admin.

  </div>


  <div
    id="approvedInfo"
    class="participant">
  </div>


  <button
    id="startButton"
    onclick="startTest()">

    MULAI TES

  </button>

</div>


<!-- ======================================================
     EXAM
     ====================================================== -->

<div
  id="examPage"
  class="card hidden">


  <div
    id="timer"
    class="timer">

    30:00

  </div>


  <div
    id="examParticipant"
    class="participant">
  </div>


  <div class="progress">

    <div
      id="progressBar"
      class="progressBar">
    </div>

  </div>


  <div
    id="questionsContainer">
  </div>


  <button
    id="submitButton"
    class="success"
    onclick="submitTest()">

    KIRIM JAWABAN

  </button>


  <div id="examMessage"></div>

</div>


<!-- ======================================================
     FINISHED
     ====================================================== -->

<div
  id="finishedPage"
  class="card hidden">

  <h2>
    Ujian Selesai
  </h2>


  <div
    id="finishedMessage"
    class="info">

    Jawaban Anda telah diterima.

  </div>

</div>


</div>


<script>


/* ==========================================================
 * URL WEB APP
 * ==========================================================
 */

const WEB_APP_URL =
  'https://script.google.com/macros/s/AKfycbwF-IzqUDYnpuQXbCrAwi4f_dKGNtRO3xK2qc2akf2ylRYwiHEEnunIrDSDXElzP5gZ/exec';


/* ==========================================================
 * STATE
 * ==========================================================
 */

let currentEmail = '';

let currentName = '';

let currentSessionId = '';

let questions = [];

let answers = {};

let endTime = 0;

let timerInterval = null;

let saveTimeout = null;

let isSubmitting = false;


/* ==========================================================
 * HELPER DOM
 * ==========================================================
 */

function $(id) {

  return document.getElementById(
    id
  );

}


/* ==========================================================
 * PAGE
 * ==========================================================
 */

function showOnly(
  pageId
) {

  const pages = [

    'homePage',

    'waitingPage',

    'approvedPage',

    'examPage',

    'finishedPage'

  ];


  pages.forEach(
    function(id) {

      $(id)
        .classList
        .add(
          'hidden'
        );

    }
  );


  $(pageId)
    .classList
    .remove(
      'hidden'
    );

}


/* ==========================================================
 * ERROR
 * ==========================================================
 */

function showError(
  elementId,
  message
) {

  $(elementId)
    .innerHTML =
      '<div class="error">' +
      escapeHtml(
        message
      ) +
      '</div>';

}


/* ==========================================================
 * HTML ESCAPE
 * ==========================================================
 */

function escapeHtml(
  value
) {

  return String(
    value == null
      ? ''
      : value
  )
    .replace(
      /&/g,
      '&amp;'
    )
    .replace(
      /</g,
      '&lt;'
    )
    .replace(
      />/g,
      '&gt;'
    )
    .replace(
      /"/g,
      '&quot;'
    )
    .replace(
      /'/g,
      '&#039;'
    );

}


/* ==========================================================
 * JSONP API
 *
 * TIDAK MENGGUNAKAN FETCH.
 *
 * Ini penting karena GitHub Pages dan Apps Script
 * berbeda domain.
 * ==========================================================
 */

function api(
  action,
  params = {}
) {

  return new Promise(
    function(resolve, reject) {

      const callbackName =
        '__apiCallback_' +
        Date.now() +
        '_' +
        Math.floor(
          Math.random() * 100000
        );


      const script =
        document.createElement(
          'script'
        );


      let finished =
        false;


      const timeout =
        setTimeout(
          function() {

            if (finished) {
              return;
            }

            finished = true;

            cleanup();

            reject(
              new Error(
                'Gagal terhubung ke Web App. Periksa deployment Apps Script.'
              )
            );

          },
          20000
        );


      function cleanup() {

        clearTimeout(
          timeout
        );

        try {

          delete window[
            callbackName
          ];

        } catch (e) {

          window[
            callbackName
          ] = undefined;

        }


        if (
          script.parentNode
        ) {

          script.parentNode
            .removeChild(
              script
            );

        }

      }


      window[
        callbackName
      ] =
        function(data) {

          if (finished) {
            return;
          }


          finished = true;

          cleanup();

          resolve(
            data
          );

        };


      const query =
        new URLSearchParams();


      query.set(
        'action',
        action
      );


      query.set(
        'callback',
        callbackName
      );


      Object.keys(
        params
      )
      .forEach(
        function(key) {

          const value =
            params[key];


          if (
            value !== undefined &&
            value !== null
          ) {

            query.set(
              key,
              String(value)
            );

          }

        }
      );


      script.src =
        WEB_APP_URL +
        '?' +
        query.toString();


      script.onerror =
        function() {

          if (finished) {
            return;
          }


          finished = true;

          cleanup();


          reject(
            new Error(
              'Gagal terhubung ke Web App. Pastikan deployment Apps Script sudah aktif dan URL benar.'
            )
          );

        };


      document.body.appendChild(
        script
      );

    }
  );

}


/* ==========================================================
 * CEK KONEKSI
 * ==========================================================
 */

async function testConnection() {

  try {

    const result =
      await api(
        'ping'
      );


    if (
      !result ||
      !result.success
    ) {

      throw new Error(
        'Web App tidak merespons.'
      );

    }


    return true;


  } catch (error) {

    console.error(
      error
    );

    return false;

  }

}


/* ==========================================================
 * PERIKSA PESERTA
 * ==========================================================
 */

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


  $('homeMessage')
    .innerHTML =
      '';


  if (!email) {

    showError(
      'homeMessage',
      'Email wajib diisi.'
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


  button.disabled =
    true;

  button.innerText =
    'MEMERIKSA...';


  try {

    /*
     * CEK STATUS DULU
     */

    let result =
      await api(
        'checkParticipant',
        {
          email: email
        }
      );


    /*
     * BELUM TERDAFTAR
     * OTOMATIS DAFTARKAN
     */

    if (
      result &&
      result.registered === false &&
      !result.hasHistory
    ) {

      result =
        await api(
          'registerParticipant',
          {
            email: email,
            name: name
          }
        );

    }


    handleParticipantResult(
      result
    );


  } catch (error) {

    console.error(
      error
    );


    showError(
      'homeMessage',
      error.message ||
      'Gagal terhubung ke Web App.'
    );

  } finally {

    button.disabled =
      false;

    button.innerText =
      'PERIKSA DATA';

  }

}


/* ==========================================================
 * HASIL PESERTA
 * ==========================================================
 */

function handleParticipantResult(
  result
) {

  if (!result) {

    showError(
      'homeMessage',
      'Tidak ada respons dari Web App.'
    );

    return;

  }


  if (
    result.hasHistory
  ) {

    showError(
      'homeMessage',
      result.message ||
      'Email sudah pernah mengikuti tes.'
    );

    return;

  }


  currentEmail =
    result.email ||
    currentEmail;


  currentName =
    result.nama ||
    currentName ||
    $('name').value.trim();


  /*
   * SESSION AKTIF
   */

  if (
    result.activeSession
  ) {

    openExam(
      result
    );

    return;

  }


  /*
   * WAITING
   */

  if (
    result.registered &&
    !result.approved
  ) {

    $('waitingInfo')
      .innerHTML =
        participantInfoHtml(
          result
        );


    showOnly(
      'waitingPage'
    );

    return;

  }


  /*
   * APPROVED
   */

  if (
    result.approved
  ) {

    $('approvedInfo')
      .innerHTML =
        participantInfoHtml(
          result
        );


    showOnly(
      'approvedPage'
    );

    return;

  }


  showError(
    'homeMessage',
    result.message ||
    'Data tidak dapat diproses.'
  );

}


/* ==========================================================
 * INFO PESERTA
 * ==========================================================
 */

function participantInfoHtml(
  data
) {

  return (

    '<strong>Nama:</strong> ' +
    escapeHtml(
      data.nama ||
      currentName ||
      ''
    ) +

    '<br>' +

    '<strong>Email:</strong> ' +
    escapeHtml(
      data.email ||
      currentEmail ||
      ''
    ) +

    (
      data.code
        ? (
          '<br>' +
          '<strong>Kode:</strong> ' +
          escapeHtml(
            data.code
          )
        )
        : ''
    )

  );

}


/* ==========================================================
 * CEK STATUS LAGI
 * ==========================================================
 */

async function checkStatusAgain() {

  if (!currentEmail) {

    showOnly(
      'homePage'
    );

    return;

  }


  try {

    const result =
      await api(
        'checkStatus',
        {
          email:
            currentEmail
        }
      );


    handleParticipantResult(
      result
    );


  } catch (error) {

    showError(
      'waitingInfo',
      error.message ||
      'Gagal memeriksa status.'
    );

  }

}


/* ==========================================================
 * MULAI TES
 * ==========================================================
 */

async function startTest() {

  if (!currentEmail) {

    showOnly(
      'homePage'
    );

    return;

  }


  const button =
    $('startButton');


  button.disabled =
    true;

  button.innerText =
    'MEMULAI...';


  try {

    const result =
      await api(
        'startExam',
        {
          email:
            currentEmail
        }
      );


    if (
      !result ||
      !result.success
    ) {

      if (
        result &&
        result.waiting
      ) {

        showOnly(
          'waitingPage'
        );

        return;

      }


      throw new Error(
        result &&
        result.message
          ? result.message
          : 'Tes gagal dimulai.'
      );

    }


    openExam(
      result
    );


  } catch (error) {

    showError(
      'approvedInfo',
      error.message ||
      'Gagal memulai tes.'
    );

  } finally {

    button.disabled =
      false;

    button.innerText =
      'MULAI TES';

  }

}


/* ==========================================================
 * BUKA EXAM
 * ==========================================================
 */

function openExam(
  data
) {

  currentEmail =
    data.email ||
    currentEmail;


  currentName =
    data.nama ||
    currentName;


  currentSessionId =
    data.sessionId ||
    currentSessionId;


  questions =
    data.questions ||
    [];


  answers =
    data.answers ||
    {};


  endTime =
    Number(
      data.endTime || 0
    );


  if (
    !currentSessionId
  ) {

    showError(
      'homeMessage',
      'Session ujian tidak ditemukan.'
    );

    showOnly(
      'homePage'
    );

    return;

  }


  $('examParticipant')
    .innerHTML =
      participantInfoHtml(
        data
      );


  renderQuestions();

  updateProgress();

  showOnly(
    'examPage'
  );


  startTimer();

}


/* ==========================================================
 * RENDER SOAL
 * ==========================================================
 */

function renderQuestions() {

  const container =
    $('questionsContainer');


  container.innerHTML =
    '';


  if (
    !questions.length
  ) {

    container.innerHTML =
      '<div class="error">' +
      'Tidak ada soal.' +
      '</div>';

    return;

  }


  questions.forEach(
    function(q, index) {

      const number =
        index + 1;


      const box =
        document.createElement(
          'div'
        );


      box.className =
        'question';


      let html =
        '<div class="questionTitle">' +
        number +
        '. ' +
        escapeHtml(
          q.question
        ) +
        '</div>';


      const type =
        String(
          q.type || 'TEXT'
        )
          .toUpperCase();


      /*
       * PILIHAN
       */

      if (
        (
          type === 'RADIO' ||
          type === 'CHOICE' ||
          type === 'SELECT' ||
          type === 'MULTIPLE_CHOICE'
        ) &&
        Array.isArray(
          q.choices
        ) &&
        q.choices.length
      ) {

        q.choices.forEach(
          function(choice) {

            const checked =
              String(
                answers[
                  String(number)
                ] || ''
              ) ===
              String(choice);


            html +=

              '<label class="option">' +

              '<input ' +

              'type="radio" ' +

              'name="question_' +
              number +
              '" ' +

              'value="' +
              escapeHtml(
                choice
              ) +
              '" ' +

              (
                checked
                  ? 'checked'
                  : ''
              ) +

              ' onchange="answerChanged(' +
              number +
              ', this.value)">' +

              escapeHtml(
                choice
              ) +

              '</label>';

          }
        );

      }


      /*
       * TRUE/FALSE
       */

      else if (
        type === 'TRUE_FALSE' ||
        type === 'BOOLEAN'
      ) {

        [
          'Ya',
          'Tidak'
        ]
        .forEach(
          function(choice) {

            const checked =
              String(
                answers[
                  String(number)
                ] || ''
              ) ===
              choice;


            html +=

              '<label class="option">' +

              '<input ' +

              'type="radio" ' +

              'name="question_' +
              number +
              '" ' +

              'value="' +
              choice +
              '" ' +

              (
                checked
                  ? 'checked'
                  : ''
              ) +

              ' onchange="answerChanged(' +
              number +
              ', this.value)">' +

              choice +

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

          'id="question_' +
          number +
          '" ' +

          'placeholder="Ketik jawaban Anda..." ' +

          'oninput="answerChanged(' +
          number +
          ', this.value)">' +

          escapeHtml(
            answers[
              String(number)
            ] || ''
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


/* ==========================================================
 * JAWABAN BERUBAH
 * ==========================================================
 */

function answerChanged(
  number,
  value
) {

  answers[
    String(number)
  ] =
    value;


  updateProgress();


  /*
   * Simpan satu jawaban.
   * Tidak mengirim seluruh object.
   */

  if (
    saveTimeout
  ) {

    clearTimeout(
      saveTimeout
    );

  }


  saveTimeout =
    setTimeout(
      function() {

        saveSingleAnswer(
          number,
          value
        );

      },
      500
    );

}


/* ==========================================================
 * SIMPAN SATU JAWABAN
 * ==========================================================
 */

async function saveSingleAnswer(
  number,
  value
) {

  if (
    !currentSessionId ||
    !currentEmail ||
    isSubmitting
  ) {

    return;

  }


  try {

    await api(
      'saveAnswer',
      {

        sessionId:
          currentSessionId,

        email:
          currentEmail,

        number:
          number,

        answer:
          value

      }
    );


  } catch (error) {

    console.log(
      'Gagal autosave:',
      error
    );

  }

}


/* ==========================================================
 * PROGRESS
 * ==========================================================
 */

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

        String(
          value
        ).trim() !== ''

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


/* ==========================================================
 * TIMER
 * ==========================================================
 */

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


/* ==========================================================
 * UPDATE TIMER
 * ==========================================================
 */

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


  $('timer')
    .innerText =

      String(
        minutes
      )
        .padStart(
          2,
          '0'
        ) +

      ':' +

      String(
        seconds
      )
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


/* ==========================================================
 * AUTO SUBMIT
 * ==========================================================
 */

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

    const result =
      await api(
        'submitExam',
        {

          sessionId:
            currentSessionId,

          email:
            currentEmail,

          answers:
            JSON.stringify(
              answers
            )

        }
      );


    finishExam(
      result
    );


  } catch (error) {

    /*
     * Jika server sudah menerima submit tetapi
     * browser gagal membaca respons, jangan membuat
     * peserta mengulang.
     */

    finishExam({
      success: true,
      autoSubmit: true
    });

  }

}


/* ==========================================================
 * SUBMIT MANUAL
 * ==========================================================
 */

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

    const result =
      await api(
        'submitExam',
        {

          sessionId:
            currentSessionId,

          email:
            currentEmail,

          answers:
            JSON.stringify(
              answers
            )

        }
      );


    finishExam(
      result
    );


  } catch (error) {

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


/* ==========================================================
 * SELESAI
 * ==========================================================
 */

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

  } else {

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


/* ==========================================================
 * LOAD
 * ==========================================================
 */

window.addEventListener(
  'load',
  function() {

    $('email')
      .focus();

  }
);


/* ==========================================================
 * ENTER EMAIL
 * ==========================================================
 */

$('email')
  .addEventListener(
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


/* ==========================================================
 * ENTER NAME
 * ==========================================================
 */

$('name')
  .addEventListener(
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
