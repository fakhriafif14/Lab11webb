# 📘 PHP Framework (CodeIgniter 4) – Praktikum 4–6

**Mata Kuliah:** Pemrograman Web 2

| Field     | Data                          |
| --------- | ----------------------------- |
| **NIM**   | 312310632                     |
| **Nama**  | Fakhri Afif                   |
| **Kelas** | TI.23.A6                      |
| **Dosen** | Agung Nugroho, S.Kom., M.Kom. |

---

## ✅ Praktikum 4 – Database Seeder & Auth Filter

### 🔹 Membuat Tabel `user`

```sql
CREATE TABLE user (
 id INT(11) auto_increment,
 username VARCHAR(200) NOT NULL,
 useremail VARCHAR(200),
 userpassword VARCHAR(200),
 PRIMARY KEY(id)
);
```

### 🔹 Membuat Model `User`

![User Model](ss/ssmodel.png)

### 🔹 Seeder untuk Data Dummy Login

1. **Jalankan CLI**:
   ![User Seeder CLI](ss/userseeder.png)

2. **Edit file** `app/Database/Seeds/UserSeeder.php`:
   ![User Seeder Code](ss/seeds.png)

3. **Jalankan Seeder**:
   ![Save Seeds](ss/saveseeds.png)

---

### 🔹 Uji Coba Login

* Akses: [http://localhost:8080/user/login](http://localhost:8080/user/login)
* Tampilan:
  ![Login Page](ss/login.png)

---

### 🔹 Menambahkan Auth Filter

1. Buat file `Auth.php` di `app/Filters/`
   ![Auth Filter](ss/auth.png)

2. Daftarkan filter di `app/Config/Filters.php`:

   ```php
   'auth' => App\Filters\Auth::class,
   ```

   ![Filters Config](ss/filters.png)

3. Atur route yang ingin dilindungi di `app/Config/Routes.php`
   ![Routes Setup](ss/routes.png)

---

### 🔹 Pengujian Akses Admin (Tanpa Login)

* Akses: [http://localhost:8080/admin/artikel](http://localhost:8080/admin/artikel)
* Redirect ke login jika belum autentikasi:
  ![Admin Artikel](ss/adminartikel.png)

---

## ✅ Praktikum 5 – Pagination & Pencarian Artikel

### 🔹 Menambahkan Pagination

1. Modifikasi `admin_index()` di `App/Controller/Artikel`
   ![Controller Pagination](ss/ssp5_2.png)

2. Tambahkan form pencarian di `Views/artikel/admin_index.php`
   ![Form Search](ss/ssp5_3.png)

3. Tampilkan link pagination di bawah tabel
   ![Pagination Links](ss/ssp5_4.png)

---

## ✅ Praktikum 6 – Unggah Gambar pada Tambah Artikel

### 🔹 Modifikasi Controller

* Ubah method `add()` di `Artikel.php` agar mendukung upload gambar:
  ![Upload Controller](ss/ssuploadcontroller.png)

### 🔹 Tambah Elemen Input di Form Tambah Artikel

* File: `views/artikel/form_add.php`
  ![Upload Form](ss/ssuploadform.png)

### 🔹 Pengujian Fitur Upload

* Uji coba tambah artikel + upload gambar melalui form:
  ![Upload Result](ss/ssuploadresult.png)

---

Selesai. Terima kasih 🙌
Jika ada kesalahan atau pembaruan, silakan lakukan pull request atau issue.

---

