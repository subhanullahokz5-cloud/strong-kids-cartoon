
<!DOCTYPE html>
<html lang="ur" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>STRONG KIDS CARTOON</title>
<style>
*{box-sizing:border-box}
body{
 margin:0;
 font-family:Arial,sans-serif;
 background:#10152b;
 color:white;
 text-align:center;
}
header{
 background:#6539d9;
 padding:25px 10px;
}
header h1{margin:0;font-size:27px}
header p{margin-bottom:0}
.search{padding:15px}
input{
 width:90%;padding:14px;
 border-radius:12px;border:0;font-size:16px;
}
.menu{
 display:flex;flex-wrap:wrap;
 justify-content:center;gap:10px;
 padding:10px;
}
button{
 border:0;border-radius:12px;
 padding:13px 17px;
 font-size:16px;font-weight:bold;
 background:#ffbd35;color:#17152b;
 cursor:pointer;
}
.cards{
 display:grid;
 grid-template-columns:repeat(2,1fr);
 gap:12px;padding:15px;
}
.card{
 background:#252d4c;
 padding:20px 8px;
 border-radius:15px;
 cursor:pointer;
}
.card span{font-size:40px}
.card h3{margin:10px 0}
#story{
 display:none;background:#fff;color:#222;
 margin:15px;padding:20px;
 border-radius:15px;line-height:2;
}
footer{padding:25px;color:#bbb}
</style>
</head>
<body>

<header>
<h1>🌟 STRONG KIDS CARTOON 🌟</h1>
<p>بچوں کی تعلیم اور تفریح کی دنیا</p>
</header>

<div class="search">
<input id="search" placeholder="کہانی تلاش کریں..." oninput="filterCards()">
</div>

<div class="menu">
<button onclick="showAll()">سب دیکھیں</button>
<button onclick="filterType('islam')">اسلامی</button>
<button onclick="filterType('learn')">تعلیم</button>
<button onclick="filterType('fun')">مزاحیہ</button>
</div>

<div class="cards" id="cards">

<div class="card" data-type="islam" onclick="openStory('🌙 اسلامی کہانی','ایک دن احمد نے اپنے دوست کی مدد کی۔ اس کے استاد نے کہا: دوسروں کی مدد کرنا بہت اچھی عادت ہے۔ اللہ نیکی کرنے والوں کو پسند فرماتا ہے۔')">
<span>🌙</span><h3>اسلامی کہانیاں</h3>
</div>

<div class="card" data-type="learn" onclick="openStory('🔤 ABC سیکھیں','A for Apple 🍎<br>B for Ball ⚽<br>C for Cat 🐱<br>D for Dog 🐶')">
<span>🔤</span><h3>ABC سیکھیں</h3>
</div>

<div class="card" data-type="fun" onclick="openStory('😂 مزاحیہ کہانی','ایک خرگوش نے کچھوا سے کہا: تم بہت آہستہ چلتے ہو! کچھوے نے جواب دیا: لیکن میں کبھی ہمت نہیں ہارتا!')">
<span>😂</span><h3>مزاحیہ کہانیاں</h3>
</div>

<div class="card" data-type="learn" onclick="openStory('📚 اردو حروف','ا سے انار 🍎<br>ب سے بکری 🐐<br>پ سے پتنگ 🪁<br>ت سے تتلی 🦋')">
<span>📚</span><h3>اردو سیکھیں</h3>
</div>

<div class="card" data-type="fun" onclick="openStory('🦁 جانوروں کی دنیا','شیر جنگل کا بادشاہ ہے۔ ہاتھی بہت بڑا جانور ہے اور خرگوش بہت تیز دوڑتا ہے۔')">
<span>🦁</span><h3>جانوروں کی دنیا</h3>
</div>

<div class="card" data-type="learn" onclick="openStory('🔢 گنتی سیکھیں','1 ایک ☝️<br>2 دو ✌️<br>3 تین<br>4 چار<br>5 پانچ')">
<span>🔢</span><h3>گنتی سیکھیں</h3>
</div>

</div>

<div id="story">
<h2 id="storyTitle"></h2>
<p id="storyText"></p>
<button onclick="closeStory()">واپس جائیں</button>
</div>

<footer>
❤️ STRONG KIDS CARTOON<br>
بچوں کے روشن مستقبل کے لیے
</footer>

<script>
function openStory(title,text){
 document.getElementById('storyTitle').innerHTML=title;
 document.getElementById('storyText').innerHTML=text;
 document.getElementById('story').style.display='block';
 document.getElementById('cards').style.display='none';
}
function closeStory(){
 document.getElementById('story').style.display='none';
 document.getElementById('cards').style.display='grid';
}
function filterType(type){
 document.querySelectorAll('.card').forEach(card=>{
 card.style.display=card.dataset.type===type?'block':'none';
 });
 document.getElementById('story').style.display='none';
 document.getElementById('cards').style.display='grid';
}
function showAll(){
 document.querySelectorAll('.card').forEach(card=>{
 card.style.display='block';
 });
 document.getElementById('cards').style.display='grid';
 document.getElementById('story').style.display='none';
}
function filterCards(){
 let q=document.getElementById('search').value;
 document.querySelectorAll('.card').forEach(card=>{
 card.style.display=card.innerText.includes(q)?'block':'none';
 });
}
</script>

</body>
</html>
