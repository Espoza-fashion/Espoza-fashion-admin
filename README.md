<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Espoza Fashion Admin</title>

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;600;700;800&display=swap" rel="stylesheet">

<style>

*{
box-sizing:border-box;
margin:0;
padding:0;
}

body{
font-family:Tajawal,sans-serif;
background:#f6f6f6;
color:#222;
}

.hidden{
display:none!important;
}

button,
input,
textarea,
select{
font-family:inherit;
}


/* =========================
LOGIN
========================= */

.login-page{
min-height:100vh;
display:flex;
align-items:center;
justify-content:center;
padding:20px;
background:#111;
}

.login-box{
width:100%;
max-width:400px;
background:#fff;
border-radius:22px;
padding:35px 25px;
text-align:center;
box-shadow:0 20px 60px rgba(0,0,0,.3);
}

.logo{
font-size:30px;
font-weight:800;
letter-spacing:3px;
margin-bottom:8px;
}

.gold{
color:#d4af37;
}

.login-box h1{
font-size:24px;
margin-bottom:8px;
}

.login-box p{
color:#777;
margin-bottom:25px;
}

.login-box input{
width:100%;
padding:15px;
border:1px solid #ddd;
border-radius:12px;
font-size:16px;
text-align:center;
outline:none;
margin-bottom:12px;
}

.login-box input:focus{
border-color:#d4af37;
}

.login-box button{
width:100%;
padding:15px;
border:0;
border-radius:12px;
background:#111;
color:#fff;
font-size:16px;
font-weight:700;
cursor:pointer;
}

.login-box button:hover{
background:#d4af37;
color:#111;
}

.error{
color:#d00000;
font-size:14px;
margin-top:12px;
min-height:20px;
}


/* =========================
TOPBAR
========================= */

.topbar{
background:#111;
color:#fff;
padding:17px 22px;
display:flex;
justify-content:space-between;
align-items:center;
position:sticky;
top:0;
z-index:100;
}

.brand{
font-size:24px;
font-weight:800;
letter-spacing:2px;
}

.brand small{
display:block;
font-size:12px;
font-weight:400;
letter-spacing:0;
color:#aaa;
margin-top:3px;
}

.logout{
background:#d4af37;
color:#111;
border:0;
border-radius:10px;
padding:10px 16px;
font-weight:700;
cursor:pointer;
}


/* =========================
MAIN
========================= */

.container{
max-width:1200px;
margin:auto;
padding:25px 16px 50px;
}

.welcome{
margin-bottom:25px;
}

.welcome h1{
font-size:28px;
margin-bottom:5px;
}

.welcome p{
color:#777;
}


/* =========================
STATS
========================= */

.stats{
display:grid;
grid-template-columns:repeat(4,1fr);
gap:15px;
margin-bottom:25px;
}

.stat{
background:#fff;
border-radius:16px;
padding:20px;
box-shadow:0 4px 15px rgba(0,0,0,.05);
}

.stat span{
font-size:14px;
color:#777;
}

.stat strong{
display:block;
font-size:28px;
margin-top:7px;
}


/* =========================
MENU
========================= */

.menu{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:15px;
}

.menu-btn{
background:#fff;
border:0;
border-radius:16px;
padding:22px 17px;
text-align:right;
cursor:pointer;
box-shadow:0 4px 15px rgba(0,0,0,.05);
transition:.2s;
}

.menu-btn:hover{
transform:translateY(-3px);
}

.menu-icon{
font-size:30px;
display:block;
margin-bottom:10px;
}

.menu-btn strong{
display:block;
font-size:18px;
margin-bottom:5px;
}

.menu-btn small{
color:#777;
}


/* =========================
CONTENT
========================= */

.content{
margin-top:25px;
background:#fff;
border-radius:18px;
padding:22px;
box-shadow:0 4px 15px rgba(0,0,0,.05);
}

.content-head{
display:flex;
justify-content:space-between;
align-items:center;
gap:10px;
margin-bottom:20px;
}

