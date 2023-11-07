# Tugas POO Pertemuan 5 dan 6
## **Repositori ini dibuat untuk memenuhi tugas pertemuan 5 dan 6**  
**""Karena Link pada pertemuan 5 tidak tertaut karena error""**  
Nama           : Dinda Aurelia Zalsabella  
Nim            : 312210045  
Kelas          : TI.22.B1  
Mata Kuliah    : Pemrograman Orientasi Objek  
Dosen Pengampu : Wiyanto, S.Kom., M.Kom.  

**Tugas 5 :**  
**latihan 1 : Mendeklarasikan Class Person, dengan atribut Nama, Jenis Kelamin, Umur dan lengkapi dengan acces modifier.**  
**latihan 2: Buatlah dua buah objek dari class person bernama Anton dan Riko dan panggil method setter dan getter.**  

Source Code Pada C# :  
latihan 1 (Class Person)  
*Program.cs  
``` c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using OOP5;

namespace OOP6
{
    class Program
    {
        public static void Main(string[] args)
        {
            Mahasiswa mhs = new Mahasiswa();
            Console.Write("Masukkan Nama : ");
            mhs.Nama = Console.ReadLine();
            Console.Write("Masukkan Nim : ");
            mhs.Nim = Convert.ToInt32(Console.ReadLine());
            Console.Write("Masukkan Jenis Kelamin : ");
            mhs.JenisKelamin = Console.ReadLine();
            Console.Write("Masukkan Umur : ");
            mhs.Umur = Console.ReadLine();
            Console.WriteLine();
            Console.WriteLine("Nama : " + mhs.Nama);
            Console.WriteLine("NIM : " + mhs.Nim);
            Console.WriteLine("Jenis Kelamin : " + mhs.JenisKelamin);
            Console.WriteLine("Umur : " + mhs.Umur);
            Console.ReadKey(true);
        }
    }

}
```
Penjelasan :  
1. Pada Class Program, kita memiliki 4 pertanyaan diantaranya:
   * Nama Mahasiswa
   * Nim Mahasiswa
   * Jenis Kelamin Mahasiswa
   * Umur Mahasiswa  
Saat kita telah mengisi petanyaan tersebut kita berarti kita telah berhasil mendeklarasikan class person dengan acces modifier.

 Source Code Pada C# :  
latihan 2 (Class Person Setter dan Getter)  
*Program.cs
```using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace POO5
{   
    class Person
    {        
        protected string nama, jenisKelamin;
        protected int umur;

        public void setNama(string nama)
        {
            this.nama = nama;
        }
        public string getNama()
        {
            return this.nama;
        }

        public void setJenisKelamin(string jenisKelamin)
        {
            this.jenisKelamin = jenisKelamin;
        }
        public string getJenisKelamin()
        {
            return this.jenisKelamin;
        }
        public void setUmur(int umur)
        {
            this.umur = umur;
        }
        public int getUmur()
        {
            return this.umur;
        }
    }
    class akunBank
    {
        public int saldo = 1000000;

        public void cekSaldo()
        {
            Console.WriteLine("Saldo Saat ini: Rp. " + this.saldo);
        }
        public void simpanUang()
        {
            Console.Write("Simpan Uang : Rp. ");
            this.saldo += Convert.ToInt32(Console.ReadLine());
            this.cekSaldo();
        }
        public void ambilUang()
        {
            Console.Write("Ambil Uang : Rp. ");
            this.saldo -= Convert.ToInt32(Console.ReadLine());
            this.cekSaldo();
        }

    }
    class Program
    {   
        public static void Latihan1()
        {
            Person Anton = new Person();
            Anton.setNama("Anton");
            Anton.setJenisKelamin("Laki-Laki");
            Anton.setUmur(28);
            Console.WriteLine("Anton adalah seorang " + Anton.getJenisKelamin() + ", berusia "+ Anton.getUmur() + " tahun");

            Person Rika = new Person();
            Rika.setNama("Rika");
            Rika.setJenisKelamin("Perempuan");
            Rika.setUmur(20);
            Console.WriteLine("dan Rika adalah seorang " + Rika.getJenisKelamin() + ", berusia "+ Rika.getUmur() + " tahun");

        }

        public static void Latihan2()
        {
            akunBank akun = new akunBank();
            Console.WriteLine("Selamat Datang di bank BNA");
            akun.cekSaldo();
            Console.WriteLine();
            akun.simpanUang();
            Console.WriteLine();
            akun.ambilUang();
        }
        static void Main(string[] args)
        {
            Latihan1();
            Console.WriteLine("\n");
            Latihan2();
            Console.Write("Press any key to continue..");
            Console.ReadKey();
        }
    }
}
```
Penjelasan :  
**Latihan 1**
1. Pada Class Setter dan Getter, kita memiliki beberapa pernyataan diantaranya:
   * Terdapat keterangan Nama,Jenis Kelamin dan umur Anton
   * Terdapat keterangan Nama,Jenis Kelamin dan umur Rika
  
