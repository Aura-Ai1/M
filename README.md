<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MIZUYA — Japanese Lifestyle Cafe</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>
:root{
  --black:#0b0b0a;
  --cream:#eee9df;
  --muted:#9c988e;
  --line:rgba(238,233,223,.16);
  --orange:#c86f42;
}

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

html{
  scroll-behavior:smooth;
}

body{
  background:var(--black);
  color:var(--cream);
  font-family:"DM Sans",sans-serif;
  overflow-x:hidden;
}

body:before{
  content:"";
  position:fixed;
  inset:0;
  pointer-events:none;
  z-index:9999;
  opacity:.045;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.5'/%3E%3C/svg%3E");
}

a{
  color:inherit;
  text-decoration:none;
}

button{
  font:inherit;
}

.cursor{
  width:12px;
  height:12px;
  border:1px solid white;
  border-radius:50%;
  position:fixed;
  pointer-events:none;
  z-index:10000;
  transform:translate(-50%,-50%);
  transition:.12s ease;
  mix-blend-mode:difference;
}

.preloader{
  position:fixed;
  inset:0;
  z-index:9998;
  background:#0b0b0a;
  display:flex;
  align-items:center;
  justify-content:center;
  animation:loader 1.5s ease forwards;
}

.preloader span{
  font-family:"Cormorant Garamond";
  font-size:clamp(3rem,8vw,8rem);
  letter-spacing:.16em;
}

@keyframes loader{
  0%,65%{opacity:1}
  100%{opacity:0;visibility:hidden}
}

/* NAV */

nav{
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:88px;
  z-index:1000;
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0 5vw;
  mix-blend-mode:difference;
}

.logo{
  font-family:"Cormorant Garamond";
  font-size:31px;
  letter-spacing:.16em;
  font-weight:600;
}

.navlinks{
  display:flex;
  gap:35px;
  font-size:11px;
  letter-spacing:.18em;
  text-transform:uppercase;
}

.navlinks a{
  opacity:.75;
  transition:.3s;
}

.navlinks a:hover{
  opacity:1;
}

.navbtn{
  border:1px solid rgba(255,255,255,.6);
  padding:12px 20px;
  font-size:10px;
  letter-spacing:.16em;
  text-transform:uppercase;
}

/* HERO */

.hero{
  min-height:100svh;
  position:relative;
  display:flex;
  align-items:flex-end;
  padding:0 6vw 8vh;
  overflow:hidden;
}

.hero-media{
  position:absolute;
  inset:0;
  background:
  linear-gradient(180deg,rgba(0,0,0,.15),rgba(0,0,0,.75)),
  url("https://images.unsplash.com/photo-1579871494447-9811cf80d66c?auto=format&fit=crop&w=2200&q=90")
  center/cover;
  transform:scale(1.05);
  animation:heroZoom 10s ease-out forwards;
}

@keyframes heroZoom{
  to{transform:scale(1)}
}

.hero-content{
  position:relative;
  z-index:2;
  max-width:1200px;
}

.kicker{
  display:flex;
  gap:15px;
  align-items:center;
  text-transform:uppercase;
  letter-spacing:.25em;
  font-size:10px;
  margin-bottom:28px;
}

.kicker:before{
  content:"";
  width:45px;
  height:1px;
  background:var(--cream);
}

.hero h1{
  font-family:"Cormorant Garamond";
  font-size:clamp(5rem,12vw,13rem);
  line-height:.72;
  font-weight:500;
  letter-spacing:-.055em;
}

.hero h1 em{
  font-weight:400;
  margin-left:10vw;
}

.hero-bottom{
  margin-top:55px;
  display:flex;
  justify-content:space-between;
  align-items:end;
  gap:30px;
}

.hero-desc{
  max-width:390px;
  color:#c2beb5;
  font-size:14px;
  line-height:1.8;
}

