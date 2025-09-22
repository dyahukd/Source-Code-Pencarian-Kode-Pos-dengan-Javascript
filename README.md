# Source-Code-Pencarian-Kode-Pos-dengan-Javascript
Berikut adalah source code untuk membuat suatu form yang berfungsi untuk mencari kode pos dengan menginput provinsi, kabupaten/kota, dan kecamatan.
```
<html>
<head>
  <meta charset="UTF-8">
  <title>Pencarian Kode Pos</title>
  <style>
    body {
      font-family: Palatino, Georgia;
      background: #fce4ec;
      color: #333;
      text-align: center;
      padding: 20px;
    }
    .container {
      background: white;
      padding: 20px;
      border-radius: 10px;
      width: 400px;
      margin: auto;
      box-shadow: 0 2px 5px rgba(0,0,0,0.2);
    }
    h2 {
      color: #d81b60;
    }
    select, input {
      width: 90%;
      padding: 8px;
      margin: 8px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      background: #d81b60;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 5px;
      cursor: pointer;
    }
    .hasil {
      margin-top: 20px;
      padding: 15px;
      background: #e8f5e9;
      border-radius: 5px;
      color: #2e7d32;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Pencarian Kode Pos</h2>
    
    <label>Provinsi:</label>
    <select id="provinsi">
      <option value="">Pilih Provinsi</option>
      <option value="Jawa Timur">Jawa Timur</option>
      <option value="DKI Jakarta">DKI Jakarta</option>
    </select><br>

    <label>Kota/Kabupaten:</label>
    <select id="kota">
      <option value="">Pilih Kota/Kabupaten</option>
      <option value="Surabaya">Surabaya</option>
      <option value="Sidoarjo">Sidoarjo</option>
      <option value="Jakarta Pusat">Jakarta Pusat</option>
    </select><br>

    <label>Kecamatan:</label>
    <select id="kecamatan">
      <option value="">Pilih Kecamatan</option>
      <option value="Sukolilo">Sukolilo</option>
      <option value="Rungkut">Rungkut</option>
      <option value="Menteng">Menteng</option>
    </select><br>

    <button onclick="carikodepos()">Cari</button>

    <div id="output" class="hasil" style="display:none;"></div>
  </div>

  <script>
    const kodepos = [
      {provinsi: "Jawa Timur", kota: "Surabaya", kecamatan: "Sukolilo", kodepos: "60111"},
      {provinsi: "Jawa Timur", kota: "Surabaya", kecamatan: "Rungkut", kodepos: "60293"},
      {provinsi: "Jawa Timur", kota: "Sidoarjo", kecamatan: "Candi", kodepos: "61271"},
      {provinsi: "DKI Jakarta", kota: "Jakarta Pusat", kecamatan: "Menteng", kodepos: "10310"}
    ];

    function carikodepos() {
      let prov = document.getElementById("provinsi").value;
      let kota = document.getElementById("kota").value;
      let kec = document.getElementById("kecamatan").value;

      let hasil = kodepos.find(item => 
        item.provinsi === prov && item.kota === kota && item.kecamatan === kec
      );

      let output = document.getElementById("output");
      if (hasil) {
        output.style.display = "block";
        output.innerHTML = `
          <b>Kode Pos:</b> ${hasil.kodepos} <br>
          <b>Daerah:</b> ${hasil.kecamatan}, ${hasil.kota}, ${hasil.provinsi}
        `;
      } else {
        output.style.display = "block";
        output.innerHTML = "Data tidak ditemukan.";
      }
    }
  </script>
</body>
</html>
```