.content-head h2{
font-size:22px;
}

.primary{
background:#111;
color:#fff;
border:0;
border-radius:10px;
padding:11px 16px;
cursor:pointer;
font-weight:700;
}

.primary:hover{
background:#d4af37;
color:#111;
}


/* =========================
PRODUCTS
========================= */

.product-list{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:15px;
}

.product-card{
border:1px solid #eee;
border-radius:15px;
overflow:hidden;
background:#fff;
}

.product-image{
width:100%;
height:210px;
object-fit:cover;
background:#eee;
}

.product-info{
padding:15px;
}

.product-info h3{
font-size:17px;
margin-bottom:6px;
}

.product-price{
font-weight:800;
font-size:18px;
}

.product-category{
font-size:13px;
color:#777;
margin:5px 0 12px;
}

.actions{
display:flex;
gap:8px;
}

.action{
flex:1;
padding:9px;
border:0;
border-radius:9px;
cursor:pointer;
font-weight:700;
}

.edit{
background:#eee;
}

.delete{
background:#111;
color:#fff;
}


/* =========================
FORMS
========================= */

.form{
display:grid;
gap:14px;
}

.form label{
font-weight:700;
font-size:14px;
}

.form input,
.form textarea,
.form select{
width:100%;
padding:13px;
border:1px solid #ddd;
border-radius:10px;
outline:none;
font-size:15px;
}

.form textarea{
min-height:110px;
resize:vertical;
}

.form input:focus,
.form textarea:focus,
.form select:focus{
border-color:#d4af37;
}

.form-actions{
display:flex;
gap:10px;
margin-top:5px;
}

.cancel{
background:#eee;
color:#222;
border:0;
border-radius:10px;
padding:12px 18px;
font-weight:700;
cursor:pointer;
}


/* =========================
ORDERS
========================= */

.order{
border:1px solid #eee;
border-radius:14px;
padding:15px;
margin-bottom:12px;
}

.order strong{
font-size:17px;
}

.order p{
color:#666;
margin-top:5px;
font-size:14px;
}

.status{
display:inline-block;
margin-top:10px;
padding:5px 10px;
border-radius:8px;
background:#eee;
font-size:13px;
}


/* =========================
MOBILE
========================= */

@media(max-width:750px){

.stats{
grid-template-columns:repeat(2,1fr);
}

.menu{
grid-template-columns:repeat(2,1fr);
}

.product-list{
grid-template-columns:repeat(2,1fr);
}

}

@media(max-width:480px){

.topbar{
padding:14px;
}

.brand{
font-size:20px;
}

.logout{
padding:8px 12px;
}

.container{
padding:20px 12px 40px;
}

.menu{
grid-template-columns:1fr;
}

.product-list{
grid-template-columns:1fr;
}

.stats{
gap:10px;
}

.stat{
padding:16px;
}

.content{
padding:16px;
}

}

</style>
</head>

<body>


<!-- =========================
LOGIN
========================= -->

<div id="loginPage" class="login-page">

<div class="login-box">

<div class="logo">
ESPOZA <span class="gold">ADMIN</span>
</div>

<h1>لوحة التحكم</h1>

<p>
تسجيل الدخول لإدارة المتجر
</p>

<input
id="password"
type="password"
placeholder="كلمة السر"
autocomplete="off"
onkeydown="if(event.key==='Enter')login()"
>

<button onclick="login()">
دخول
</button>

<div id="loginError" class="error"></div>

</div>

</div>



<!-- =========================
ADMIN
========================= -->

<div id="adminPage" class="hidden">

<header class="topbar">

<div>

<div class="brand">
ESPOZA <span class="gold">ADMIN</span>
</div>

<div class="brand small">
إدارة متجر Espoza Fashion
</div>

</div>

<button class="logout" onclick="logout()">
تسجيل الخروج
</button>

</header>


<main class="container">

<section class="welcome">

<h1>
أهلًا بك 👋
</h1>

