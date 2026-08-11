<html lang="id">

<head>

<meta charset="UTF-8">

<meta
  name="viewport"
  content="width=device-width,initial-scale=1.0">

<title>Recruitment Test</title>

<style>

* {
  box-sizing: border-box;
}

body {

  margin: 0;

  padding: 20px;

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

  max-width:
    760px;

  margin:
    30px auto;

}

.card {

  background:
    white;

  padding:
    28px;

  border-radius:
    14px;

  box-shadow:
    0 4px 18px
    rgba(0,0,0,.08);

}

h1,
h2 {

  margin-top:
    0;

}

.subtitle {

  margin-bottom:
    25px;

  color:
    #666;

}

label {

  display:
    block;

  margin-top:
    15px;

  margin-bottom:
    6px;

  font-weight:
    bold;

}

input,
textarea,
select {

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

textarea {

  min-height:
    120px;

  resize:
    vertical;

}

button {

  width:
    100%;

  margin-top:
    20px;

  padding:
    14px;

  border:
    0;

  border-radius:
    8px;

  background:
    #1769aa;

  color:
    white;

  font-size:
    15px;

  font-weight:
    bold;

  cursor:
    pointer;

}

button:disabled {

  opacity:
    .6;

  cursor:
    not-allowed;

}

.success {

  background:
    #168544;

}

.warning {

  padding:
    16px;

  margin-top:
    20px;

  border-radius:
    8px;

  background:
    #fff3cd;

}

.info {

  padding:
    16px;

  margin-top:
    20px;

  border-radius:
    8px;

  background:
    #e7f3ff;

}

.error {

  padding:
    14px;

  margin-top:
    15px;

  border-radius:
    8px;

  background:
    #ffe5e5;

  color:
    #a00000;

}

.rules {

  margin-top:
    20px;

  padding:
    18px;

  background:
    #f7f7f7;

  border-radius:
    8px;

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
    #f5f5f5;

  border-radius:
    8px;

}

.page {

  display:
    none;

}

.page.active {

  display:
    block;

}

.timer {

  text-align:
    center;

  font-size:
    32px;

  font-weight:
    bold;

  margin-bottom:
    20px;

}

.warningTimer {

  color:
    #d58a00;

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
    #ddd;

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
    #1769aa;

}

.question {

  padding:
    20px;

  margin-bottom:
    18px;

  border:
    1px solid #ddd;

  border-radius:
    10px;

}

.questionTitle {

  font-weight:
    bold;

  margin-bottom:
    15px;

}

.option {

  display:
    block;

  padding:
    10px;

  margin:
    7px 0;

  border:
    1px solid #ddd;

  border-radius:
    7px;

}

.option input {

  width:
    auto;

  margin-right:
    8px;

}

.small {

  font-size:
    13px;

  color:
    #777;

}

</style>

</head>


<body>


<div class="container">


<!-- =====================================================
     HOME
===================================================== -->

<div
  id="homePage"
  class="card page active">

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


<!-- =====================================================
     WAITING
===================================================== -->

<div
  id="waitingPage"
  class="card page">

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


<!-- =====================================================
     APPROVED
===================================================== -->

<div
  id="approvedPage"
  class="card page">

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


<!-- =====================================================
     EXAM
===================================================== -->

<div
  id="examPage"
  class="card page">

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


<!-- =====================================================
     FINISHED
===================================================== -->

<div
  id="finishedPage"
  class="card page">

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


/* ======================================================
   API
====================================================== */

const API_URL =
  'https://script.google.com/macros/s/AKfycbwF-IzqUDYnpuQXbCrAwi4f_dKGNtRO3xK2qc2akf2ylRYwiHEEnunIrDSDXElzP5gZ/exec';


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
          value
        );

      }
    );


  const response =
    await fetch(
      API_URL,
      {
        method:
          'POST',

        headers: {
          'Content-Type':
            'application/x-www-form-urlencoded;charset=UTF-8'
        },

        body:
          body.toString()
      }
    );


  const text =
    await response.text();


  let result;


  try {

    result =
      JSON.parse(
        text
      );

  } catch (error) {

    throw new Error(
      'Respons server tidak valid.'
    );

  }


  if (
    result &&
    result.success === false &&
    result.message
  ) {

    throw new Error(
      result.message
    );

  }


  return result;

}


/* ======================================================
   GLOBAL
====================================================== */

let currentEmail =
  '';

let currentName =
  '';

let currentSessionId =
  '';

let questions =
  [];

let answers =
  {};

let endTime =
  0;

let timerInterval =
  null;

let saveTimeout =
  null;

let isSubmitting =
  false;


/* ======================================================
   HELPER
====================================================== */

function $(id) {

  return document.getElementById(
    id
  );

}


function showOnly(
  pageId
) {

  document
    .querySelectorAll(
      '.page'
    )
    .forEach(
      function(page) {

        page.classList.remove(
          'active'
        );

      }
    );


  $(pageId)
    .classList
    .add(
      'active'
    );

}


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


