# lien-pour-verification
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Ben Adaptivité</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f1f0ff;
      color: #202124;
    }

    .container {
      max-width: 700px;
      margin: auto;
      padding: 15px;
    }

    .header,
    .question {
      background: white;
      border-radius: 12px;
      margin-bottom: 15px;
      padding: 22px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.12);
    }

    .header {
      border-top: 8px solid #5b45df;
    }

    h1 {
      margin: 0 0 8px;
      font-size: 30px;
    }

    .description {
      color: #666;
      margin: 0;
    }

    .required {
      color: #d93025;
      font-size: 14px;
    }

    .question-title {
      font-size: 18px;
      font-weight: bold;
      margin-bottom: 15px;
    }

    .required-star {
      color: red;
    }

    input[type="text"],
    input[type="tel"],
    input[type="number"] {
      width: 100%;
      border: none;
      border-bottom: 2px solid #ddd;
      padding: 12px 2px;
      font-size: 16px;
      outline: none;
      background: transparent;
    }

    input:focus {
      border-bottom: 2px solid #5b45df;
    }

    .option {
      display: block;
      margin: 14px 0;
      font-size: 17px;
    }

    .option input {
      width: 18px;
      height: 18px;
      margin-right: 10px;
      accent-color: #5b45df;
    }

    .buttons {
      display: flex;
      justify-content: space-between;
      gap: 15px;
    }

    button {
      padding: 14px 25px;
      border: none;
      border-radius: 7px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
    }

    .send {
      background: #5b45df;
      color: white;
    }

    .delete {
      background: #eeeeee;
      color: #333;
    }

    .message {
      display: none;
      margin-top: 15px;
      padding: 15px;
      border-radius: 8px;
      background: #e8f5e9;
      color: #1b5e20;
      text-align: center;
      font-weight: bold;
    }

    .loading {
      background: #fff3cd;
      color: #856404;
    }

    @media (max-width: 500px) {
      h1 {
        font-size: 25px;
      }

      .question {
        padding: 18px;
      }

      .buttons {
        flex-direction: column;
      }

      button {
        width: 100%;
      }
    }
  </style>
</head>

<body>

<div class="container">

  <!-- EN-TÊTE -->
  <div class="header">

    <h1>Ben Adaptivité</h1>

    <p class="description">
      Formulaire de participation
    </p>

    <p class="required">
      * Indique une question obligatoire
    </p>

  </div>


  <!--
    FORMULAIRE CONNECTÉ À TON GOOGLE APPS SCRIPT
  -->
  <form
    id="monFormulaire"
    action="https://script.google.com/macros/s/AKfycbz6nmcZZZ0g85Q_6z3ZYsFiEaj0GYm2sUO-n4jFWP2bczFnHloJB3DcXasnnwUfShqK/exec"
    method="POST"
    target="envoi">

    <!-- NOM ET PRÉNOM -->
    <div class="question">

      <div class="question-title">
        Nom et prénom
        <span class="required-star">*</span>
      </div>

      <input
        type="text"
        name="nom"
        placeholder="Votre réponse"
        required>

    </div>


    <!-- NUMÉRO -->
    <div class="question">

      <div class="question-title">
        Numéro de téléphone
        <span class="required-star">*</span>
      </div>

      <input
        type="tel"
        name="telephone"
        placeholder="Votre numéro"
        required>

    </div>


    <!-- WHATSAPP -->
    <div class="question">

      <div class="question-title">
        Ton numéro WhatsApp
        <span class="required-star">*</span>
      </div>

      <input
        type="tel"
        name="whatsapp"
        placeholder="Votre numéro WhatsApp"
        required>

    </div>


    <!-- GENRE -->
    <div class="question">

      <div class="question-title">
        Ton genre
        <span class="required-star">*</span>
      </div>

      <label class="option">
        <input
          type="radio"
          name="genre"
          value="Homme"
          required>
        Homme
      </label>

      <label class="option">
        <input
          type="radio"
          name="genre"
          value="Femme">
        Femme
      </label>

    </div>


    <!-- ATF -->
    <div class="question">

      <div class="question-title">
        Êtes-vous fier de ZAP à l'ATF ?
        <span class="required-star">*</span>
      </div>

      <label class="option">
        <input
          type="radio"
          name="atf"
          value="Oui"
          required>
        Oui
      </label>

      <label class="option">
        <input
          type="radio"
          name="atf"
          value="Non">
        Non
      </label>

    </div>


    <!-- MOYENNE -->
    <div class="question">

      <div class="question-title">
        Ta moyenne
        <span class="required-star">*</span>
      </div>

      <input
        type="number"
        name="moyenne"
        min="0"
        max="20"
        step="0.01"
        placeholder="Exemple : 14,50"
        required>

    </div>


    <!-- SÉRIE -->
    <div class="question">

      <div class="question-title">
        Ta série
        <span class="required-star">*</span>
      </div>

      <label class="option">
        <input
          type="radio"
          name="serie"
          value="C"
          required>
        C
      </label>

      <label class="option">
        <input
          type="radio"
          name="serie"
          value="D">
        D
      </label>

      <label class="option">
        <input
          type="radio"
          name="serie"
          value="E">
        E
      </label>

      <label class="option">
        <input
          type="radio"
          name="serie"
          value="F">
        F
      </label>

      <label class="option">
        <input
          type="radio"
          name="serie"
          value="H">
        H
      </label>

      <label class="option">
        <input
          type="radio"
          name="serie"
          value="Autre">
        Autre
      </label>

    </div>


    <!-- BOUTONS -->
    <div class="question">

      <div class="buttons">

        <button
          type="submit"
          class="send">
          Envoyer
        </button>

        <button
          type="reset"
          class="delete">
          Supprimer
        </button>

      </div>

      <div
        id="message"
        class="message">
      </div>

    </div>

  </form>


  <!--
    Cette iframe permet d'envoyer le formulaire
    sans quitter la page.
  -->
  <iframe
    name="envoi"
    id="envoi"
    style="display:none;">
  </iframe>

</div>


<script>

const formulaire =
  document.getElementById("monFormulaire");

const message =
  document.getElementById("message");

formulaire.addEventListener("submit", function() {

  message.style.display = "block";

  message.className = "message loading";

  message.textContent =
    "⏳ Envoi de votre réponse...";

  /*
    Après l'envoi, on affiche la confirmation.
  */
  setTimeout(function() {

    message.className = "message";

    message.textContent =
      "✅ Réponse envoyée avec succès !";

    formulaire.reset();

  }, 1500);

});

</script>

</body>
</html>