<p>
من هون رح تتحكم بمتجر Espoza Fashion كامل.
</p>

</section>


<section class="stats">

<div class="stat">
<span>المنتجات</span>
<strong id="productsCount">0</strong>
</div>

<div class="stat">
<span>الطلبات</span>
<strong id="ordersCount">0</strong>
</div>

<div class="stat">
<span>العروض</span>
<strong id="offersCount">0</strong>
</div>

<div class="stat">
<span>حالة المتجر</span>
<strong>فعال</strong>
</div>

</section>


<section class="menu">

<button class="menu-btn" onclick="showProducts()">

<span class="menu-icon">👗</span>

<strong>
المنتجات
</strong>

<small>
إضافة وتعديل وحذف المنتجات
</small>

</button>


<button class="menu-btn" onclick="showOrders()">

<span class="menu-icon">🛍️</span>

<strong>
الطلبات
</strong>

<small>
مشاهدة طلبات الزبائن
</small>

</button>


<button class="menu-btn" onclick="showSlider()">

<span class="menu-icon">🖼️</span>

<strong>
السلايدر
</strong>

<small>
إدارة صور الواجهة الرئيسية
</small>

</button>


<button class="menu-btn" onclick="showAnnouncement()">

<span class="menu-icon">📢</span>

<strong>
الإعلان العلوي
</strong>

<small>
تعديل الإعلان الموجود أعلى الموقع
</small>

</button>


<button class="menu-btn" onclick="showSettings()">

<span class="menu-icon">⚙️</span>

<strong>
إعدادات المتجر
</strong>

<small>
الواتساب والتوصيل والمعلومات
</small>

</button>


<button class="menu-btn" onclick="showSocial()">

<span class="menu-icon">📱</span>

<strong>
السوشيال ميديا
</strong>

<small>
الروابط وأعداد المتابعين
</small>

</button>

</section>


<section id="content" class="content">

<div style="text-align:center;padding:40px;color:#777">

<h2>
اختر قسمًا للبدء
</h2>

<p style="margin-top:8px">
لوحة التحكم جاهزة للربط مع بيانات المتجر.
</p>

</div>

</section>

</main>

</div>



<script>

/* ==========================================
SUPABASE
========================================== */

/*
ضع بيانات مشروعك هنا
*/

const SUPABASE_URL = "ضع Project URL هنا";

const SUPABASE_KEY = "ضع Publishable key هنا";


const supabaseClient =
window.supabase.createClient(
SUPABASE_URL,
SUPABASE_KEY
);


/* ==========================================
ADMIN PASSWORD
========================================== */

const ADMIN_PASSWORD = "Espoza202900$";


/* ==========================================
LOGIN
========================================== */

function login(){

const password =
document.getElementById("password").value;

const error =
document.getElementById("loginError");


if(password === ADMIN_PASSWORD){

localStorage.setItem(
"espoza_admin_logged",
"true"
);

document
.getElementById("loginPage")
.classList.add("hidden");

document
.getElementById("adminPage")
.classList.remove("hidden");

loadDashboard();

}else{

error.textContent =
"كلمة السر غير صحيحة ❌";

}

}


/* ==========================================
LOGOUT
========================================== */

function logout(){

localStorage.removeItem(
"espoza_admin_logged"
);

location.reload();

}


/* ==========================================
CHECK LOGIN
========================================== */

function checkLogin(){

const logged =
localStorage.getItem(
"espoza_admin_logged"
);

if(logged === "true"){

document
.getElementById("loginPage")
.classList.add("hidden");

document
.getElementById("adminPage")
.classList.remove("hidden");

loadDashboard();

}

}


/* ==========================================
DASHBOARD
========================================== */

async function loadDashboard(){

try{

const products =
await supabaseClient
.from("products")
.select("id,is_offer");

if(!products.error){

document.getElementById(
"productsCount"
).textContent =
products.data.length;

document.getElementById(
"offersCount"
).textContent =
products.data.filter(
p=>p.is_offer === true
).length;

}


const orders =
await supabaseClient
.from("orders")
.select("id");

if(!orders.error){

document.getElementById(
"ordersCount"
).textContent =
orders.data.length;

}

}catch(error){

console.error(error);

}

}