**Latihan 2**
1. Pada Class Akun Bank dengan menggunakan instance method kita dapat melakukan diantaranya :
   * Kita dapat melihat jumlah uang pada tabungan kita
   * Kita juga dapat menginputkan Tabungan kita kedalam Bank BNA
   * Dalam Bank BNA kita dapat mengambil dan menyimpan uang dan melihat sisa tabungan kita.
  
**Tugas 6 :**  
**Membuat class Mahasiswa dengan setter dan getter, serta mengimplementasikan code c# diagram class Pegawai,Proggramer, dan Manager**  

Source Code pada c#   
Tugas 1 (Class Mahasiswa, setter dan getter)  
```using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace POO6
{
    public class Pegawai
    {
        private string _nama;
        private double _gajiPokok;

        public void setNama(string ParamNama)
        {
            _nama = ParamNama;
        }
        public string getNama()
        {
            return _nama;
        }

        public void setGajiPokok(double paramGaji)
        {
            _gajiPokok = paramGaji;
        }

        public double getGajiPokok()
        {
            return _gajiPokok;
        }

        public virtual void cetakInfo()
        {
            Console.WriteLine("Pegawai : " + getNama());
            Console.WriteLine("Gaji Pokok : " + getGajiPokok());
        }
    }

    public class Manager : Pegawai {
        private double _tunjangan;

        public void setTunjangan(double paramTunjangan){
            _tunjangan = paramTunjangan;
        }

        public double getTunjangan(){
            return _tunjangan;
        }

        public void cetakTunjangan(){
            Console.WriteLine("Tunjangan Anda : " + getTunjangan());
        }
        public virtual void cetakInfo(){
        Console.WriteLine("Pegawai : " + getNama());
        Console.WriteLine("Posisi Anda : Manager" );
        Console.WriteLine("Gaji Pokok Anda : " + getGajiPokok());
        }
    }

    public class Programmer : Pegawai{
        private double _bonus;

        public void setBonus(double paramBonus){
            _bonus = paramBonus;
        }

        public double getBonus(){
            return _bonus;
        }

        public void cetakBonus(){
            Console.WriteLine("Bonus Anda : " + getBonus());
        }

        public virtual void cetakInfo(){
            Console.WriteLine("Pegawai : " + getNama());
            Console.WriteLine("Posisi : Programmer" );
            Console.WriteLine("Gaji Pokok Anda : " + getGajiPokok());
        }
    }

    class Program{
        static void Main(string[] args){
            Console.WriteLine("========Pegawai Class========");
            Pegawai pegawai = new Pegawai();
            pegawai.setNama("Bella Pegawai");
            pegawai.setGajiPokok(8000000);
            pegawai.cetakInfo();

            Console.WriteLine("========Manager Class========");
            Manager manager = new Manager();
            manager.setNama("Bella Manager");
            manager.setGajiPokok(15000000);
            manager.setTunjangan(10000000);
            manager.cetakInfo();
            manager.cetakTunjangan();

            Console.WriteLine("========Programmer Class========");
            Programmer programmer = new Programmer();
            programmer.setNama("Bella Programmer");
            programmer.setGajiPokok(12000000);
            programmer.setBonus(1500000);
            programmer.cetakInfo();
            programmer.cetakBonus();
        }
    }
}
```
Penjelasan :  
**Tugas 1**
1. Pada Class Setter dan Getter, kita dapat melihat beberapa pernyataan diantaranya :
   * Nama Pegawai, Nama Programmer, Nama Manager
   * Kita dapat melihat gaji yang berbeda diantara masing-masing jabatan
   * Kita uga dapat mengetahui jumlah bonus serta tunjangan yang di dapatkan antar masing-masing jabatan.