.scroll{
  font-size:10px;
  letter-spacing:.22em;
  text-transform:uppercase;
  display:flex;
  gap:14px;
  align-items:center;
}

.scroll i{
  width:55px;
  height:1px;
  background:white;
}

/* INTRO */

.section{
  padding:15vh 6vw;
}

.intro{
  min-height:90vh;
  display:grid;
  grid-template-columns:1fr 1.4fr;
  gap:8vw;
  align-items:center;
}

.number{
  color:#77736b;
  font-size:10px;
  letter-spacing:.25em;
  margin-bottom:30px;
}

.display{
  font-family:"Cormorant Garamond";
  font-size:clamp(3.5rem,7vw,8rem);
  line-height:.9;
  font-weight:400;
  letter-spacing:-.04em;
}

.display em{
  color:#b7b0a4;
}

.intro-text{
  max-width:580px;
}

.intro-text p{
  font-family:"Cormorant Garamond";
  font-size:clamp(1.8rem,3vw,3.5rem);
  line-height:1.05;
  margin-bottom:35px;
}

.small{
  color:var(--muted);
  line-height:1.9;
  font-size:13px;
}

/* VIDEO / PROCESS */

.process{
  padding:0 4vw;
}

.process-video{
  height:80vh;
  min-height:550px;
  position:relative;
  overflow:hidden;
  background:#151513;
}

.process-video video{
  width:100%;
  height:100%;
  object-fit:cover;
  opacity:.78;
}

.video-fallback{
  position:absolute;
  inset:0;
  background:
    linear-gradient(90deg,rgba(0,0,0,.7),rgba(0,0,0,.05)),
    url("https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?auto=format&fit=crop&w=2200&q=90")
    center/cover;
  z-index:-1;
}

.process-overlay{
  position:absolute;
  inset:0;
  display:flex;
  flex-direction:column;
  justify-content:space-between;
  padding:5vw;
}

.process-title{
  font-family:"Cormorant Garamond";
  font-size:clamp(4rem,9vw,10rem);
  line-height:.8;
  max-width:800px;
}

.play{
  width:75px;
  height:75px;
  border:1px solid rgba(255,255,255,.6);
  border-radius:50%;
  display:grid;
  place-items:center;
  font-size:18px;
}

/* MARQUEE */

.marquee{
  overflow:hidden;
  border-top:1px solid var(--line);
  border-bottom:1px solid var(--line);
  padding:23px 0;
  white-space:nowrap;
}

.marquee-track{
  display:inline-flex;
  animation:marquee 25s linear infinite;
}

.marquee span{
  font-family:"Cormorant Garamond";
  font-size:36px;
  margin:0 30px;
}

.marquee b{
  color:var(--orange);
  font-size:14px;
}

@keyframes marquee{
  to{transform:translateX(-50%)}
}

/* DISHES */

.dishes-head{
  display:flex;
  justify-content:space-between;
  align-items:end;
  margin-bottom:80px;
}

.dishes-grid{
  display:grid;
  grid-template-columns:repeat(12,1fr);
  gap:20px;
}

.dish{
  position:relative;
  overflow:hidden;
}

.dish:nth-child(1){grid-column:1/7}
.dish:nth-child(2){grid-column:8/13;margin-top:130px}
.dish:nth-child(3){grid-column:2/7;margin-top:30px}
.dish:nth-child(4){grid-column:8/13;margin-top:-30px}

.dish-img{
  height:520px;
  overflow:hidden;
}

.dish:nth-child(2) .dish-img,
.dish:nth-child(4) .dish-img{
  height:400px;
}

.dish-img img{
  width:100%;
  height:100%;
  object-fit:cover;
  transition:transform 1s cubic-bezier(.2,.7,.2,1);
}

.dish:hover img{
  transform:scale(1.06);
}

.dish-info{
  display:flex;
  justify-content:space-between;
  padding:17px 0 45px;
  border-bottom:1px solid var(--line);
}

