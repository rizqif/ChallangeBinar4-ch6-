# binar-challengech6

### Step-by-step to run the app

1. Clone repository.
2. jalankan terminal : `npm install` untuk install semua, membutuhkan package yang ada di**_packages.json_**.
3. buat database di pgadmin
4. buat **_.env_** environment file based on **_.env.example_**. pastikan nama database benar
5. Migrate database tables dan populate seeders.
6. Run **Server** di terminal menggunakan : `npm run start` or `yarn start`.

### STEP-BY-STEP Test middlewares & controllers (untuk contoh gunakan port 3000)

1. Go to index page, enter `localhost:3000/` or `localhost:3000/index` or `localhost:3000/home`. hasilnya akan sama , index page.
2. coba akses ke `localhost:3000/profile` atau play the game dengan menekan **PLAY NOW** button. server akan mengarahkan ke login page (`localhost:3000/auth/login`).
3. jika belum terdaftar maka tekan **SIGN UP** button (`localhost:3000/auth/signup`) di atas sebelah kanan
4. Test basic validasi. kamu dapat menemukan requirement untuk mengisi form didalam middlewares > validation folder. jika semua conditions tidak bertemu, server akan error.
5. jika registrasi sukses, check new user entry di db. password akan diberikan oleh bcrypt.
6. coba untuk login dengan registered account.
7. setelah login, kamu tidak dapat mengakses `localhost:3000/auth/signup` atau `localhost:3000/auth/login`. coba untuk test lewat browser URL
8. saat kamu login, server akan memberikanmu cookies dan session akan expires dalam 2 jam. cookies membutuhkan authenticate, jika cookies espired maka user perlu login kembali
9. Click **LOGGED IN AS username** . ini adalah bagian edit profile dimana kamu dapat mengganti password dan profile.
10. sekarang coba untuk edit profile pertama klik **EDIT PROFILE** button. jika sudah , klik **SUBMIT** button.
11. sekarang coba untuk merubah password dengan **CHANGE PASSWORD** .
12. sekarang kembali ke index page atau atau langsung akses ke game dengan `localhost:3000/rockpaperscissor`.
13. setelah main game, silahkan cek **SEE GAME HISTORY** button untuk melihat history permainan.
14. jika sudah silahkan kembali ke profile dan hapus profile dengan menekan **DELETE ALL USER DATA** button.

### Packages :

- Babel.js : Transcompiler
- Express : Node.js Framework
- dotenv : Environment
- EJS : View Engine
- ESLint : Linter - airbnb based
- Morgan : Logger (see the log on node console)
- Sequelize : ORM for PostgreSQL
- bcrypt : Password hashing
- Joi : Form Validation
- express-session : Authentication (Session & Cookies)
- method-override : Override POST method in form
- Helmet : Secure HTTP headers

### Folders :

- public -> Serve static files (css, images, js, etc).
- configs -> config file(s).
- controllers -> controllers for user interactions.
- middlewares -> express-session authentication & joi validation.
- migrations -> migration for db tables.
- models -> model mapping.
- routes -> web routes.
- seeders -> populate dummy data into migrated db tables.
- views -> act as views in MVC pattern using EJS.