/* ==========================================
PRODUCTS
========================================== */

async function showProducts(){

const content =
document.getElementById("content");

content.innerHTML = `

<div class="content-head">

<h2>👗 المنتجات</h2>

<button
class="primary"
onclick="addProduct()"
>
+ إضافة منتج
</button>

</div>

<div id="productList">
جاري تحميل المنتجات...
</div>

`;

await loadProducts();

}


async function loadProducts(){

const box =
document.getElementById("productList");

const result =
await supabaseClient
.from("products")
.select("*")
.order("created_at",{ascending:false});


if(result.error){

box.innerHTML =
"<p>حدث خطأ في تحميل المنتجات.</p>";

console.error(result.error);

return;

}


if(!result.data.length){

box.innerHTML = `

<div style="text-align:center;padding:40px;color:#777">

<h3>
لا يوجد منتجات حتى الآن
</h3>

<p style="margin-top:8px">
اضغط إضافة منتج لبدء إضافة منتجات Espoza.
</p>

</div>

`;

return;

}


box.className="product-list";


box.innerHTML =
result.data.map(product=>`

<div class="product-card">

<div
style="
height:210px;
background:#eee;
display:flex;
align-items:center;
justify-content:center;
color:#aaa;
"
>
لا توجد صورة
</div>

<div class="product-info">

<h3>
${escapeHtml(product.name || "بدون اسم")}
</h3>

<div class="product-category">
${escapeHtml(product.category || "")}
</div>

<div class="product-price">
${product.price || 0} ₪
</div>

<div class="actions">

<button
class="action edit"
onclick="editProduct('${product.id}')"
>
تعديل
</button>

<button
class="action delete"
onclick="deleteProduct('${product.id}')"
>
حذف
</button>

</div>

</div>

</div>

`).join("");

}


/* ==========================================
ADD PRODUCT
========================================== */

function addProduct(){

const content =
document.getElementById("content");

content.innerHTML = `

<div class="content-head">

<h2>➕ إضافة منتج</h2>

</div>


<form
class="form"
onsubmit="saveProduct(event)"
>

<label>
اسم المنتج
</label>

<input
id="productName"
required
placeholder="مثال: فستان ليان"
>


<label>
الوصف
</label>

<textarea
id="productDescription"
placeholder="وصف المنتج"
></textarea>


<label>
التصنيف
</label>

<select id="productCategory">

<option value="dresses">
فساتين
</option>

<option value="sets">
أطقم
</option>

<option value="offers">
العروضات
</option>

</select>


<label>
السعر
</label>

<input
id="productPrice"
type="number"
min="0"
step="0.01"
required
placeholder="250"
>


<label>
السعر القديم
</label>

<input
id="productOldPrice"
type="number"
min="0"
step="0.01"
placeholder="300"
>


<label>
SKU
</label>

<input
id="productSku"
placeholder="ESP-001"
>


<label>

<input
id="productOffer"
type="checkbox"
style="width:auto"
>

 المنتج ضمن العروضات

</label>


<label>

<input
id="productAvailable"
type="checkbox"
checked
style="width:auto"
>

 المنتج متوفر

</label>


<div class="form-actions">

<button
type="submit"
class="primary"
>
حفظ المنتج
</button>

<button
type="button"
class="cancel"
onclick="showProducts()"
>
إلغاء
</button>

</div>

</form>

`;

}


async function saveProduct(event){

event.preventDefault();


const product = {

name:
document.getElementById("productName").value.trim(),

description:
document.getElementById("productDescription").value.trim(),

category:
document.getElementById("productCategory").value,

price:
Number(document.getElementById("productPrice").value),

old_price:
Number(document.getElementById("productOldPrice").value) || null,

sku:
document.getElementById("productSku").value.trim() || null,

is_offer:
document.getElementById("productOffer").checked,

is_available:
document.getElementById("productAvailable").checked

};


const result =
await supabaseClient
.from("products")
.insert(product);


if(result.error){

alert(
"حدث خطأ أثناء حفظ المنتج:\n"
+
result.error.message
);

return;

}


alert("تم إضافة المنتج بنجاح ✅");

await loadDashboard();

showProducts();

}


