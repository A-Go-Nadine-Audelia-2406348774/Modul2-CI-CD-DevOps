Nama = Go Nadine Audelia
NPM = 2406348774

REFLECTION MODULE 2

1. List the code quality issue(s) that you fixed during the exercise and explain your strategy on fixing them. 

Saya sempat mengalami isu peringatan keamanan kotlin:S6474 karena proyek menggunakan library eksternal tanpa verifikasi integritas, yang menyebabkan Security Hotspots pada SonarCloud. Awalnya cara saya membenarkan adalah dengan membuat verification-metadata.xml, tapi ternyata ada cara lain yang lebih praktis sehingga saya menghapus file verification-metadata.xml. Cara yang akhirnya saya pakai adalah pergi langsung ke web SonarCloud dan di bagian Security Hotspot saya ubah untuk menandainya menjadi Reviewed-Safe. Lebih baik pakai cara ini karena saya cukup yakin library yang saya gunakan itu terpercaya.
Saya juga sempat mengalami masalah kegagalan di unit test dan yang saya lakukan untuk membenarkan isu itu adalah dengan memperbaiki method yang menjadi penyebab masalah dan menambahkan unit test agar bisa mencapai 100% coverage.

2. Look at your CI/CD workflows (GitHub)/pipelines (GitLab). Do you think the current implementation has met the definition of Continuous Integration and Continuous Deployment? Explain the reasons (minimum 3 sentences)!
Menurut saya, implementasi saat ini udah memenuhi Continuous Integration karena setiap kali ada perubahan kode yang di-push ke repositori GitHub, GitHub actions langsung menjalankan proses build,  unit test, dan mengecek quality code melalui SonarCloud. Selain itu, implementasi juga telah memenuhi kriteria Continuous Deployment melalui integrasi dengan PaaS Koyeb yang menggunakan metode pull based approach. Setiap perubahan yang lolos tahap CI dan dimerge ke branch main akan otomatis dirilis ke lingkungan produksi.
