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

  font-family:
    Arial,
    Helvetica,
    sans-serif;

  background:
    #f4f6f8;

  color:
    #222;

}

.container {

  width:
    min(760px, 94%);

  margin:
    30px auto;

}

.card {

  background:
    white;

  border-radius:
    16px;

  padding:
    24px;

  box-shadow:
    0 5px 25px
    rgba(0,0,0,.08);

}

h1,
h2 {

  margin-top:
    0;

}

.subtitle {

  color:
    #666;

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

input {

  width:
    100%;

  padding:
    13px;

  border:
    1px solid #ccc;

  border-radius:
    8px;

  font-size:
    16px;

}

button {

  width:
    100%;

  padding:
    14px;

  margin-top:
    20px;

  border:
    0;

  border-radius:
    8px;

  background:
    #1a73e8;

  color:
    white;

  font-weight:
    bold;

  font-size:
    15px;

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

.rules {

  background:
    #f8f9fa;

  padding:
    18px;

  border-radius:
    10px;

  margin-top:
    20px;

}

.rules li {

  margin-bottom:
    8px;

}

.warning {

  background:
    #fff3cd;

  border:
    1px solid #ffe69c;

  padding:
    18px;

  border-radius:
    10px;

}

.info {

  background:
    #dff5e5;

  border:
    1px solid #a8dfb8;

  padding:
    18px;

  border-radius:
    10px;

}

.error {

  background:
    #fde2e2;

  color:
    #9b1c1c;

  border:
    1px solid #f5b5b5;

  padding:
    14px;

  border-radius:
    8px;

  margin-top:
    15px;

}

.participant {

  margin-top:
    15px;

  padding:
    14px;

  background:
    #f5f7fa;

  border-radius:
    8px;

}

.timer {

  text-align:
    center;

  font-size:
    34px;

  font-weight:
    bold;

  margin-bottom:
    18px;

}

.warningTimer {

  color:
    #d98200;

}

.dangerTimer {

  color:
    #d00000;

}

.progress {

  width:
    100%;

  height:
    10px;

  background:
    #e5e7eb;

  border-radius:
    10px;

  overflow:
    hidden;

  margin:
    20px 0;

}

.progressBar {

  height:
    100%;

  width:
    0%;

  background:
    #1a73e8;

  transition:
    width .2s;

}

.question {

  padding:
    18px;

  border:
    1px solid #ddd;

  border-radius:
    12px;

  margin-bottom:
    18px;

}

.questionTitle {

  font-weight:
    bold;

  margin-bottom:
    15px;

}

.choice {

  display:
    block;

  padding:
    10px;

  margin:
    8px 0;

  background:
    #f8f9fa;

  border-radius:
    8px;

}

.choice input {

  width:
    auto;

  margin-right:
    8px;

}

textarea {

  width:
    100%;

  min-height:
    120px;

  padding:
    12px;

  border:
    1px solid #ccc;

  border-radius:
    8px;

  font-size:
    15px;

  resize:
    vertical;

}

.success {

  background:
    #198754;

}

.hidden {

  display:
    none !important;

}

.center {

  text-align:
    center;

}

.small {

  font-size:
    13px;

  color:
    #666;

}

</style>

</head>


<body>

<div class="container">


<!-- ========================================================
     HOME
========================================================= -->

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
        Setelah tes dikirim, tes tidak dapat diulang.
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


<!-- ========================================================
     WAITING
========================================================= -->

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


<!-- ========================================================
     APPROVED
========================================================= -->

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


<!-- ========================================================
     EXAM
========================================================= -->

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


<!-- ========================================================
     FINISHED
========================================================= -->

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
   WEB APP URL
========================================================== */

const WEB_APP_URL =
  'https://script.google.com/macros/s/AKfycbwF-IzqUDYnpuQXbCrAwi4f_dKGNtRO3xK2qc2akf2ylRYwiHEEnunIrDSDXElzP5gZ/exec';


/* ==========================================================
   GLOBAL
========================================================== */

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
   HELPER
========================================================== */

function $(id) {

  return document.getElementById(id);

}


/* ==========================================================
   SHOW PAGE
========================================================== */

function showOnly(pageId) {

  const pages = [

    'homePage',

    'waitingPage',

    'approvedPage',

    'examPage',

    'finishedPage'

  ];


  pages.forEach(
    function(id) {

      const el =
        $(id);

      if (!el) {
        return;
      }

      el.classList.toggle(
        'hidden',
        id !== pageId
      );

    }
  );

}


/* ==========================================================
   ERROR
========================================================== */

function showError(
  elementId,
  message
) {

  const el =
    $(elementId);

  if (!el) {
    return;
  }

  el.innerHTML =
    '<div class="error">' +
    escapeHtml(
      message ||
      'Terjadi kesalahan.'
    ) +
    '</div>';

}


/* ==========================================================
   ESCAPE HTML
========================================================== */

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
   API FETCH
========================================================== */

async function api(
  action,
  data = {}
) {

  const body =
    new URLSearchParams();

  body.append(
    'action',
    action
  );


  Object.keys(data)
    .forEach(
      function(key) {

        let value =
          data[key];

        if (
          value !== null &&
          typeof value ===
            'object'
        ) {

          value =
            JSON.stringify(
              value
            );

        }

        body.append(
          key,
          value == null
            ? ''
            : String(value)
        );

      }
    );


  let response;

  try {

    response =
      await fetch(
        WEB_APP_URL,
        {

          method:
            'POST',

          mode:
            'cors',

          headers: {

            'Content-Type':
              'application/x-www-form-urlencoded;charset=UTF-8'

          },

          body:
            body.toString(),

          redirect:
            'follow'

        }
      );

  } catch (error) {

    throw new Error(
      'Gagal terhubung ke Web App. Pastikan deployment Apps Script sudah aktif dan aksesnya "Anyone".'
    );

  }


  if (!response.ok) {

    throw new Error(
      'Web App mengembalikan HTTP ' +
      response.status
    );

  }


  let result;

  try {

    result =
      await response.json();

  } catch (error) {

    throw new Error(
      'Respons Web App bukan JSON. Pastikan Code.gs sudah diganti dengan versi API.'
    );

  }


  if (
    result &&
    result.success === false &&
    result.message
  ) {

    /*
     * Beberapa response false memang bukan
     * error teknis, misalnya waiting.
     * Tetap dikembalikan.
     */

  }


  return result;

}


/* ==========================================================
   CHECK PARTICIPANT
========================================================== */

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


  $('homeMessage')
    .innerHTML = '';


  try {

    const result =
      await api(
        'register',
        {

          email:
            email,

          name:
            name

        }
      );


    if (
      result.hasHistory
    ) {

      currentEmail =
        email;

      currentName =
        name;

      showOnly(
        'finishedPage'
      );

      $('finishedMessage')
        .innerHTML =
          '<strong>Tes tidak dapat diulang.</strong><br><br>' +
          escapeHtml(
            result.message
          );

      return;

    }


    currentEmail =
      result.email ||
      email;

    currentName =
      result.nama ||
      name;


    if (
      result.approved
    ) {

      showApproved(
        result
      );

      return;

    }


    showWaiting(
      result
    );

  } catch (error) {

    showError(
      'homeMessage',
      error.message
    );

  } finally {

    button.disabled =
      false;

    button.innerText =
      'PERIKSA DATA';

  }

}


/* ==========================================================
   WAITING
========================================================== */

function showWaiting(
  data
) {

  showOnly(
    'waitingPage'
  );


  $('waitingInfo')
    .innerHTML =

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

}


/* ==========================================================
   APPROVED
========================================================== */

function showApproved(
  data
) {

  showOnly(
    'approvedPage'
  );


  $('approvedInfo')
    .innerHTML =

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

}


/* ==========================================================
   CHECK STATUS AGAIN
========================================================== */

async function checkStatusAgain() {

  if (!currentEmail) {

    currentEmail =
      $('email')
        .value
        .trim()
        .toLowerCase();

  }


  if (!currentEmail) {

    showOnly(
      'homePage'
    );

    return;

  }


  try {

    const result =
      await api(
        'status',
        {

          email:
            currentEmail

        }
      );


    if (
      result.hasHistory
    ) {

      showOnly(
        'finishedPage'
      );

      $('finishedMessage')
        .innerHTML =
          '<strong>Tes sudah selesai.</strong><br><br>' +
          escapeHtml(
            result.message
          );

      return;

    }


    if (
      result.activeSession
    ) {

      currentName =
        result.nama ||
        currentName;

      restoreExam(
        result
      );

      return;

    }


    if (
      result.approved
    ) {

      currentName =
        result.nama ||
        currentName;

      showApproved(
        result
      );

      return;

    }


    showWaiting(
      result
    );

  } catch (error) {

    /*
     * Tetap berada di halaman waiting
     * jika pemeriksaan gagal.
     */

    showError(
      'waitingInfo',
      error.message
    );

  }

}


/* ==========================================================
   START TEST
========================================================== */

async function startTest() {

  if (!currentEmail) {

    currentEmail =
      $('email')
        .value
        .trim()
        .toLowerCase();

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
        'start',
        {

          email:
            currentEmail

        }
      );


    if (
      result.waiting
    ) {

      showWaiting(
        result
      );

      return;

    }


    if (
      result.activeSession
    ) {

      restoreExam(
        result
      );

      return;

    }


    if (
      !result.success
    ) {

      throw new Error(
        result.message ||
        'Tes tidak dapat dimulai.'
      );

    }


    restoreExam(
      result
    );

  } catch (error) {

    showApproved(
      {
        email:
          currentEmail,

        nama:
          currentName
      }
    );

    showError(
      'approvedInfo',
      error.message
    );

  } finally {

    button.disabled =
      false;

    button.innerText =
      'MULAI TES';

  }

}