/* ==========================================
EDIT PRODUCT
========================================== */

async function editProduct(id){

const result =
await supabaseClient
.from("products")
.select("*")
.eq("id",id)
.single();


if(result.error){

alert(result.error.message);

return;

}


const p=result.data;


const content =
document.getElementById("content");


content.innerHTML = `

<div class="content-head">

<h2>✏️ تعديل المنتج</h2>

</div>


<form
class="form"
onsubmit="updateProduct(event,'${id}')"
>

<label>
اسم المنتج
</label>

<input
id="productName"
value="${escapeAttr(p.name || "")}"
required
>


<label>
الوصف
</label>

<textarea
id="productDescription"
>${escapeHtml(p.description || "")}</textarea>


<label>
التصنيف
</label>

<select id="productCategory">

<option value="dresses" ${p.category==="dresses"?"selected":""}>
فساتين
</option>

<option value="sets" ${p.category==="sets"?"selected":""}>
أطقم
</option>

<option value="offers" ${p.category==="offers"?"selected":""}>
العروضات
</option>

</select>


<label>
السعر
</label>

<input
id="productPrice"
type="number"
value="${p.price || 0}"
required
>


<label>
السعر القديم
</label>

<input
id="productOldPrice"
type="number"
value="${p.old_price || ""}"
>


<label>
SKU
</label>

<input
id="productSku"
value="${escapeAttr(p.sku || "")}"
>


<label>

<input
id="productOffer"
type="checkbox"
${p.is_offer ? "checked":""}
style="width:auto"
>

 المنتج ضمن العروضات

</label>


<label>

<input
id="productAvailable"
type="checkbox"
${p.is_available !== false ? "checked":""}
style="width:auto"
>

 المنتج متوفر

</label>


<div class="form-actions">

<button
type="submit"
class="primary"
>
حفظ التعديل
</button>

<button
type="button"
class="cancel"
onclick="showProducts()"
>
إلغاء
</button>

</div>

</form>

`;

}


async function updateProduct(event,id){

event.preventDefault();


const update = {

name:
document.getElementById("productName").value.trim(),

description:
document.getElementById("productDescription").value.trim(),

category:
document.getElementById("productCategory").value,

price:
Number(document.getElementById("productPrice").value),

old_price:
Number(document.getElementById("productOldPrice").value) || null,

sku:
document.getElementById("productSku").value.trim() || null,

is_offer:
document.getElementById("productOffer").checked,

is_available:
document.getElementById("productAvailable").checked,

updated_at:
new Date().toISOString()

};


const result =
await supabaseClient
.from("products")
.update(update)
.eq("id",id);


if(result.error){

alert(result.error.message);

return;

}


alert("تم تعديل المنتج ✅");

showProducts();

await loadDashboard();

}


/* ==========================================
DELETE PRODUCT
========================================== */

async function deleteProduct(id){

if(!confirm("هل أنت متأكد من حذف المنتج؟")){

return;

}


const result =
await supabaseClient
.from("products")
.delete()
.eq("id",id);


if(result.error){

alert(result.error.message);

return;

}


alert("تم حذف المنتج 🗑️");

showProducts();

await loadDashboard();

}


/* ==========================================
ORDERS
========================================== */