.dish-name{
  font-family:"Cormorant Garamond";
  font-size:28px;
}

.dish-cat{
  font-size:9px;
  letter-spacing:.18em;
  color:#77736b;
  text-transform:uppercase;
}

/* MENU */

.menu-section{
  background:#e8e2d7;
  color:#111;
  padding:14vh 6vw;
}

.menu-top{
  display:flex;
  justify-content:space-between;
  margin-bottom:80px;
}

.menu-title{
  font-family:"Cormorant Garamond";
  font-size:clamp(5rem,11vw,12rem);
  line-height:.72;
  letter-spacing:-.06em;
}

.menu-tabs{
  display:flex;
  gap:10px;
  flex-wrap:wrap;
  max-width:450px;
  align-content:flex-start;
}

.menu-tabs button{
  background:none;
  border:1px solid rgba(0,0,0,.2);
  padding:10px 15px;
  cursor:pointer;
  font-size:10px;
  text-transform:uppercase;
  letter-spacing:.12em;
}

.menu-tabs button.active{
  background:#111;
  color:#eee;
}

.menu-list{
  border-top:1px solid rgba(0,0,0,.25);
}

.menu-item{
  display:grid;
  grid-template-columns:80px 1fr auto;
  gap:20px;
  padding:27px 0;
  border-bottom:1px solid rgba(0,0,0,.18);
  align-items:center;
}

.menu-item .id{
  color:#777;
  font-size:11px;
}

.menu-item h3{
  font-family:"Cormorant Garamond";
  font-size:29px;
  font-weight:500;
}

.menu-item p{
  font-size:11px;
  color:#777;
  margin-top:5px;
}

.price{
  font-family:"Cormorant Garamond";
  font-size:25px;
}

/* EXPERIENCE */

.experience{
  min-height:100vh;
  display:grid;
  grid-template-columns:1fr 1fr;
  padding:0;
}

.exp-img{
  min-height:750px;
  background:
    linear-gradient(180deg,transparent,rgba(0,0,0,.45)),
    url("https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1600&q=90")
    center/cover;
}

.exp-copy{
  padding:10vw 7vw;
  display:flex;
  flex-direction:column;
  justify-content:center;
}

.exp-copy h2{
  font-family:"Cormorant Garamond";
  font-size:clamp(4rem,7vw,8rem);
  line-height:.8;
  font-weight:400;
}

.exp-copy p{
  color:#a6a198;
  max-width:450px;
  margin-top:45px;
  line-height:1.9;
  font-size:14px;
}

/* RESERVATION */

.reserve{
  padding:15vh 6vw;
}

.reserve-inner{
  border-top:1px solid var(--line);
  border-bottom:1px solid var(--line);
  padding:90px 0;
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:10vw;
}

.reserve h2{
  font-family:"Cormorant Garamond";
  font-size:clamp(4rem,8vw,9rem);
  line-height:.78;
  font-weight:400;
}

.reserve p{
  color:#9b978f;
  margin-top:35px;
  max-width:400px;
  line-height:1.8;
}

.form{
  display:grid;
  gap:18px;
}

.form input,
.form select{
  width:100%;
  background:none;
  border:none;
  border-bottom:1px solid var(--line);
  padding:18px 0;
  color:white;
  outline:none;
}

.form select option{
  background:#111;
}

.form button{
  margin-top:25px;
  padding:20px;
  border:1px solid white;
  background:white;
  color:#111;
  cursor:pointer;
  letter-spacing:.18em;
  font-size:10px;
  transition:.3s;
}

.form button:hover{
  background:transparent;
  color:white;
}

/* FOOTER */

footer{
  padding:8vh 6vw 35px;
}

.footer-logo{
  font-family:"Cormorant Garamond";
  font-size:clamp(6rem,17vw,18rem);
  line-height:.65;
  letter-spacing:-.07em;
}

