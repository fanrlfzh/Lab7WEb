# Lab7WEb

#Php dasar
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>PHP Dasar</title>
</head>
<body>
<h1>Belajar PHP Dasar</h1>
<?php
echo "Hello World";
?>
</body>
</html>
![WhatsApp Image 2024-11-19 at 08 28 39](https://github.com/user-attachments/assets/46cd2b9e-b970-4b47-bba6-2464caaae9c8)

#Variable php
<?php
$nim = "0411500400";
$nama = 'Abdullah';
echo "NIM : " . $nim . "<br>";
echo "Nama : $nama";
?>
![Screenshot (513)(1)](https://github.com/user-attachments/assets/6f9a9ce9-b23d-4298-8231-0652b33ddf5c)

#Predefine php
<?php
echo 'Selamat Datang ' . $_GET['nama'];
?>
![WhatsApp Image 2024-11-19 at 08 45 24](https://github.com/user-attachments/assets/1a3f8415-7782-45fa-84cf-8421275bd5b4)

#Membuat form input
<!DOCTYPE html>
<html lang="en">
<head>
      <meta charset="UTF-8">
      <title>PHP Dasar</title>
</head>
<body>
      <h2>Form Input</h2>
      <form method="post">
      <label>Nama: </label>
      <input type="text" name="nama">
      <input type="submit" value="Kirim">
    </form>
    <?php
    echo 'Selamat Datang ' . $_GET['nama'];
    ?>
</body>
</html>
![WhatsApp Image 2024-11-19 at 08 38 49](https://github.com/user-attachments/assets/b9a23f12-d716-422b-92b4-82a3b0b5973c)

#Operator
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji*$pajak);
echo "Gaji sebelum pajak = Rp. $gaji <br>";
echo "Gaji yang dibawa pulang = Rp. $thp";
?>
![WhatsApp Image 2024-11-19 at 08 36 54](https://github.com/user-attachments/assets/b9a0639a-bcd3-4dac-86c2-e3a5cfa7e805)

#Kondisi if
<?php
$nama_hari = date("l");
if ($nama_hari == "Sunday") {
echo "Minggu";
} elseif ($nama_hari == "Monday") {
echo "Senin";
} else {
echo "Selasa";
}
?>
![WhatsApp Image 2024-11-19 at 08 38 14](https://github.com/user-attachments/assets/7cb5ddb3-24aa-47c2-989f-8c200511dacb)

#Kondisi Switch
<?php
$nama_hari = date("l");
switch ($nama_hari) {
    case "Sunday":
        echo "Minggu";
        break;
    case "Monday":
        echo "Senin";
        break;
    case "Tuesday":
        echo "Selasa";
        break;
    default:
        echo "Sabtu";
}
?>
![WhatsApp Image 2024-11-19 at 08 37 48](https://github.com/user-attachments/assets/084f37e4-5422-4cb2-96b0-b8ec99ad218e)

#Perulangan for
<?php
echo "Perulangan 1 sampai 10 <br />";
for ($i=1; $i<=10; $i++) {
echo "Perulangan ke: " . $i . '<br />';
}
echo "Perulangan Menurun dari 10 ke 1 <br />";
for ($i=10; $i>=1; $i--) {
echo "Perulangan ke: " . $i . '<br />';
}
?>
![WhatsApp Image 2024-11-19 at 08 35 50](https://github.com/user-attachments/assets/c6050112-f7dd-42b5-abb6-44a5398b7a2e)

#Peulangan while
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
while ($i<=10) {
echo "Perulangan ke: " . $i . '<br />';
$i++;
}
?>
![WhatsApp Image 2024-11-19 at 08 35 08](https://github.com/user-attachments/assets/186d50d4-2147-419b-b582-3374d2d11f11)

#Perulangan dowhile
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
do {
echo "Perulangan ke: " . $i . '<br />';
$i++;
} while ($i<=10);
?>
![WhatsApp Image 2024-11-19 at 08 36 24](https://github.com/user-attachments/assets/14631b1f-4e95-4912-a6d2-6bfc817e9cab)


#Pertanyaan dan Tugas
Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan
nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung
umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang
berbeda-beda sesuai pilihan pekerjaan.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Form Input</title>
</head>
<body>
    <h2>Form Input</h2>
    <form method="post">
        <label>Nama: </label><input type="text" name="nama"><br>
        <label>Tanggal Lahir: </label><input type="date" name="tanggal_lahir"><br>
        <label>Pekerjaan: </label>
        <select name="pekerjaan">
            <option value="developer">Developer</option>
            <option value="designer">Designer</option>
            <option value="manager">Manager</option>
        </select><br>
        <input type="submit" value="Kirim">
    </form>

    <?php
    if ($_SERVER['REQUEST_METHOD'] == 'POST') {
        $nama = $_POST['nama'];
        $tanggal_lahir = $_POST['tanggal_lahir'];
        $pekerjaan = $_POST['pekerjaan'];

        
        $tanggal_lahir = new DateTime($tanggal_lahir);
        $sekarang = new DateTime();
        $umur = $sekarang->diff($tanggal_lahir)->y;

        
        $gaji = 0;
        if ($pekerjaan == "developer") {
            $gaji = 8000000;
        } elseif ($pekerjaan == "designer") {
            $gaji = 6000000;
        } elseif ($pekerjaan == "manager") {
            $gaji = 10000000;
        }

        
        echo "<h3>Hasil Input</h3>";
        echo "Nama: $nama<br>";
        echo "Tanggal Lahir: " . $tanggal_lahir->format('d-m-Y') . "<br>";
        echo "Umur: $umur tahun<br>";
        echo "Pekerjaan: " . ucfirst($pekerjaan) . "<br>";
        echo "Gaji: Rp. " . number_format($gaji, 0, ',', '.') . "<br>";
    }
    ?>
</body>
</html>
![WhatsApp Image 2024-11-19 at 08 33 23](https://github.com/user-attachments/assets/b2b8a555-8e9c-41b8-b2a4-f0987709b57f)