async function showOrders(){

const content =
document.getElementById("content");

content.innerHTML = `

<div class="content-head">

<h2>🛍️ الطلبات</h2>

</div>

<div id="ordersList">
جاري تحميل الطلبات...
</div>

`;


const result =
await supabaseClient
.from("orders")
.select("*")
.order("created_at",{ascending:false});


const box =
document.getElementById("ordersList");


if(result.error){

box.innerHTML =
"<p>حدث خطأ في تحميل الطلبات.</p>";

return;

}


if(!result.data.length){

box.innerHTML = `

<div style="text-align:center;padding:40px;color:#777">

<h3>
لا توجد طلبات حتى الآن
</h3>

</div>

`;

return;

}


box.innerHTML =
result.data.map(order=>`

<div class="order">

<strong>
${escapeHtml(order.customer_name || "")}
</strong>

<p>
📞 ${escapeHtml(order.phone || "")}
</p>

<p>
📍 ${escapeHtml(order.region || "")}
</p>

<p>
📦 ${escapeHtml(order.product_name || "")}
</p>

<p>
💰 المجموع: ${order.total_price || 0} ₪
</p>

<span class="status">
${escapeHtml(order.status || "new")}
</span>

</div>

`).join("");

}


/* ==========================================
SLIDER
========================================== */

function showSlider(){

document.getElementById("content").innerHTML = `

<div class="content-head">

<h2>🖼️ السلايدر</h2>

</div>

<p style="color:#777">
قسم السلايدر جاهز، وسنربطه بالصور في الخطوة التالية.
</p>

`;

}


/* ==========================================
ANNOUNCEMENT
========================================== */

function showAnnouncement(){

document.getElementById("content").innerHTML = `

<div class="content-head">

<h2>📢 الإعلان العلوي</h2>

</div>

<p style="color:#777">
قسم الإعلان جاهز، وسنربطه بقاعدة البيانات في الخطوة التالية.
</p>

`;

}


/* ==========================================
SETTINGS
========================================== */

function showSettings(){

document.getElementById("content").innerHTML = `

<div class="content-head">

<h2>⚙️ إعدادات المتجر</h2>

</div>

<div class="form">

<label>
اسم المتجر
</label>

<input
value="Espoza Fashion"
>

<label>
رقم واتساب الطلبات
</label>

<input
placeholder="ضع رقم الواتساب"
>

<label>
توصيل الضفة الغربية
</label>

<input
type="number"
value="20"
>

<label>
توصيل القدس
</label>

<input
type="number"
value="30"
>

<label>
توصيل الداخل
</label>

<input
type="number"
value="70"
>

<button
class="primary"
onclick="alert('سيتم ربط الإعدادات بقاعدة البيانات في الخطوة القادمة.')"
>
حفظ الإعدادات
</button>

</div>

`;

}


/* ==========================================
SOCIAL
========================================== */

function showSocial(){

document.getElementById("content").innerHTML = `

<div class="content-head">

<h2>📱 السوشيال ميديا</h2>

</div>

<div class="form">

<label>
Instagram
</label>

<input
placeholder="رابط Instagram"
>

<label>
Facebook
</label>

<input
placeholder="رابط Facebook"
>

<label>
TikTok
</label>

<input
placeholder="رابط TikTok"
>

<label>
Snapchat
</label>

<input
placeholder="رابط Snapchat"
>

<label>
عدد متابعي Facebook
</label>

<input
type="number"
value="22025"
>

<label>
عدد متابعي Instagram
</label>

<input
type="number"
value="900"
>

<label>
عدد متابعي TikTok
</label>

<input
type="number"
value="700"
>

<label>
عدد متابعي Snapchat
</label>

<input
type="number"
value="500"
>

<button
class="primary"
onclick="alert('سيتم ربط السوشيال ميديا بقاعدة البيانات في الخطوة القادمة.')"
>
حفظ
</button>

</div>

`;

}


/* ==========================================
SECURITY HELPERS
========================================== */

function escapeHtml(value){

return String(value)
.replace(/&/g,"&amp;")
.replace(/</g,"&lt;")
.replace(/>/g,"&gt;")
.replace(/"/g,"&quot;")
.replace(/'/g,"&#039;");

}


function escapeAttr(value){

return escapeHtml(value);

}


/* ==========================================
START
========================================== */

checkLogin();

</script>

</body>
</html>