/* ==========================================================
   RESTORE / START EXAM
========================================================== */

function restoreExam(
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
    Array.isArray(
      data.questions
    )
      ? data.questions
      : [];

  answers =
    data.answers ||
    {};

  endTime =
    Number(
      data.endTime ||
      (
        Date.now() +
        Number(
          data.remaining ||
          0
        )
      )
    );


  showOnly(
    'examPage'
  );


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


  renderQuestions();

  updateProgress();

  startTimer();

}


/* ==========================================================
   RENDER QUESTIONS
========================================================== */

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
      'Tidak ada soal yang diterima.' +
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


      const title =
        document.createElement(
          'div'
        );

      title.className =
        'questionTitle';


      title.innerText =
        number +
        '. ' +
        q.question;


      box.appendChild(
        title
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


      /*
       * RADIO / PILIHAN GANDA
       */

      if (
        type === 'RADIO' ||
        type === 'SINGLE' ||
        type === 'SINGLE_CHOICE' ||
        type === 'PILIHAN GANDA' ||
        type === 'PILIHAN_GANDA'
      ) {

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
              'radio';

            input.name =
              'question_' +
              number;

            input.value =
              choice;


            if (
              String(
                answers[
                  String(number)
                ] ||
                ''
              ) ===
              String(choice)
            ) {

              input.checked =
                true;

            }


            input.addEventListener(
              'change',
              function() {

                answerChanged(
                  number,
                  input.value
                );

              }
            );


            label.appendChild(
              input
            );

            label.appendChild(
              document.createTextNode(
                choice
              )
            );


            box.appendChild(
              label
            );

          }
        );


      /*
       * CHECKBOX / MULTIPLE
       */

      } else if (

        type === 'CHECKBOX' ||
        type === 'MULTIPLE' ||
        type === 'MULTI' ||
        type === 'MULTIPLE_CHOICE'

      ) {

        let selected =
          answers[
            String(number)
          ];


        if (
          !Array.isArray(
            selected
          )
        ) {

          selected =
            selected
              ? String(
                  selected
                )
                  .split(',')
                  .map(
                    function(v) {
                      return v.trim();
                    }
                  )
                  .filter(Boolean)
              : [];

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
              selected.includes(
                choice
              );


            input.addEventListener(
              'change',
              function() {

                const checked =
                  Array.from(
                    box.querySelectorAll(
                      'input[type="checkbox"]'
                    )
                  )
                  .filter(
                    function(el) {
                      return el.checked;
                    }
                  )
                  .map(
                    function(el) {
                      return el.value;
                    }
                  );


                answerChanged(
                  number,
                  checked
                );

              }
            );


            label.appendChild(
              input
            );

            label.appendChild(
              document.createTextNode(
                choice
              )
            );


            box.appendChild(
              label
            );

          }
        );


      /*
       * TEXT
       */

      } else {

        const textarea =
          document.createElement(
            'textarea'
          );


        textarea.placeholder =
          'Tulis jawaban Anda...';


        textarea.value =
          answers[
            String(number)
          ] || '';


        textarea.addEventListener(
          'input',
          function() {

            answerChanged(
              number,
              textarea.value
            );

          }
        );


        box.appendChild(
          textarea
        );

      }


      container.appendChild(
        box
      );

    }
  );

}


