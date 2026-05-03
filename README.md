<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Noor Traveler</title>

<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&family=Big+Shoulders+Display:wght@800&display=swap" rel="stylesheet">

<!-- GSAP -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>

<style>
body{
  margin:0;
  font-family:'Cairo',sans-serif;
  background:#050807;
  color:#fff;
  overflow-x:hidden;
}

/* 🎬 INTRO */
.intro{
  position:fixed;
  inset:0;
  background:#000;
  display:flex;
  align-items:center;
  justify-content:center;
  z-index:9999;
}

.intro h1{
  font-family:'Big Shoulders Display';
  font-size:60px;
  letter-spacing:5px;
}

/* HERO VIDEO */
.hero{
  height:100vh;
  position:relative;
  overflow:hidden;
}

.hero video{
  position:absolute;
  width:100%;
  height:100%;
  object-fit:cover;
}

.overlay{
  position:absolute;
  inset:0;
  background:linear-gradient(rgba(0,0,0,.4),rgba(0,0,0,.9));
}

.hero-content{
  position:absolute;
  bottom:20%;
  right:10%;
}

.hero h1{
  font-size:70px;
  margin:0;
}

/* SECTIONS */
.section{
  padding:100px 20px;
  max-width:1100px;
  margin:auto;
  opacity:0;
  transform:translateY(40px);
}

/* CARDS */
.cards{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:20px;
}

.card{
  background:#111;
  padding:30px;
  cursor:pointer;
  transition:.4s;
}

.card:hover{
  transform:scale(1.07);
  background:#1a1a1a;
}
</style>
</head>

<body>

<!-- INTRO -->
<div class="intro" id="intro">
  <h1>NOOR TRAVELER</h1>
</div>

<!-- HERO -->
<div class="hero">
  <video autoplay muted loop>
    <source src="https://cdn.coverr.co/videos/coverr-aerial-shot-of-mountains-1573/1080p.mp4">
  </video>
  <div class="overlay"></div>

  <div class="hero-content">
    <h1>رحلة… داخل العالم الحقيقي</h1>
    <p>مش فلوق — تجربة</p>
  </div>
</div>

<!-- ABOUT -->
<div class="section">
  <h2>من أنا</h2>
  <p>أنا أوثق تجارب السفر بدون فلترة. أماكن حقيقية، ناس حقيقيين، لحظات ما تنعاد.</p>
</div>

<!-- TRIPS -->
<div class="section">
  <h2>رحلاتي</h2>
  <div class="cards">
    <div class="card">بونكاك - مغامرة ATV</div>
    <div class="card">بالي - شلالات</div>
    <div class="card">جاكرتا - الحياة اليومية</div>
  </div>
</div>

<script>

// 🎬 INTRO ANIMATION
gsap.to("#intro", {
  opacity:0,
  duration:1.5,
  delay:1.5,
  onComplete:()=>document.getElementById("intro").style.display="none"
})

// ✨ SCROLL ANIMATION
gsap.utils.toArray(".section").forEach(section=>{
  gsap.to(section,{
    scrollTrigger:{
      trigger:section,
      start:"top 80%"
    },
    opacity:1,
    y:0,
    duration:1
  })
})

</script>

</body>
</html>
