<!DOCTYPE html>
<html lang="el">
<head>
  <meta charset="UTF-8">
  <title>Η Blockchain Σελίδα μου</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to right, #e0eafc, #cfdef3);
      text-align: center;
      padding-top: 100px;
      color: #333;
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 30px;
    }

    button {
      padding: 15px 30px;
      font-size: 1em;
      background-color: #4caf50;
      color: white;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #45a049;
    }

    #wallet {
      margin-top: 20px;
      font-size: 1.1em;
    }

    footer {
      margin-top: 100px;
      font-size: 0.9em;
      color: #666;
    }
  </style>
</head>
<body>

  <h1>🔗 Καλωσήρθες στην Blockchain Σελίδα μου</h1>

  <button onclick="syndesiWallet()">Σύνδεση με Πορτοφόλι</button>
  <p id="wallet">Δεν έχει γίνει σύνδεση ακόμα.</p>

  <footer>
    Δημιουργήθηκε από τον Σίμο με 💚 Web3
  </footer>

  <script>
    async function syndesiWallet() {
      if (typeof window.ethereum !== 'undefined') {
        try {
          const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' });
          document.getElementById('wallet').innerText = 'Συνδέθηκες με: ' + accounts[0];
        } catch (err) {
          document.getElementById('wallet').innerText =
