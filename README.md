# Lab10Web

| INDIRA ALINE      |   312010042       |
|-------------------|-------------------|
| TI.20.A.1         | PEMROGRAMAN WEB   |
| PERTEMUAN 11      | PRAKTIKUM 10      |

Dipertemuan ini akan mempelajari  **PHP OOP**

## LANGKAH - LANGKAH PRAKTIKUM

## 1). MENJALANKAN XAMPP SERVER
![xampp-server](img/mysqlserver.png)

**PENJELASAN**

Menjalankan xampp server.

## 2). BUAT FOLDER BARU DENGAN NAMA **lab10_php_oop**
![folder-lab10](img/newfolder.png)

**PENJELASAN**

Setelah itu jalankan dengan mengakses URL: http://localhost/Lab10Web/lab10_php_oop/

## 3). BUAT FILE BARU DENGAN NAMA **mobil.php**
![class](img/mobil.png)

**PENJELASAN**

Menggunakan **class** dan **pemanggilan class**

**code php**

```php
<?php
/**
* Program sederhana pendefinisian class dan pemanggilan class.
**/
class Mobil
{
    private $warna;
    private $merk;
    private $harga;
    public function __construct()
    {
        $this->warna = "Biru";
        $this->merk = "BMW";
        $this->harga = "10000000";
    }
    
    public function gantiWarna ($warnaBaru)
    {
        $this->warna = $warnaBaru;
    }
    public function tampilWarna ()
    {
        echo "Warna mobilnya : " . $this->warna; 
    }
}
// membuat objek mobil
$a = new Mobil();
$b = new Mobil();

// memanggil objek
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");
$a->tampilWarna();

// memanggil objek
echo "<br><b>Mobil kedua</b><br>";
$b->gantiWarna("Hijau");
$b->tampilWarna();
?>
```

## 4). BUAT FILE BARU DENGAN NAMA **form.php**

**code php**

```php
<?php
/**
* Nama Class: Form
* Deskripsi: CLass untuk membuat form inputan text sederhana
**/

class Form
{
    private $fields = array();
    private $action;
    private $submit = "Submit Form";
    private $jumField = 0;
    public function __construct($action, $submit)
    {
        $this->action = $action;
        $this->submit = $submit;
    }
    
    public function displayForm()
    {
        echo "<form action='".$this->action."' method='POST'>";
        echo '<table width="100%" border="0">';
        for ($j=0; $j<count($this->fields); $j++) {
            echo "<tr><td align='right'>".$this->fields[$j]['label']."</td>";
            echo "<td><input type='text' name='".$this->fields[$j]['name']."'></td></tr>";
        }
        echo "<tr><td colspan='2'>";
        echo "<input type='submit' value='".$this->submit."'></td></tr>";
        echo "</table>";
    }

    public function addField($name, $label)
    {
        $this->fields [$this->jumField]['name'] = $name;
        $this->fields [$this->jumField]['label'] = $label;
        $this->jumField ++;
    }
}
?>
```

## 5). BUAT FILE BARU DENGAN NAMA **form_input.php**
![form-input](img/form_input.png)

**PENJELASAN**

Membuat metode input dengan **include** untuk target halaman.

**code php**

```php
<?php
/**
* Program memanfaatkan Program 10.2 untuk membuat form inputan sederhana.
**/

include "form.php";

echo "<html><head><title>Mahasiswa</title></head><body>";
$form = new Form("","Input Form");
$form->addField("txtnim", " <b> Nim : </b> ");
$form->addField("txtnama", " <b> Nama : </b> ");
$form->addField("txtalamat", "<b> Alamat :</b>");
echo "<h3>Silahkan isi form berikut ini :</h3>";
$form->displayForm();
echo "</body></html>";
?>
```

--------------------------------------------------------------------------------------------------

## TERIMAKASIH
