# Pertemuan Keempat

## Daftar Isi
- [CRUD](#crud)
  - [Create](#create)
  - [Read](#read)
  - [Update](#update)
  - [Delete](#delete)
- [Exception Handling](#exception-handling)
  - [Try Catch](#try-catch)
  - [Throws](#throws)

---

## CRUD
CRUD adalah singkatan dari empat operasi dasar dalam manajemen data, yaitu:
- **Create**: Membuat atau menambah data baru.
- **Read**: Membaca data yang sudah ada.
- **Update**: Mengubah data yang sudah ada.
- **Delete**: Menghapus data yang sudah ada.

---

## Exception Handling
Exception handling adalah proses merespons terjadinya pengecualian yang memerlukan pemrosesan khusus selama eksekusi program. 

### Try Catch
Try-catch digunakan untuk menangani error yang terjadi dalam blok kode tertentu. Jika terjadi error di dalam blok `try`, kontrol akan langsung dialihkan ke blok `catch` untuk menangani error tersebut.

**Contoh Kode Try Catch:**
```java
public class TryCatch {
    public void aksesArrayDenganTryCatch() {
        int[] angka = {1, 2, 3, 4};
        try {
            System.out.println(angka[7]); // Akses indeks di luar batas array
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Indeks array melebihi batas: " + e.getMessage());
        }
    }

    public static void main(String[] args) {
        TryCatch contoh = new TryCatch();
        contoh.aksesArrayDenganTryCatch();
    }
}

```
### Throws
Throws merupakan salah satu cara untuk meng-handle kemunculan exception selain
menggunakan try-catch. Dengan menggunakan throws, exception yang muncul pada
suatu blok kode dalam suatu method akan dilemparkan lagi menuju kode yang
memanggil method tersebut. Dengan demikian, biarkan yang menggunakan method
tersebut yang melakukan handle lebih lanjut dari exception yang telah muncul.

**Contoh Kode Throws:**
```java
public class Throws {
    
    public int aksesArray(int[] arr, int indeks) throws ArrayIndexOutOfBoundsException {
        if (indeks < 0 || indeks >= arr.length) {
            throw new ArrayIndexOutOfBoundsException("Indeks di luar batas: " + indeks);
        }
        return arr[indeks];
    }

    public static void main(String[] args) {
        Throws contoh = new Throws();
        int[] array = {1, 2, 3, 4, 5};

        try {
            int hasil = contoh.aksesArray(array, 10); // Mengakses indeks yang tidak valid
            System.out.println(hasil);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Terjadi kesalahan: " + e.getMessage());
        }
    }
}