/* ==========================================================
   ANSWER CHANGED
========================================================== */

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


/* ==========================================================
   PROGRESS
========================================================== */

function updateProgress() {

  if (
    !questions.length
  ) {

    return;

  }


  let answered = 0;


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
            : String(
                value
              ).trim() !== ''
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


/* ==========================================================
   SAVE ANSWERS
========================================================== */

async function saveCurrentAnswers() {

  if (

    !currentSessionId ||

    !currentEmail ||

    isSubmitting

  ) {

    return;

  }


  try {

    await api(
      'save',
      {

        sessionId:
          currentSessionId,

        email:
          currentEmail,

        answers:
          answers

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
   TIMER
========================================================== */

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


/* ==========================================================
   UPDATE TIMER
========================================================== */

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
   AUTO SUBMIT
========================================================== */

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
        'submit',
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

  } catch (error) {

    /*
     * Jangan langsung menganggap sukses
     * jika API gagal.
     */

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
      error.message
    );

  }

}


/* ==========================================================
   MANUAL SUBMIT
========================================================== */

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
     * Simpan jawaban terakhir
     */

    await api(
      'save',
      {

        sessionId:
          currentSessionId,

        email:
          currentEmail,

        answers:
          answers

      }
    );


    const result =
      await api(
        'submit',
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
      error.message
    );

  }

}


/* ==========================================================
   FINISH
========================================================== */

function finishExam(
  data
) {

  if (timerInterval) {

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
   PAGE LOAD
========================================================== */

window.addEventListener(
  'load',
  function() {

    $('email')
      .focus();

  }
);


/* ==========================================================
   ENTER EMAIL
========================================================== */

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


/* ==========================================================
   ENTER NAME
========================================================== */

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


/* ==========================================================
   AUTO CHECK SESSION
   Jika halaman di-refresh saat ujian aktif,
   peserta bisa memasukkan email lalu cek lagi.
========================================================== */

</script>

</body>

</html>