.footer-grid{
  display:grid;
  grid-template-columns:2fr 1fr 1fr 1fr;
  gap:30px;
  margin-top:100px;
  padding-top:30px;
  border-top:1px solid var(--line);
}

.footer-grid h4{
  font-size:9px;
  letter-spacing:.2em;
  color:#77736b;
  margin-bottom:18px;
}

.footer-grid p,
.footer-grid a{
  font-size:12px;
  line-height:1.9;
  color:#b0aca3;
}

.copy{
  margin-top:80px;
  color:#66635d;
  font-size:10px;
}

/* REVEAL */

.reveal{
  opacity:0;
  transform:translateY(40px);
  transition:1s cubic-bezier(.2,.7,.2,1);
}

.reveal.visible{
  opacity:1;
  transform:none;
}

/* MOBILE */

@media(max-width:800px){

  nav{
    height:70px;
    padding:0 20px;
  }

  .navlinks{
    display:none;
  }

  .logo{
    font-size:25px;
  }

  .hero{
    padding:0 20px 50px;
  }

  .hero h1{
    font-size:25vw;
  }

  .hero h1 em{
    margin-left:15vw;
  }

  .hero-bottom{
    flex-direction:column;
    align-items:flex-start;
  }

  .intro{
    display:block;
    min-height:auto;
  }

  .intro-text{
    margin-top:70px;
  }

  .process{
    padding:0 15px;
  }

  .process-video{
    height:70vh;
    min-height:500px;
  }

  .dishes-head{
    display:block;
  }

  .dishes-grid{
    display:block;
  }

  .dish{
    margin:0 0 50px!important;
  }

  .dish-img,
  .dish:nth-child(2) .dish-img,
  .dish:nth-child(4) .dish-img{
    height:430px;
  }

  .menu-top{
    display:block;
  }

  .menu-tabs{
    margin-top:50px;
  }

  .menu-item{
    grid-template-columns:35px 1fr auto;
  }

  .menu-item h3{
    font-size:23px;
  }

  .experience{
    display:block;
  }

  .exp-img{
    min-height:65vh;
  }

  .reserve-inner{
    display:block;
  }

  .form{
    margin-top:70px;
  }

  .footer-grid{
    grid-template-columns:1fr 1fr;
    margin-top:70px;
  }

  .cursor{
    display:none;
  }
}
</style>
</head>

<body>

<div class="cursor"></div>

<div class="preloader">
  <span>MIZUYA</span>
</div>

<nav>
  <a href="#" class="logo">MIZUYA</a>

  <div class="navlinks">
    <a href="#story">Hikâye</a>
    <a href="#dishes">Lezzetler</a>
    <a href="#menu">Menü</a>
    <a href="#experience">Mekân</a>
  </div>

  <a href="#reservation" class="navbtn">Rezervasyon</a>
</nav>


<!-- HERO -->

<section class="hero">

  <div class="hero-media"></div>

  <div class="hero-content">

    <div class="kicker">
      Çorum · Japanese Lifestyle Cafe
    </div>

    <h1>
      Taste<br>
      <em>the</em> ritual.
    </h1>

    <div class="hero-bottom">

      <p class="hero-desc">
        Sushi, Korean toast, wok ve matcha kültürünün
        modern bir yorumla buluştuğu Mizuya.
        Bir yemek değil, akşamın kendisi.
      </p>

      <div class="scroll">
        aşağı kaydır
        <i></i>
      </div>

    </div>

  </div>
</section>


<!-- INTRO -->

<section class="section intro" id="story">

  <div class="reveal">
    <div class="number">01 / HİKÂYE</div>

    <div class="display">
      Bir fikirden<br>
      <em>bir tabağa.</em>
    </div>
  </div>

  <div class="intro-text reveal">

    <p>
      Mizuya, Japon estetiğini
      Çorum'un enerjisiyle
      yeniden yorumlar.
    </p>

    <div class="small">
      Her roll elde hazırlanır. Her sos mutfakta hazırlanır.
      Her tabak, malzemenin karakterini öne çıkarmak için
      tasarlanır.
      <br><br>
      Günlük taze ürünler, yüksek ateş, dengeli tatlar
      ve modern bir servis anlayışı.
    </div>

  </div>

