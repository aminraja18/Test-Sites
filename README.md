# Sick
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Promosi Kedai</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      line-height: 1.6;
      color: #333;
      max-width: 1000px;
      margin: 0 auto;
      padding: 20px;
      background-color: #f9f9f9;
    }
    header {
      background-color: #2c3e50;
      color: white;
      padding: 20px;
      text-align: center;
      border-radius: 8px;
      margin-bottom: 30px;
    }
    h1 {
      margin: 0;
      font-size: 2.2em;
    }
    .container {
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
    }
    .main-content {
      flex: 2;
      min-width: 300px;
      background: white;
      padding: 25px;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }
    .sidebar {
      flex: 1;
      min-width: 250px;
    }
    .info-box {
      background: white;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }
    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
      gap: 10px;
      margin-top: 20px;
    }
    .gallery img {
      width: 100%;
      height: 150px;
      object-fit: cover;
      border-radius: 5px;
      transition: transform 0.3s;
    }
    .gallery img:hover {
      transform: scale(1.05);
    }
    .btn {
      display: inline-block;
      background-color: #e74c3c;
      color: white;
      padding: 12px 25px;
      text-decoration: none;
      border-radius: 5px;
      font-weight: bold;
      margin-top: 15px;
      transition: background-color 0.3s;
    }
    .btn:hover {
      background-color: #c0392b;
    }
    .highlight {
      background-color: #fdebd0;
      padding: 15px;
      border-left: 4px solid #e67e22;
      margin: 20px 0;
      border-radius: 0 5px 5px 0;
    }
    .testimonial {
      background: #f8f9fa;
      padding: 15px;
      border-radius: 5px;
      margin-bottom: 15px;
      border-left: 3px solid #2c3e50;
    }
    .testimonial-author {
      font-weight: bold;
      text-align: right;
      font-style: italic;
    }
    footer {
      text-align: center;
      margin-top: 40px;
      padding: 20px;
      background-color: #2c3e50;
      color: white;
      border-radius: 8px;
    }
    @media (max-width: 768px) {
      .container {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1 id="shop-name">Nama Kedai Anda</h1>
    <p id="shop-tagline">Tagline atau slogan kedai Anda</p>
  </header>

  <div class="container">
    <main class="main-content">
      <section>
        <h2>Tentang Kami</h2>
        <p id="about-text">Deskripsi tentang kedai Anda, produk/jasa yang ditawarkan, dan nilai unik yang Anda berikan kepada pelanggan.</p>
        
        <div class="highlight">
          <h3>Promosi Spesial!</h3>
          <p id="promo-text">Tuliskan promosi atau penawaran khusus Anda di sini. Buat menarik untuk menarik minat pelanggan.</p>
        </div>
      </section>

      <section>
        <h2>Produk/Jasa Unggulan</h2>
        <div id="featured-products">
          <!-- Produk akan ditambahkan secara dinamis -->
        </div>
      </section>

      <section>
        <h2>Testimoni Pelanggan</h2>
        <div id="testimonials">
          <!-- Testimoni akan ditambahkan secara dinamis -->
        </div>
      </section>
    </main>

    <aside class="sidebar">
      <div class="info-box">
        <h3>Info Kontak</h3>
        <p><strong>Alamat:</strong> <span id="shop-address">Alamat kedai Anda</span></p>
        <p><strong>Telepon:</strong> <span id="shop-phone">Nomor telepon</span></p>
        <p><strong>Email:</strong> <span id="shop-email">Alamat email</span></p>
        <p><strong>Jam Buka:</strong> <span id="shop-hours">Jam operasional</span></p>
        
        <a href="#" class="btn" id="contact-btn">Hubungi Kami</a>
      </div>

      <div class="info-box">
        <h3>Galeri</h3>
        <div class="gallery" id="shop-gallery">
          <!-- Gambar akan ditambahkan secara dinamis -->
        </div>
      </div>

      <div class="info-box">
        <h3>Lokasi</h3>
        <div id="shop-map" style="height: 200px; background-color: #eee; display: flex; align-items: center; justify-content: center; border-radius: 5px;">
          [Peta lokasi akan ditampilkan di sini]
        </div>
      </div>
    </aside>
  </div>

  <footer>
    <p>&copy; <span id="current-year"></span> <span id="footer-shop-name">Nama Kedai Anda</span>. Semua Hak Cipta Dilindungi.</p>
    <div id="social-media">
      <!-- Link media sosial akan ditambahkan di sini -->
    </div>
  </footer>

  <script>
    // Data kedai - akan diisi melalui prompt
    const shopData = {
      name: "",
      tagline: "",
      about: "",
      promo: "",
      address: "",
      phone: "",
      email: "",
      hours: "",
      products: [],
      testimonials: [],
      gallery: [],
      socialMedia: []
    };

    // Fungsi untuk mengisi data kedai
    function collectShopData() {
      shopData.name = prompt("Masukkan nama kedai Anda:", "Contoh: Kedai Serba Ada");
      shopData.tagline = prompt("Masukkan tagline/slogan kedai Anda:", "Contoh: Kualitas Terbaik, Harga Terjangkau");
      shopData.about = prompt("Deskripsikan tentang kedai Anda (minimal 2 kalimat):", "Kedai kami menyediakan berbagai kebutuhan sehari-hari dengan kualitas terbaik. Kami berkomitmen untuk memberikan pelayanan terbaik kepada pelanggan.");
      shopData.promo = prompt("Masukkan teks promosi spesial Anda:", "Diskon 20% untuk pembelian pertama! Berlaku hingga 30 November 2023.");
      shopData.address = prompt("Masukkan alamat lengkap kedai:", "Jl. Contoh No. 123, Kota Anda");
      shopData.phone = prompt("Masukkan nomor telepon yang bisa dihubungi:", "+62 812-3456-7890");
      shopData.email = prompt("Masukkan alamat email:", "kontak@kedaianda.com");
      shopData.hours = prompt("Masukkan jam operasional:", "Senin-Minggu, 08:00 - 21:00 WIB");
      
      // Produk unggulan
      let addMoreProducts = true;
      while(addMoreProducts) {
        const productName = prompt("Masukkan nama produk/jasa unggulan:", "Contoh: Paket Hemat Keluarga");
        const productDesc = prompt("Deskripsikan produk/jasa ini:", "Paket lengkap untuk kebutuhan keluarga selama seminggu dengan harga spesial");
        
        if(productName && productDesc) {
          shopData.products.push({
            name: productName,
            description: productDesc
          });
        }
        
        addMoreProducts = confirm("Tambahkan produk/jasa unggulan lainnya?");
      }
      
      // Testimoni
      let addMoreTestimonials = confirm("Tambahkan testimoni pelanggan?");
      while(addMoreTestimonials) {
        const testimonialText = prompt("Masukkan testimoni pelanggan:", "Pelayanan sangat memuaskan dan produknya berkualitas!");
        const testimonialAuthor = prompt("Masukkan nama pemberi testimoni:", "Budi Santoso");
        
        if(testimonialText && testimonialAuthor) {
          shopData.testimonials.push({
            text: testimonialText,
            author: testimonialAuthor
          });
        }
        
        addMoreTestimonials = confirm("Tambahkan testimoni pelanggan lainnya?");
      }
      
      // Media sosial
      let addMoreSocialMedia = confirm("Tambahkan media sosial kedai Anda?");
      while(addMoreSocialMedia) {
        const platform = prompt("Masukkan nama platform (contoh: Facebook, Instagram):", "Instagram");
        const url = prompt("Masukkan URL/link:", "https://instagram.com/kedaianda");
        
        if(platform && url) {
          shopData.socialMedia.push({
            platform: platform,
            url: url
          });
        }
        
        addMoreSocialMedia = confirm("Tambahkan media sosial lainnya?");
      }
      
      // Gambar galeri
      alert("Untuk galeri gambar, Anda perlu menambahkan URL gambar nanti secara manual ke dalam kode HTML. Kami akan menyediakan tempat untuk 4 gambar.");
      
      updatePageContent();
    }

    // Fungsi untuk mengupdate halaman dengan data yang telah dikumpulkan
    function updatePageContent() {
      document.getElementById('shop-name').textContent = shopData.name;
      document.getElementById('shop-tagline').textContent = shopData.tagline;
      document.getElementById('about-text').textContent = shopData.about;
      document.getElementById('promo-text').textContent = shopData.promo;
      document.getElementById('shop-address').textContent = shopData.address;
      document.getElementById('shop-phone').textContent = shopData.phone;
      document.getElementById('shop-email').textContent = shopData.email;
      document.getElementById('shop-hours').textContent = shopData.hours;
      document.getElementById('footer-shop-name').textContent = shopData.name;
      
      // Tahun sekarang di footer
      document.getElementById('current-year').textContent = new Date().getFullYear();
      
      // Produk unggulan
      const productsContainer = document.getElementById('featured-products');
      shopData.products.forEach(product => {
        const productHTML = `
          <div class="info-box">
            <h4>${product.name}</h4>
            <p>${product.description}</p>
          </div>
        `;
        productsContainer.innerHTML += productHTML;
      });
      
      // Testimoni
      const testimonialsContainer = document.getElementById('testimonials');
      shopData.testimonials.forEach(testimonial => {
        const testimonialHTML = `
          <div class="testimonial">
            <p>"${testimonial.text}"</p>
            <p class="testimonial-author">- ${testimonial.author}</p>
          </div>
        `;
        testimonialsContainer.innerHTML += testimonialHTML;
      });
      
      // Media sosial
      const socialMediaContainer = document.getElementById('social-media');
      shopData.socialMedia.forEach(social => {
        const socialHTML = `
          <a href="${social.url}" target="_blank" style="color: white; margin: 0 10px;">${social.platform}</a>
        `;
        socialMediaContainer.innerHTML += socialHTML;
      });
      
      // Link tombol hubungi kami
      document.getElementById('contact-btn').href = `mailto:${shopData.email}?subject=Kontak dari ${shopData.name}`;
    }

    // Mulai mengumpulkan data saat halaman dimuat
    window.onload = function() {
      if(confirm("Selamat datang di generator halaman promosi kedai! Mari kita buat halaman web untuk kedai Anda. Klik OK untuk mulai.")) {
        collectShopData();
      }
    };
  </script>
</body>
</html>
