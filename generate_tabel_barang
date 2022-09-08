<?php
  // buat koneksi dengan database mysql
  $dbhost = "localhost";
  $dbuser = "root";
  $dbpass = "";
  $link   = mysqli_connect($dbhost,$dbuser,$dbpass);

  //periksa koneksi, tampilkan pesan kesalahan jika gagal
  if(!$link){
    die ("Koneksi dengan database gagal: ".mysqli_connect_errno().
         " - ".mysqli_connect_error());
  }

  //buat database inventory jika belum ada
  $query = "CREATE DATABASE IF NOT EXISTS inventory";
  $result = mysqli_query($link, $query);

  if(!$result){
    die ("Query Error: ".mysqli_errno($link).
         " - ".mysqli_error($link));
  }
  else {
    echo "Database <b>'inventory'</b> berhasil dibuat... <br>";
  }

  //pilih database inventory
  $result = mysqli_select_db($link, "inventory");

  if(!$result){
    die ("Query Error: ".mysqli_errno($link).
         " - ".mysqli_error($link));
  }
  else {
    echo "Database <b>'inventory'</b> berhasil dipilih... <br>";
  }

  // cek apakah tabel barang sudah ada. jika ada, hapus tabel
  $query = "DROP TABLE IF EXISTS barang";
  $hasil_query = mysqli_query($link, $query);

  if(!$hasil_query){
    die ("Query Error: ".mysqli_errno($link).
         " - ".mysqli_error($link));
  }
  else {
    echo "Tabel <b>'barang'</b> berhasil dihapus... <br>";
  }

  // buat query untuk CREATE tabel barang
  $query  = "CREATE TABLE barang (id_barang INT(10), kode_barang VARCHAR(20), ";
  $query .= "nama_barang VARCHAR(50), tanggal_pembelian DATE, jumlah_barang INT(10), ";
  $query .= "satuan_barang VARCHAR(20), harga_beli INT(20), ";
  $query .= "status_barang VARCHAR(20), PRIMARY KEY(id_barang))";

  $hasil_query = mysqli_query($link, $query);

  if(!$hasil_query){
      die ("Query Error: ".mysqli_errno($link).
           " - ".mysqli_error($link));
  }
  else {
    echo "Tabel <b>'barang'</b> berhasil dibuat... <br>";
  }

  // buat query untuk INSERT data ke tabel barang
  $query  = "INSERT INTO barang VALUES ";
  $query .= "('1', 'a', 'Monitor ASUS', '2022-04-09', '1', ";
  $query .= "'Unit', ' 6056489', 'Available'), ";
  $query .= "('2', 'b', 'Samsung Galaxy A52', '2021-09-14', '4', ";
  $query .= "'Pcs', ' 5399000', 'Available'), ";
  $query .= "('3', 'c', 'Lenovo Flex 5', '2021-04-05', '1', ";
  $query .= "'Pcs', '19796819', 'Available'), ";
  $query .= "('4', 'd', 'CPU Rakitan', '2022-05-06','1', ";
  $query .= "'Pcs', '3785000', 'Available'), ";
  $query .= "('5', 'e', 'Kabel Printer', '2021-03-17', '2', ";
  $query .= "'Meter',' 30000', 'Not Available')";

  $hasil_query = mysqli_query($link, $query);

  if(!$hasil_query){
      die ("Query Error: ".mysqli_errno($link).
           " - ".mysqli_error($link));
  }
  else {
    echo "Tabel <b>'barang'</b> berhasil diisi... <br>";
  }

  // tutup koneksi dengan database mysql
  mysqli_close($link);
?>