</section>


<!-- VIDEO -->

<section class="process">

  <div class="process-video reveal">

    <div class="video-fallback"></div>

    <!-- Kendi videon varsa dosya adını buraya koy -->
    <video
      autoplay
      muted
      loop
      playsinline
      poster="https://images.unsplash.com/photo-1579584425555-c3ce17fd4351?auto=format&fit=crop&w=2000&q=85">

      <source src="mizuya-sushi-yapimi.mp4" type="video/mp4">

    </video>

    <div class="process-overlay">

      <div class="number">02 / MUTFAK</div>

      <div class="process-title">
        Elinden<br>
        masaya.
      </div>

      <div class="play">↗</div>

    </div>

  </div>

</section>


<div class="marquee">

  <div class="marquee-track">

    <span>SUSHI</span><b>✦</b>
    <span>NOODLE</span><b>✦</b>
    <span>KOREAN TOAST</span><b>✦</b>
    <span>MATCHA</span><b>✦</b>
    <span>COCKTAIL</span><b>✦</b>

    <span>SUSHI</span><b>✦</b>
    <span>NOODLE</span><b>✦</b>
    <span>KOREAN TOAST</span><b>✦</b>
    <span>MATCHA</span><b>✦</b>
    <span>COCKTAIL</span><b>✦</b>

  </div>

</div>


<!-- DISHES -->

<section class="section" id="dishes">

  <div class="dishes-head reveal">

    <div>
      <div class="number">03 / SEÇKİ</div>

      <div class="display">
        İmza<br>
        <em>lezzetler.</em>
      </div>
    </div>

    <p class="small">
      Mizuya mutfağından seçilmiş
      birkaç özel dokunuş.
    </p>

  </div>


  <div class="dishes-grid">

    <article class="dish reveal">

      <div class="dish-img">
        <img src="https://images.unsplash.com/photo-1553621042-f6e147245754?auto=format&fit=crop&w=1400&q=90">
      </div>

      <div class="dish-info">
        <div>
          <div class="dish-name">Salmon Aburi</div>
          <div class="dish-cat">Signature Roll</div>
        </div>

        <div class="price">790 ₺</div>
      </div>

    </article>


    <article class="dish reveal">

      <div class="dish-img">
        <img src="https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?auto=format&fit=crop&w=1200&q=90">
      </div>

      <div class="dish-info">
        <div>
          <div class="dish-name">California</div>
          <div class="dish-cat">Classic Roll</div>
        </div>

        <div class="price">750 ₺</div>
      </div>

    </article>


    <article class="dish reveal">

      <div class="dish-img">
        <img src="https://images.unsplash.com/photo-1569718212165-3a8278d5f624?auto=format&fit=crop&w=1400&q=90">
      </div>

      <div class="dish-info">
        <div>
          <div class="dish-name">Wok Noodle</div>
          <div class="dish-cat">High Heat Kitchen</div>
        </div>

        <div class="price">490 ₺</div>
      </div>

    </article>


    <article class="dish reveal">

      <div class="dish-img">
        <img src="https://images.unsplash.com/photo-1541167760496-1628856ab772?auto=format&fit=crop&w=1200&q=90">
      </div>

      <div class="dish-info">
        <div>
          <div class="dish-name">Matcha Latte</div>
          <div class="dish-cat">Mizuya Bar</div>
        </div>

        <div class="price">270 ₺</div>
      </div>

    </article>

  </div>

</section>


<!-- MENU -->