function escapeHtml(
  value
) {

  return String(
    value || ''
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


/* ======================================================
   PERIKSA DATA
====================================================== */

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


  $('checkButton')
    .disabled = true;


  $('checkButton')
    .innerText =
      'MEMERIKSA...';


  $('homeMessage')
    .innerHTML =
      '';


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


    currentEmail =
      email;

    currentName =
      name;


    if (
      result.hasHistory
    ) {

      showError(
        'homeMessage',
        result.message
      );

      return;

    }


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

  }

  catch (error) {

    showError(
      'homeMessage',
      error.message
    );

  }

  finally {

    $('checkButton')
      .disabled = false;

    $('checkButton')
      .innerText =
        'PERIKSA DATA';

  }

}


/* ======================================================
   WAITING
====================================================== */

function showWaiting(
  data
) {

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

  showOnly(
    'waitingPage'
  );

}


/* ======================================================
   CEK STATUS LAGI
====================================================== */

async function checkStatusAgain() {

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

      showError(
        'waitingInfo',
        result.message
      );

      return;

    }


    if (
      result.activeSession
    ) {

      loadExam(
        result
      );

      return;

    }


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

  }

  catch (error) {

    showError(
      'waitingInfo',
      error.message
    );

  }

}


/* ======================================================
   APPROVED
====================================================== */

function showApproved(
  data
) {

  currentEmail =
    data.email ||
    currentEmail;


  currentName =
    data.nama ||
    currentName;


  $('approvedInfo')
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

  showOnly(
    'approvedPage'
  );

}


/* ======================================================
   START TEST
====================================================== */

async function startTest() {

  $('startButton')
    .disabled = true;


  $('startButton')
    .innerText =
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


    loadExam(
      result
    );

  }

  catch (error) {

    showError(
      'approvedInfo',
      error.message
    );

  }

  finally {

    $('startButton')
      .disabled = false;

    $('startButton')
      .innerText =
        'MULAI TES';

  }

}


/* ======================================================
   LOAD EXAM
====================================================== */

function loadExam(
  data
) {

  currentSessionId =
    data.sessionId;

  currentEmail =
    data.email ||
    currentEmail;

  currentName =
    data.nama ||
    currentName;

  questions =
    data.questions ||
    [];

  answers =
    data.answers ||
    {};

  endTime =
    Number(
      data.endTime
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

  showOnly(
    'examPage'
  );

  startTimer();

}


/* ======================================================
   RENDER SOAL
====================================================== */

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


      const title =
        document.createElement(
          'div'
        );


      title.className =
        'questionTitle';


      title.innerHTML =
        number +
        '. ' +
        escapeHtml(
          q.question
        );


      box.appendChild(
        title
      );


      const type =
        String(
          q.type ||
          'TEXT'
        )
          .toUpperCase();


      if (
        q.choices &&
        q.choices.length &&
        (
          type === 'RADIO' ||
          type === 'CHOICE' ||
          type === 'MCQ' ||
          type === 'MULTIPLE_CHOICE'
        )
      ) {

        q.choices.forEach(
          function(choice) {

            const label =
              document.createElement(
                'label'
              );


            label.className =
              'option';


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
                ] || ''
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
                  this.value
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

      }


      else if (
        q.choices &&
        q.choices.length &&
        (
          type === 'CHECKBOX' ||
          type === 'MULTI'
        )
      ) {

        const old =
          Array.isArray(
            answers[
              String(number)
            ]
          )
            ? answers[
                String(number)
              ]
            : [];


        q.choices.forEach(
          function(choice) {

            const label =
              document.createElement(
                'label'
              );


            label.className =
              'option';


            const input =
              document.createElement(
                'input'
              );


            input.type =
              'checkbox';


            input.value =
              choice;


            input.checked =
              old.includes(
                choice
              );


            input.addEventListener(
              'change',
              function() {

                const values =
                  Array.from(
                    box.querySelectorAll(
                      'input[type="checkbox"]:checked'
                    )
                  )
                  .map(
                    function(item) {
                      return item.value;
                    }
                  );


                answerChanged(
                  number,
                  values
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

      }


      else {

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
              this.value
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


/* ======================================================
   ANSWER CHANGED
====================================================== */

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


/* ======================================================
   PROGRESS
====================================================== */

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


/* ======================================================
   AUTOSAVE
====================================================== */

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

  }

  catch (error) {

    console.log(
      'Autosave gagal:',
      error
    );

  }

}


/* ======================================================
   TIMER
====================================================== */

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


/* ======================================================
   AUTO SUBMIT
====================================================== */

async function autoSubmitTest() {

  if (
    isSubmitting
  ) {

    return;

  }


  isSubmitting =
    true;


  $('submitButton')
    .disabled = true;


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

  }

  catch (error) {

    finishExam({
      success: true,
      autoSubmit: true
    });

  }

}


/* ======================================================
   MANUAL SUBMIT
====================================================== */

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
    .disabled = true;


  $('submitButton')
    .innerText =
      'MENGIRIM...';


  try {

    await saveCurrentAnswers();


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

  }

  catch (error) {

    isSubmitting =
      false;


    $('submitButton')
      .disabled = false;


    $('submitButton')
      .innerText =
        'KIRIM JAWABAN';


    showError(
      'examMessage',
      error.message
    );

  }

}


/* ======================================================
   FINISH
====================================================== */

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


/* ======================================================
   LOAD
====================================================== */

window.addEventListener(
  'load',
  function() {

    $('email')
      .focus();

  }
);


/* ======================================================
   ENTER
====================================================== */

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
