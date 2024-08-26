# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini
1. DevOps merupakan penggabungan proses development dari sebuah aplikasi dengan operation. Devops memiliki kunci koordinasi antar tim, dimana koordinastersebut menggunakan tools seperti Gitub, GitLab, dan semacamnya.

2. Infrastruktur sendiri mencakup segala hal yang diperlukan untuk membangun dan menjalankan aplikasi

3. Merupakan salah satu sistem komputer yang menyediakan jenis layanan tertentu. Contohnya web server, database server, file server dan semacamnya

4. Untuk keamanan, Memudahkan pengembang melakukan Pengujian, serta memudahkan pengembang mengakses data secara efisien

5. Kontainer dan virtualisasi merupakan teknologi deployment, dimana masing mempunyai kelebihan dan kekurangan sendiri. Contoh Virtualisasi memiliki ukuran yg lebih besar dan container memiliki ukuran yg lbih ringan

6. Container dapat dengan cepat di deploy, diatur dan dimanage sesuai kebutuhan.

7. Orchestration Container System adalah proses mengotomatiskan pengelolaan kontainer sehingga memudahkan pengembang menerapkan pada aplikasi skala besar.


## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