<section class="menu-section" id="menu">

  <div class="menu-top">

    <div>
      <div class="number">04 / MENÜ</div>

      <div class="menu-title">
        Ne<br>
        istersin?
      </div>
    </div>

    <div class="menu-tabs">

      <button class="active" data-cat="sushi">Sushi</button>
      <button data-cat="noodle">Noodle</button>
      <button data-cat="toast">Korean Toast</button>
      <button data-cat="drink">İçecek</button>

    </div>

  </div>


  <div class="menu-list">

    <div class="menu-item" data-cat="sushi">
      <span class="id">01</span>
      <div>
        <h3>Fried Roll</h3>
        <p>Çıtır kaplamalı imza roll</p>
      </div>
      <span class="price">750 ₺</span>
    </div>

    <div class="menu-item" data-cat="sushi">
      <span class="id">02</span>
      <div>
        <h3>Trüflü Ebiten Crispy</h3>
        <p>Karides · trüf · crispy</p>
      </div>
      <span class="price">780 ₺</span>
    </div>

    <div class="menu-item" data-cat="sushi">
      <span class="id">03</span>
      <div>
        <h3>Crazy Chef Roll</h3>
        <p>Şefin özel yorumu</p>
      </div>
      <span class="price">790 ₺</span>
    </div>

    <div class="menu-item" data-cat="sushi">
      <span class="id">04</span>
      <div>
        <h3>Philadelphia Roll</h3>
        <p>Somon · avokado · krem peynir</p>
      </div>
      <span class="price">690 ₺</span>
    </div>

    <div class="menu-item" data-cat="noodle">
      <span class="id">05</span>
      <div>
        <h3>Tavuklu Sebzeli Noodle</h3>
        <p>Yüksek ateşte wok</p>
      </div>
      <span class="price">490 ₺</span>
    </div>

    <div class="menu-item" data-cat="noodle">
      <span class="id">06</span>
      <div>
        <h3>Karidesli Sebzeli Noodle</h3>
        <p>Karides · sebze · soya-sesam</p>
      </div>
      <span class="price">690 ₺</span>
    </div>

    <div class="menu-item" data-cat="toast">
      <span class="id">07</span>
      <div>
        <h3>Korean Chicken</h3>
        <p>Çıtır ekmek · tavuk · özel sos</p>
      </div>
      <span class="price">450 ₺</span>
    </div>

    <div class="menu-item" data-cat="drink">
      <span class="id">08</span>
      <div>
        <h3>Çilekli Matcha</h3>
        <p>Matcha · çilek · süt</p>
      </div>
      <span class="price">270 ₺</span>
    </div>

    <div class="menu-item" data-cat="drink">
      <span class="id">09</span>
      <div>
        <h3>Sakura Pink</h3>
        <p>Mizuya signature</p>
      </div>
      <span class="price">260 ₺</span>
    </div>

  </div>

</section>


<!-- EXPERIENCE -->

<section class="experience" id="experience">

  <div class="exp-img reveal"></div>

  <div class="exp-copy reveal">

    <div class="number">05 / MEKÂN</div>

    <h2>
      Tokyo<br>
      esintisi.<br>
      Çorum'da.
    </h2>

    <p>
      Terracotta duvarlar, sıcak ışıklar,
      masa başı ateş kâseleri ve modern Japon
      detaylarıyla Mizuya yalnızca yemek
      yenilen bir yer değil.
      <br><br>
      Burada akşamın kendi ritmi var.
    </p>

  </div>

</section>


<!-- RESERVATION -->

<section class="reserve" id="reservation">

  <div class="reserve-inner">

    <div>

      <div class="number">06 / REZERVASYON</div>

      <h2>
        Masanız<br>
        hazır.
      </h2>

      <p>
        Akşamınızı önceden planlayın.
        Rezervasyon talebinizi oluşturun,
        Mizuya'da yerinizi ayırtın.
      </p>

    </div>


    <form class="form" id="reservationForm">

      <input type="text" placeholder="Ad Soyad" required>

      <input type="tel" placeholder="Telefon" required>

      <input type="date" required>

      <select required>
        <option value="">Saat seçin</option>
        <option>18:00</option>
        <option>18:30</option>
        <option>19:00</option>
        <option>19:30</option>
        <option>20:00</option>
        <option>20:30</option>
        <option>21:00</option>
        <option>21:30</option>
      </select>

      <select required>
        <option value="">Kişi sayısı</option>
        <option>1 kişi</option>
        <option>2 kişi</option>
        <option>3 kişi</option>
        <option>4 kişi</option>
        <option>5 kişi</option>
        <option>6+ kişi</option>
      </select>

      <button type="submit">
        REZERVASYON TALEBİ GÖNDER
      </button>

    </form>

  </div>

</section>


<!-- FOOTER -->

<footer>

  <div class="footer-logo">
    MIZUYA
  </div>

  <div class="footer-grid">

    <div>
      <h4>HAKKINDA</h4>
      <p>
        Japanese Lifestyle Cafe<br>
        Çorum · Türkiye
      </p>
    </div>

    <div>
      <h4>ADRES</h4>
      <p>
        Çepni, Fen Lisesi Cd.<br>
        No:1 Cd. 23D<br>
        Çorum Merkez
      </p>
    </div>

    <div>
      <h4>İLETİŞİM</h4>
      <p>
        0530 010 17 97<br>
        Her gün 12:00 — 23:00
      </p>
    </div>

    <div>
      <h4>SOSYAL</h4>
      <p>
        <a href="https://instagram.com/mizuya.tr" target="_blank">
          @mizuya.tr
        </a>
      </p>
    </div>

  </div>

  <div class="copy">
    © 2026 MIZUYA — Japanese Lifestyle Cafe
  </div>

</footer>


<script>

/* CURSOR */

const cursor = document.querySelector(".cursor");

document.addEventListener("mousemove",e=>{
  cursor.style.left=e.clientX+"px";
  cursor.style.top=e.clientY+"px";
});


/* SCROLL REVEAL */

const observer = new IntersectionObserver(entries=>{
  entries.forEach(entry=>{
    if(entry.isIntersecting){
      entry.target.classList.add("visible");
    }
  });
},{
  threshold:.12
});

document.querySelectorAll(".reveal").forEach(el=>{
  observer.observe(el);
});


/* MENU FILTER */

const tabs = document.querySelectorAll(".menu-tabs button");
const items = document.querySelectorAll(".menu-item");

tabs.forEach(tab=>{

  tab.addEventListener("click",()=>{

    tabs.forEach(t=>t.classList.remove("active"));
    tab.classList.add("active");

    const category = tab.dataset.cat;

    items.forEach(item=>{

      if(item.dataset.cat === category){
        item.style.display="grid";
      }else{
        item.style.display="none";
      }

    });

  });

});


/* RESERVATION */

document
.getElementById("reservationForm")
.addEventListener("submit",function(e){

  e.preventDefault();

  const name=this.querySelector("input[type=text]").value;
  const phone=this.querySelector("input[type=tel]").value;
  const date=this.querySelector("input[type=date]").value;
  const time=this.querySelector("select").value;

  const message =
  `Merhaba Mizuya, rezervasyon yapmak istiyorum.%0A%0A`+
  `Ad Soyad: ${name}%0A`+
  `Telefon: ${phone}%0A`+
  `Tarih: ${date}%0A`+
  `Saat: ${time}`;

  window.open(
    `https://wa.me/905300101797?text=${message}`,
    "_blank"
  );

});


/* PARALLAX HERO */

window.addEventListener("scroll",()=>{

  const hero=document.querySelector(".hero-media");

  if(window.scrollY < window.innerHeight){
    hero.style.transform=
      `scale(1) translateY(${window.scrollY*0.12}px)`;
  }

});

</script

</body>
</html>
