<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Espoza Fashion — Admin</title>

<meta name="theme-color" content="#111111">

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link
    href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;600;700;800&display=swap"
    rel="stylesheet"
>

<style>

/* =========================================================
   RESET
========================================================= */

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:"Tajawal",sans-serif;
    background:#f6f6f6;
    color:#222;
    min-height:100vh;
}

button,
input,
textarea,
select{
    font-family:inherit;
}

button{
    cursor:pointer;
}

.hidden{
    display:none!important;
}


/* =========================================================
   VARIABLES
========================================================= */

:root{
    --black:#111111;
    --gold:#d4af37;
    --gold-dark:#b8921e;
    --white:#ffffff;
    --bg:#f6f6f6;
    --border:#e8e8e8;
    --muted:#777;
    --danger:#d00000;
    --success:#15803d;
    --shadow:0 5px 20px rgba(0,0,0,.05);
}


/* =========================================================
   LOGIN
========================================================= */

.login-page{
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:20px;
    background:
        radial-gradient(
            circle at top right,
            rgba(212,175,55,.12),
            transparent 35%
        ),
        #111;
}

.login-box{
    width:100%;
    max-width:420px;
    background:#fff;
    border-radius:24px;
    padding:38px 28px;
    box-shadow:0 25px 80px rgba(0,0,0,.35);
}

.login-logo{
    text-align:center;
    font-size:31px;
    font-weight:800;
    letter-spacing:3px;
    margin-bottom:8px;
}

.gold{
    color:var(--gold);
}

.login-title{
    text-align:center;
    font-size:25px;
    margin-top:12px;
}

.login-description{
    text-align:center;
    color:var(--muted);
    margin-top:7px;
    margin-bottom:28px;
}

.login-field{
    position:relative;
}

.login-field input{
    width:100%;
    height:54px;
    border:1px solid #ddd;
    border-radius:13px;
    padding:0 16px;
    outline:none;
    font-size:16px;
    text-align:center;
    transition:.2s;
}

.login-field input:focus{
    border-color:var(--gold);
    box-shadow:0 0 0 3px rgba(212,175,55,.12);
}

.login-button{
    width:100%;
    height:54px;
    margin-top:12px;
    border:0;
    border-radius:13px;
    background:var(--black);
    color:#fff;
    font-size:17px;
    font-weight:800;
    transition:.2s;
}

.login-button:hover{
    background:var(--gold);
    color:#111;
}

.login-error{
    min-height:22px;
    margin-top:12px;
    text-align:center;
    color:var(--danger);
    font-size:14px;
    font-weight:600;
}

.login-footer{
    text-align:center;
    color:#aaa;
    font-size:12px;
    margin-top:22px;
}


/* =========================================================
   ADMIN APP
========================================================= */

.admin-app{
    min-height:100vh;
}


/* =========================================================
   TOPBAR
========================================================= */

.topbar{
    position:sticky;
    top:0;
    z-index:1000;
    height:72px;
    padding:0 24px;
    background:var(--black);
    color:#fff;

    display:flex;
    align-items:center;
    justify-content:space-between;

    box-shadow:0 4px 20px rgba(0,0,0,.15);
}

.brand{
    font-size:23px;
    font-weight:800;
    letter-spacing:2px;
}

.brand-sub{
    font-size:11px;
    color:#999;
    margin-top:2px;
}

.logout-button{
    border:0;
    background:var(--gold);
    color:#111;
    border-radius:10px;
    padding:10px 16px;
    font-weight:800;
}

.logout-button:hover{
    background:#fff;
}


/* =========================================================
   MAIN
========================================================= */

.main{
    max-width:1250px;
    margin:auto;
    padding:28px 18px 60px;
}

.welcome{
    margin-bottom:24px;
}

.welcome h1{
    font-size:29px;
    margin-bottom:5px;
}

.welcome p{
    color:var(--muted);
}


/* =========================================================
   CONNECTION STATUS
========================================================= */

.connection-status{
    display:flex;
    align-items:center;
    gap:8px;

    padding:11px 14px;
    margin-bottom:20px;

    border-radius:11px;
    background:#fff;
    border:1px solid var(--border);

    font-size:13px;
}

.status-dot{
    width:9px;
    height:9px;
    border-radius:50%;
    background:#aaa;
}

.status-dot.connected{
    background:#16a34a;
}

.status-dot.disconnected{
    background:#dc2626;
}


/* =========================================================
   STATS
========================================================= */

.stats{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:15px;
    margin-bottom:24px;
}

.stat{
    background:#fff;
    border-radius:17px;
    padding:20px;
    box-shadow:var(--shadow);
    border:1px solid #eee;
}

.stat-label{
    color:var(--muted);
    font-size:14px;
}

.stat-value{
    display:block;
    margin-top:7px;
    font-size:29px;
    font-weight:800;
}


/* =========================================================
   MENU
========================================================= */

.menu{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:15px;
}

.menu-button{
    width:100%;
    border:1px solid #eee;
    border-radius:17px;
    background:#fff;
    padding:21px;
    text-align:right;
    box-shadow:var(--shadow);
    transition:.2s;
}

.menu-button:hover{
    transform:translateY(-3px);
    border-color:#ddd;
}

.menu-icon{
    display:block;
    font-size:29px;
    margin-bottom:10px;
}

.menu-title{
    display:block;
    font-size:18px;
    font-weight:800;
    margin-bottom:4px;
}

.menu-description{
    color:var(--muted);
    font-size:13px;
}


/* =========================================================
   CONTENT
========================================================= */

.content{
    margin-top:24px;
    background:#fff;
    border:1px solid #eee;
    border-radius:18px;
    padding:22px;
    box-shadow:var(--shadow);
}

.content-header{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:12px;
    margin-bottom:20px;
}

.content-header h2{
    font-size:22px;
}


/* =========================================================
   BUTTONS
========================================================= */

.primary-button{
    border:0;
    border-radius:10px;
    background:var(--black);
    color:#fff;
    padding:11px 17px;
    font-weight:800;
}

.primary-button:hover{
    background:var(--gold);
    color:#111;
}

.secondary-button{
    border:0;
    border-radius:10px;
    background:#eee;
    color:#222;
    padding:11px 17px;
    font-weight:700;
}

.secondary-button:hover{
    background:#ddd;
}

.danger-button{
    border:0;
    border-radius:10px;
    background:#111;
    color:#fff;
    padding:9px 13px;
    font-weight:700;
}

.danger-button:hover{
    background:#d00000;
}


/* =========================================================
   PRODUCTS
========================================================= */

.product-list{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:16px;
}

.product-card{
    overflow:hidden;
    border:1px solid #eee;
    border-radius:15px;
    background:#fff;
}

.product-placeholder{
    height:220px;
    background:#f0f0f0;

    display:flex;
    align-items:center;
    justify-content:center;

    color:#999;
    font-size:14px;
}

.product-image{
    width:100%;
    height:220px;
    object-fit:cover;
    display:block;
}

.product-info{
    padding:15px;
}

.product-name{
    font-size:17px;
    font-weight:800;
    margin-bottom:5px;
}

.product-category{
    color:var(--muted);
    font-size:13px;
    margin-bottom:10px;
}

.product-price{
    font-size:19px;
    font-weight:800;
}

.old-price{
    color:#999;
    text-decoration:line-through;
    font-size:14px;
    margin-right:5px;
}

.offer-badge{
    display:inline-block;
    margin-top:9px;
    padding:5px 8px;
    border-radius:7px;
    background:#fff3c4;
    color:#8a6b00;
    font-size:12px;
    font-weight:800;
}

.unavailable-badge{
    display:inline-block;
    margin-top:9px;
    padding:5px 8px;
    border-radius:7px;
    background:#ffe5e5;
    color:#b00000;
    font-size:12px;
    font-weight:800;
}

.product-actions{
    display:flex;
    gap:8px;
    margin-top:13px;
}

.product-actions button{
    flex:1;
}


/* =========================================================
   FORM
========================================================= */

.form{
    display:grid;
    gap:14px;
}

.form-group{
    display:grid;
    gap:7px;
}

.form-label{
    font-size:14px;
    font-weight:800;
}

.form input,
.form textarea,
.form select{
    width:100%;
    border:1px solid #ddd;
    border-radius:11px;
    padding:13px;
    outline:none;
    background:#fff;
    font-size:15px;
}

.form input:focus,
.form textarea:focus,
.form select:focus{
    border-color:var(--gold);
    box-shadow:0 0 0 3px rgba(212,175,55,.10);
}

.form textarea{
    min-height:120px;
    resize:vertical;
}

.form-row{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:14px;
}

.checkbox{
    display:flex;
    align-items:center;
    gap:8px;
    cursor:pointer;
}

.checkbox input{
    width:18px;
    height:18px;
    accent-color:#111;
}

.form-actions{
    display:flex;
    gap:10px;
    margin-top:5px;
}


/* =========================================================
   ORDERS
========================================================= */

.order-card{
    border:1px solid #eee;
    border-radius:14px;
    padding:16px;
    margin-bottom:12px;
}

.order-title{
    font-size:17px;
    font-weight:800;
}

.order-line{
    margin-top:6px;
    color:#666;
    font-size:14px;
}

.order-status{
    display:inline-block;
    margin-top:10px;
    padding:5px 10px;
    background:#eee;
    border-radius:8px;
    font-size:12px;
}


/* =========================================================
   EMPTY / LOADING
========================================================= */

.loading{
    padding:40px 15px;
    text-align:center;
    color:#777;
}

.empty{
    padding:45px 15px;
    text-align:center;
    color:#777;
}

.empty-icon{
    font-size:45px;
    margin-bottom:10px;
}


/* =========================================================
   TOAST
========================================================= */

.toast-container{
    position:fixed;
    left:20px;
    bottom:20px;
    z-index:5000;

    display:flex;
    flex-direction:column;
    gap:10px;
}

.toast{
    min-width:260px;
    max-width:380px;
    padding:14px 16px;
    border-radius:12px;
    background:#111;
    color:#fff;
    box-shadow:0 10px 35px rgba(0,0,0,.2);
    font-size:14px;
    animation:toastIn .2s ease;
}

.toast.success{
    border-right:4px solid #16a34a;
}

.toast.error{
    border-right:4px solid #dc2626;
}

@keyframes toastIn{
    from{
        transform:translateY(10px);
        opacity:0;
    }

    to{
        transform:translateY(0);
        opacity:1;
    }
}


/* =========================================================
   MOBILE
========================================================= */

@media(max-width:900px){

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

@media(max-width:600px){

    .topbar{
        height:65px;
        padding:0 13px;
    }

    .brand{
        font-size:19px;
    }

    .logout-button{
        padding:8px 11px;
        font-size:13px;
    }

    .main{
        padding:20px 12px 45px;
    }

    .welcome h1{
        font-size:24px;
    }

    .content{
        padding:15px;
    }

    .content-header{
        align-items:flex-start;
        flex-direction:column;
    }

    .content-header button{
        width:100%;
    }

    .menu{
        grid-template-columns:1fr;
    }

    .product-list{
        grid-template-columns:1fr;
    }

    .form-row{
        grid-template-columns:1fr;
    }

    .form-actions{
        flex-direction:column;
    }

    .form-actions button{
        width:100%;
    }

    .toast-container{
        left:12px;
        right:12px;
        bottom:12px;
    }

    .toast{
        min-width:0;
        width:100%;
    }

}

</style>
</head>


<body>


<!-- =========================================================
     LOGIN PAGE
========================================================= -->

<section id="loginPage" class="login-page">

    <div class="login-box">

        <div class="login-logo">
            ESPOZA <span class="gold">ADMIN</span>
        </div>

        <h1 class="login-title">
            لوحة التحكم
        </h1>

        <p class="login-description">
            تسجيل الدخول لإدارة متجر Espoza Fashion
        </p>

        <form id="loginForm">

            <div class="login-field">

                <input
                    id="password"
                    type="password"
                    placeholder="أدخل كلمة السر"
                    autocomplete="current-password"
                    required
                >

            </div>

            <button
                id="loginButton"
                class="login-button"
                type="submit"
            >
                دخول
            </button>

            <div
                id="loginError"
                class="login-error"
            ></div>

        </form>

        <div class="login-footer">
            Espoza Fashion Admin
        </div>

    </div>

</section>



<!-- =========================================================
     ADMIN APP
========================================================= -->

<div
    id="adminPage"
    class="admin-app hidden"
>

    <header class="topbar">

        <div>

            <div class="brand">
                ESPOZA <span class="gold">ADMIN</span>
            </div>

            <div class="brand-sub">
                إدارة متجر Espoza Fashion
            </div>

        </div>

        <button
            id="logoutButton"
            class="logout-button"
            type="button"
        >
            تسجيل الخروج
        </button>

    </header>


    <main class="main">

        <section class="welcome">

            <h1>
                أهلًا بك 👋
            </h1>

            <p>
                من هون بتتحكم بمتجر Espoza Fashion كامل.
            </p>

        </section>


        <!-- CONNECTION -->

        <div class="connection-status">

            <span
                id="connectionDot"
                class="status-dot disconnected"
            ></span>

            <span id="connectionText">
                جاري فحص الاتصال...
            </span>

        </div>


        <!-- STATS -->

        <section class="stats">

            <div class="stat">

                <span class="stat-label">
                    المنتجات
                </span>

                <strong
                    id="productsCount"
                    class="stat-value"
                >
                    0
                </strong>

            </div>


            <div class="stat">

                <span class="stat-label">
                    الطلبات
                </span>

                <strong
                    id="ordersCount"
                    class="stat-value"
                >
                    0
                </strong>

            </div>


            <div class="stat">

                <span class="stat-label">
                    العروض
                </span>

                <strong
                    id="offersCount"
                    class="stat-value"
                >
                    0
                </strong>

            </div>


            <div class="stat">

                <span class="stat-label">
                    حالة المتجر
                </span>

                <strong
                    id="storeStatus"
                    class="stat-value"
                >
                    فعال
                </strong>

            </div>

        </section>


        <!-- MENU -->

        <section class="menu">

            <button
                class="menu-button"
                type="button"
                onclick="showProducts()"
            >

                <span class="menu-icon">
                    👗
                </span>

                <span class="menu-title">
                    المنتجات
                </span>

                <span class="menu-description">
                    إضافة وتعديل وحذف المنتجات
                </span>

            </button>


            <button
                class="menu-button"
                type="button"
                onclick="showOrders()"
            >

                <span class="menu-icon">
                    🛍️
                </span>

                <span class="menu-title">
                    الطلبات
                </span>

                <span class="menu-description">
                    مشاهدة وإدارة طلبات الزبائن
                </span>

            </button>


            <button
                class="menu-button"
                type="button"
                onclick="showSlider()"
            >

                <span class="menu-icon">
                    🖼️
                </span>

                <span class="menu-title">
                    السلايدر
                </span>

                <span class="menu-description">
                    إدارة صور الواجهة الرئيسية
                </span>

            </button>


            <button
                class="menu-button"
                type="button"
                onclick="showAnnouncement()"
            >

                <span class="menu-icon">
                    📢
                </span>

                <span class="menu-title">
                    الإعلان العلوي
                </span>

                <span class="menu-description">
                    تعديل الإعلان أعلى الموقع
                </span>

            </button>


            <button
                class="menu-button"
                type="button"
                onclick="showSettings()"
            >

                <span class="menu-icon">
                    ⚙️
                </span>

                <span class="menu-title">
                    إعدادات المتجر
                </span>

                <span class="menu-description">
                    الواتساب والتوصيل والمعلومات
                </span>

            </button>


            <button
                class="menu-button"
                type="button"
                onclick="showSocial()"
            >

                <span class="menu-icon">
                    📱
                </span>

                <span class="menu-title">
                    السوشيال ميديا
                </span>

                <span class="menu-description">
                    الروابط وأعداد المتابعين
                </span>

            </button>

        </section>


        <!-- CONTENT -->

        <section
            id="content"
            class="content"
        >

            <div class="empty">

                <div class="empty-icon">
                    ⚙️
                </div>

                <h2>
                    اختر قسمًا للبدء
                </h2>

                <p style="margin-top:8px">
                    لوحة التحكم جاهزة لإدارة المتجر.
                </p>

            </div>

        </section>

    </main>

</div>


<!-- TOAST -->

<div
    id="toastContainer"
    class="toast-container"
></div>



<script>

/* =========================================================
   CONFIGURATION
========================================================= */

/*
    ضع هنا بيانات Supabase الخاصة بمشروعك.

    مهم:
    استخدم Publishable Key فقط.

    لا تستخدم:
    service_role
    secret key
*/

const SUPABASE_URL =
    "ضع Project URL هنا";

const SUPABASE_KEY =
    "ضع Publishable key هنا";


/*
    كلمة سر لوحة التحكم الحالية.
*/

const ADMIN_PASSWORD =
    "Espoza202900$";


/*
    اسم جلسة تسجيل الدخول.
*/

const LOGIN_STORAGE_KEY =
    "espoza_admin_logged";


/* =========================================================
   SUPABASE INITIALIZATION
========================================================= */

let supabaseClient = null;


/*
    نتأكد أولًا أن بيانات Supabase حقيقية.
*/

function initializeSupabase(){

    try{

        const validUrl =
            SUPABASE_URL &&
            SUPABASE_URL.startsWith("https://") &&
            !SUPABASE_URL.includes("ضع Project");

        const validKey =
            SUPABASE_KEY &&
            !SUPABASE_KEY.includes("ضع Publishable");

        if(!validUrl || !validKey){

            updateConnectionStatus(
                false,
                "Supabase غير مربوط بعد"
            );

            return false;
        }


        if(
            !window.supabase ||
            typeof window.supabase.createClient !== "function"
        ){

            updateConnectionStatus(
                false,
                "تعذر تحميل Supabase"
            );

            return false;
        }


        supabaseClient =
            window.supabase.createClient(
                SUPABASE_URL,
                SUPABASE_KEY
            );


        updateConnectionStatus(
            true,
            "تم تجهيز اتصال Supabase"
        );

        return true;

    }catch(error){

        console.error(
            "Supabase initialization error:",
            error
        );

        updateConnectionStatus(
            false,
            "خطأ في إعداد Supabase"
        );

        return false;
    }

}


/* =========================================================
   CONNECTION STATUS
========================================================= */

function updateConnectionStatus(
    connected,
    text
){

    const dot =
        document.getElementById("connectionDot");

    const label =
        document.getElementById("connectionText");


    if(!dot || !label){
        return;
    }


    dot.classList.remove(
        "connected",
        "disconnected"
    );


    dot.classList.add(
        connected
            ? "connected"
            : "disconnected"
    );


    label.textContent = text;

}


/* =========================================================
   TOAST
========================================================= */

function showToast(
    message,
    type="success"
){

    const container =
        document.getElementById(
            "toastContainer"
        );

    const toast =
        document.createElement("div");

    toast.className =
        "toast " + type;

    toast.textContent =
        message;

    container.appendChild(toast);


    setTimeout(
        ()=>{
            toast.remove();
        },
        3500
    );

}


/* =========================================================
   LOGIN
========================================================= */

function login(){

    const input =
        document.getElementById("password");

    const error =
        document.getElementById("loginError");

    const button =
        document.getElementById("loginButton");


    const password =
        input.value.trim();


    error.textContent = "";


    if(!password){

        error.textContent =
            "اكتب كلمة السر أولًا.";

        input.focus();

        return;
    }


    if(password !== ADMIN_PASSWORD){

        error.textContent =
            "كلمة السر غير صحيحة ❌";

        input.value = "";

        input.focus();

        return;
    }


    /*
        حفظ حالة تسجيل الدخول.
    */

    localStorage.setItem(
        LOGIN_STORAGE_KEY,
        "true"
    );


    button.disabled = true;

    button.textContent =
        "جاري الدخول...";


    setTimeout(
        ()=>{
            openAdmin();
        },
        150
    );

}


/* =========================================================
   OPEN ADMIN
========================================================= */

function openAdmin(){

    document
        .getElementById("loginPage")
        .classList.add("hidden");


    document
        .getElementById("adminPage")
        .classList.remove("hidden");


    initializeSupabase();

    loadDashboard();

}


/* =========================================================
   LOGOUT
========================================================= */

function logout(){

    localStorage.removeItem(
        LOGIN_STORAGE_KEY
    );

    location.reload();

}


/* =========================================================
   CHECK SESSION
========================================================= */

function checkLogin(){

    const logged =
        localStorage.getItem(
            LOGIN_STORAGE_KEY
        );


    if(logged === "true"){

        openAdmin();

    }

}


/* =========================================================
   REQUIRE SUPABASE
========================================================= */

function requireSupabase(){

    if(!supabaseClient){

        showToast(
            "اربط Supabase أولًا من أعلى الكود.",
            "error"
        );

        return false;
    }

    return true;

}


/* =========================================================
   DASHBOARD
========================================================= */

async function loadDashboard(){

    if(!supabaseClient){

        return;
    }


    try{

        /*
            PRODUCTS
        */

        const productsResult =
            await supabaseClient
                .from("products")
                .select("id,is_offer");


        if(productsResult.error){

            console.error(
                productsResult.error
            );

        }else{

            const products =
                productsResult.data || [];


            document
                .getElementById("productsCount")
                .textContent =
                    products.length;


            document
                .getElementById("offersCount")
                .textContent =
                    products.filter(
                        product =>
                            product.is_offer === true
                    ).length;

        }


        /*
            ORDERS
        */

        const ordersResult =
            await supabaseClient
                .from("orders")
                .select("id");


        if(ordersResult.error){

            console.error(
                ordersResult.error
            );

        }else{

            document
                .getElementById("ordersCount")
                .textContent =
                    (ordersResult.data || []).length;

        }


        updateConnectionStatus(
            true,
            "متصل بقاعدة البيانات"
        );


    }catch(error){

        console.error(error);

        updateConnectionStatus(
            false,
            "تعذر الاتصال بقاعدة البيانات"
        );

    }

}


/* =========================================================
   PRODUCTS PAGE
========================================================= */

async function showProducts(){

    const content =
        document.getElementById("content");


    content.innerHTML = `

        <div class="content-header">

            <h2>
                👗 المنتجات
            </h2>

            <button
                class="primary-button"
                type="button"
                onclick="addProduct()"
            >
                + إضافة منتج
            </button>

        </div>

        <div id="productList">
            <div class="loading">
                جاري تحميل المنتجات...
            </div>
        </div>

    `;


    await loadProducts();

}


/* =========================================================
   LOAD PRODUCTS
========================================================= */

async function loadProducts(){

    const box =
        document.getElementById(
            "productList"
        );


    if(!box){
        return;
    }


    if(!requireSupabase()){

        box.innerHTML = `

            <div class="empty">

                <div class="empty-icon">
                    🔌
                </div>

                <h3>
                    Supabase غير مربوط
                </h3>

                <p style="margin-top:8px">
                    ضع Project URL و Publishable Key
                    في بداية الكود.
                </p>

            </div>

        `;

        return;
    }


    const result =
        await supabaseClient
            .from("products")
            .select("*")
            .order(
                "created_at",
                {
                    ascending:false
                }
            );


    if(result.error){

        console.error(
            result.error
        );


        box.innerHTML = `

            <div class="empty">

                <div class="empty-icon">
                    ⚠️
                </div>

                <h3>
                    حدث خطأ
                </h3>

                <p style="margin-top:8px">
                    ${escapeHtml(
                        result.error.message
                    )}
                </p>

            </div>

        `;

        return;
    }


    const products =
        result.data || [];


    if(!products.length){

        box.innerHTML = `

            <div class="empty">

                <div class="empty-icon">
                    👗
                </div>

                <h3>
                    لا يوجد منتجات
                </h3>

                <p style="margin-top:8px">
                    اضغط إضافة منتج لبدء إضافة منتجات Espoza.
                </p>

            </div>

        `;

        return;
    }


    box.className =
        "product-list";


    box.innerHTML =
        products
            .map(
                product =>
                    renderProductCard(product)
            )
            .join("");

}


/* =========================================================
   PRODUCT CARD
========================================================= */

function renderProductCard(product){

    const name =
        escapeHtml(
            product.name ||
            "بدون اسم"
        );


    const category =
        escapeHtml(
            product.category ||
            ""
        );


    const price =
        Number(product.price || 0);


    const oldPrice =
        Number(product.old_price || 0);


    const image =
        product.image_url ||
        product.main_image ||
        "";


    let imageHTML;


    if(image){

        imageHTML = `

            <img
                class="product-image"
                src="${escapeAttr(image)}"
                alt="${escapeAttr(name)}"
                loading="lazy"
                onerror="this.outerHTML='<div class=&quot;product-placeholder&quot;>الصورة غير متوفرة</div>'"
            >

        `;

    }else{

        imageHTML = `

            <div class="product-placeholder">
                لا توجد صورة
            </div>

        `;

    }


    let badges = "";


    if(product.is_offer === true){

        badges += `
            <span class="offer-badge">
                عرض
            </span>
        `;

    }


    if(product.is_available === false){

        badges += `
            <span class="unavailable-badge">
                غير متوفر
            </span>
        `;

    }


    return `

        <article class="product-card">

            ${imageHTML}

            <div class="product-info">

                <h3 class="product-name">
                    ${name}
                </h3>

                <div class="product-category">
                    ${category}
                </div>

                <div class="product-price">

                    ${price} ₪

                    ${
                        oldPrice
                            ? `
                                <span class="old-price">
                                    ${oldPrice} ₪
                                </span>
                              `
                            : ""
                    }

                </div>

                ${badges}

                <div class="product-actions">

                    <button
                        class="secondary-button"
                        type="button"
                        onclick="editProduct('${escapeAttr(product.id)}')"
                    >
                        تعديل
                    </button>

                    <button
                        class="danger-button"
                        type="button"
                        onclick="deleteProduct('${escapeAttr(product.id)}')"
                    >
                        حذف
                    </button>

                </div>

            </div>

        </article>

    `;

}


/* =========================================================
   ADD PRODUCT
========================================================= */

function addProduct(){

    const content =
        document.getElementById(
            "content"
        );


    content.innerHTML = `

        <div class="content-header">

            <h2>
                ➕ إضافة منتج
            </h2>

        </div>


        <form
            id="productForm"
            class="form"
        >

            <div class="form-group">

                <label class="form-label">
                    اسم المنتج
                </label>

                <input
                    id="productName"
                    type="text"
                    placeholder="مثال: فستان ليان"
                    required
                >

            </div>


            <div class="form-group">

                <label class="form-label">
                    الوصف
                </label>

                <textarea
                    id="productDescription"
                    placeholder="اكتب وصف المنتج"
                ></textarea>

            </div>


            <div class="form-row">

                <div class="form-group">

                    <label class="form-label">
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

                </div>


                <div class="form-group">

                    <label class="form-label">
                        SKU
                    </label>

                    <input
                        id="productSku"
                        type="text"
                        placeholder="ESP-001"
                    >

                </div>

            </div>


            <div class="form-row">

                <div class="form-group">

                    <label class="form-label">
                        السعر
                    </label>

                    <input
                        id="productPrice"
                        type="number"
                        min="0"
                        step="0.01"
                        placeholder="250"
                        required
                    >

                </div>


                <div class="form-group">

                    <label class="form-label">
                        السعر القديم
                    </label>

                    <input
                        id="productOldPrice"
                        type="number"
                        min="0"
                        step="0.01"
                        placeholder="300"
                    >

                </div>

            </div>


            <label class="checkbox">

                <input
                    id="productOffer"
                    type="checkbox"
                >

                <span>
                    المنتج ضمن العروضات
                </span>

            </label>


            <label class="checkbox">

                <input
                    id="productAvailable"
                    type="checkbox"
                    checked
                >

                <span>
                    المنتج متوفر
                </span>

            </label>


            <div class="form-actions">

                <button
                    class="primary-button"
                    type="submit"
                >
                    حفظ المنتج
                </button>

                <button
                    class="secondary-button"
                    type="button"
                    onclick="showProducts()"
                >
                    إلغاء
                </button>

            </div>

        </form>

    `;


    document
        .getElementById("productForm")
        .addEventListener(
            "submit",
            saveProduct
        );

}


/* =========================================================
   SAVE PRODUCT
========================================================= */

async function saveProduct(event){

    event.preventDefault();


    if(!requireSupabase()){
        return;
    }


    const name =
        document
            .getElementById("productName")
            .value
            .trim();


    const description =
        document
            .getElementById("productDescription")
            .value
            .trim();


    const category =
        document
            .getElementById("productCategory")
            .value;


    const price =
        Number(
            document
                .getElementById("productPrice")
                .value
        );


    const oldPriceValue =
        document
            .getElementById("productOldPrice")
            .value;


    const oldPrice =
        oldPriceValue
            ? Number(oldPriceValue)
            : null;


    const sku =
        document
            .getElementById("productSku")
            .value
            .trim() || null;


    const isOffer =
        document
            .getElementById("productOffer")
            .checked;


    const isAvailable =
        document
            .getElementById("productAvailable")
            .checked;


    const product = {

        name,
        description,
        category,
        price,
        old_price:oldPrice,
        sku,
        is_offer:isOffer,
        is_available:isAvailable

    };


    const result =
        await supabaseClient
            .from("products")
            .insert(product);


    if(result.error){

        console.error(
            result.error
        );

        showToast(
            result.error.message,
            "error"
        );

        return;
    }


    showToast(
        "تم إضافة المنتج بنجاح ✅",
        "success"
    );


    await loadDashboard();

    await showProducts();

}


/* =========================================================
   EDIT PRODUCT
========================================================= */

async function editProduct(id){

    if(!requireSupabase()){
        return;
    }


    const result =
        await supabaseClient
            .from("products")
            .select("*")
            .eq("id",id)
            .single();


    if(result.error){

        showToast(
            result.error.message,
            "error"
        );

        return;
    }


    const product =
        result.data;


    const content =
        document.getElementById(
            "content"
        );


    content.innerHTML = `

        <div class="content-header">

            <h2>
                ✏️ تعديل المنتج
            </h2>

        </div>


        <form
            id="productEditForm"
            class="form"
        >

            <div class="form-group">

                <label class="form-label">
                    اسم المنتج
                </label>

                <input
                    id="productName"
                    value="${escapeAttr(product.name || "")}"
                    required
                >

            </div>


            <div class="form-group">

                <label class="form-label">
                    الوصف
                </label>

                <textarea
                    id="productDescription"
                >${escapeHtml(product.description || "")}</textarea>

            </div>


            <div class="form-row">

                <div class="form-group">

                    <label class="form-label">
                        التصنيف
                    </label>

                    <select id="productCategory">

                        <option
                            value="dresses"
                            ${product.category === "dresses" ? "selected" : ""}
                        >
                            فساتين
                        </option>

                        <option
                            value="sets"
                            ${product.category === "sets" ? "selected" : ""}
                        >
                            أطقم
                        </option>

                        <option
                            value="offers"
                            ${product.category === "offers" ? "selected" : ""}
                        >
                            العروضات
                        </option>

                    </select>

                </div>


                <div class="form-group">

                    <label class="form-label">
                        SKU
                    </label>

                    <input
                        id="productSku"
                        value="${escapeAttr(product.sku || "")}"
                    >

                </div>

            </div>


            <div class="form-row">

                <div class="form-group">

                    <label class="form-label">
                        السعر
                    </label>

                    <input
                        id="productPrice"
                        type="number"
                        min="0"
                        step="0.01"
                        value="${Number(product.price || 0)}"
                        required
                    >

                </div>


                <div class="form-group">

                    <label class="form-label">
                        السعر القديم
                    </label>

                    <input
                        id="productOldPrice"
                        type="number"
                        min="0"
                        step="0.01"
                        value="${product.old_price ?? ""}"
                    >

                </div>

            </div>


            <label class="checkbox">

                <input
                    id="productOffer"
                    type="checkbox"
                    ${product.is_offer ? "checked" : ""}
                >

                <span>
                    المنتج ضمن العروضات
                </span>

            </label>


            <label class="checkbox">

                <input
                    id="productAvailable"
                    type="checkbox"
                    ${product.is_available !== false ? "checked" : ""}
                >

                <span>
                    المنتج متوفر
                </span>

            </label>


            <div class="form-actions">

                <button
                    class="primary-button"
                    type="submit"
                >
                    حفظ التعديل
                </button>

                <button
                    class="secondary-button"
                    type="button"
                    onclick="showProducts()"
                >
                    إلغاء
                </button>

            </div>

        </form>

    `;


    document
        .getElementById("productEditForm")
        .addEventListener(
            "submit",
            event =>
                updateProduct(
                    event,
                    id
                )
        );

}


/* =========================================================
   UPDATE PRODUCT
========================================================= */

async function updateProduct(
    event,
    id
){

    event.preventDefault();


    if(!requireSupabase()){
        return;
    }


    const update = {

        name:
            document
                .getElementById("productName")
                .value
                .trim(),

        description:
            document
                .getElementById("productDescription")
                .value
                .trim(),

        category:
            document
                .getElementById("productCategory")
                .value,

        price:
            Number(
                document
                    .getElementById("productPrice")
                    .value
            ),

        old_price:
            document
                .getElementById("productOldPrice")
                .value
                ?
                Number(
                    document
                        .getElementById("productOldPrice")
                        .value
                )
                :
                null,

        sku:
            document
                .getElementById("productSku")
                .value
                .trim() || null,

        is_offer:
            document
                .getElementById("productOffer")
                .checked,

        is_available:
            document
                .getElementById("productAvailable")
                .checked,

        updated_at:
            new Date().toISOString()

    };


    const result =
        await supabaseClient
            .from("products")
            .update(update)
            .eq("id",id);


    if(result.error){

        console.error(
            result.error
        );

        showToast(
            result.error.message,
            "error"
        );

        return;
    }


    showToast(
        "تم تعديل المنتج بنجاح ✅",
        "success"
    );


    await loadDashboard();

    await showProducts();

}


/* =========================================================
   DELETE PRODUCT
========================================================= */

async function deleteProduct(id){

    if(!requireSupabase()){
        return;
    }


    const confirmed =
        confirm(
            "هل أنت متأكد من حذف هذا المنتج؟\n\nلا يمكن التراجع عن الحذف."
        );


    if(!confirmed){
        return;
    }


    const result =
        await supabaseClient
            .from("products")
            .delete()
            .eq("id",id);


    if(result.error){

        console.error(
            result.error
        );

        showToast(
            result.error.message,
            "error"
        );

        return;
    }


    showToast(
        "تم حذف المنتج 🗑️",
        "success"
    );


    await loadDashboard();

    await showProducts();

}


/* =========================================================
   ORDERS
========================================================= */

async function showOrders(){

    const content =
        document.getElementById(
            "content"
        );


    content.innerHTML = `

        <div class="content-header">

            <h2>
                🛍️ الطلبات
            </h2>

            <button
                class="secondary-button"
                type="button"
                onclick="showOrders()"
            >
                تحديث
            </button>

        </div>


        <div id="ordersList">

            <div class="loading">
                جاري تحميل الطلبات...
            </div>

        </div>

    `;


    if(!requireSupabase()){
        return;
    }


    const result =
        await supabaseClient
            .from("orders")
            .select("*")
            .order(
                "created_at",
                {
                    ascending:false
                }
            );


    const box =
        document.getElementById(
            "ordersList"
        );


    if(result.error){

        box.innerHTML = `

            <div class="empty">

                <div class="empty-icon">
                    ⚠️
                </div>

                <h3>
                    حدث خطأ
                </h3>

                <p style="margin-top:8px">
                    ${escapeHtml(
                        result.error.message
                    )}
                </p>

            </div>

        `;

        return;
    }


    const orders =
        result.data || [];


    if(!orders.length){

        box.innerHTML = `

            <div class="empty">

                <div class="empty-icon">
                    🛍️
                </div>

                <h3>
                    لا توجد طلبات حتى الآن
                </h3>

            </div>

        `;

        return;
    }


    box.innerHTML =
        orders
            .map(
                order =>
                    `

                    <div class="order-card">

                        <div class="order-title">
                            ${escapeHtml(
                                order.customer_name ||
                                "زبون"
                            )}
                        </div>

                        <div class="order-line">
                            📞 ${escapeHtml(
                                order.phone || ""
                            )}
                        </div>

                        <div class="order-line">
                            📍 ${escapeHtml(
                                order.region || ""
                            )}
                        </div>

                        <div class="order-line">
                            📦 ${escapeHtml(
                                order.product_name || ""
                            )}
                        </div>

                        <div class="order-line">
                            💰 ${Number(
                                order.total_price || 0
                            )} ₪
                        </div>

                        <span class="order-status">
                            ${escapeHtml(
                                order.status ||
                                "new"
                            )}
                        </span>

                    </div>

                    `
            )
            .join("");

}


/* =========================================================
   SLIDER
========================================================= */

function showSlider(){

    document
        .getElementById("content")
        .innerHTML = `

        <div class="content-header">

            <h2>
                🖼️ السلايدر
            </h2>

        </div>

        <div class="empty">

            <div class="empty-icon">
                🖼️
            </div>

            <h3>
                إدارة السلايدر
            </h3>

            <p style="margin-top:8px">
                سيتم ربط صور السلايدر بقاعدة البيانات
                في الخطوة التالية.
            </p>

        </div>

    `;

}


/* =========================================================
   ANNOUNCEMENT
========================================================= */

function showAnnouncement(){

    document
        .getElementById("content")
        .innerHTML = `

        <div class="content-header">

            <h2>
                📢 الإعلان العلوي
            </h2>

        </div>

        <div class="empty">

            <div class="empty-icon">
                📢
            </div>

            <h3>
                الإعلان العلوي
            </h3>

            <p style="margin-top:8px">
                سيتم ربطه بقاعدة البيانات
                في الخطوة التالية.
            </p>

        </div>

    `;

}


/* =========================================================
   SETTINGS
========================================================= */

function showSettings(){

    document
        .getElementById("content")
        .innerHTML = `

        <div class="content-header">

            <h2>
                ⚙️ إعدادات المتجر
            </h2>

        </div>

        <div class="empty">

            <div class="empty-icon">
                ⚙️
            </div>

            <h3>
                إعدادات المتجر
            </h3>

            <p style="margin-top:8px">
                سيتم ربط إعدادات المتجر
                بقاعدة البيانات في الخطوة التالية.
            </p>

        </div>

    `;

}


/* =========================================================
   SOCIAL
========================================================= */

function showSocial(){

    document
        .getElementById("content")
        .innerHTML = `

        <div class="content-header">

            <h2>
                📱 السوشيال ميديا
            </h2>

        </div>

        <div class="empty">

            <div class="empty-icon">
                📱
            </div>

            <h3>
                السوشيال ميديا
            </h3>

            <p style="margin-top:8px">
                سيتم ربط الروابط وأعداد المتابعين
                بقاعدة البيانات في الخطوة التالية.
            </p>

        </div>

    `;

}


/* =========================================================
   SECURITY HELPERS
========================================================= */

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


/* =========================================================
   EVENTS
========================================================= */

document
    .getElementById("loginForm")
    .addEventListener(
        "submit",
        function(event){

            event.preventDefault();

            login();

        }
    );


document
    .getElementById("logoutButton")
    .addEventListener(
        "click",
        logout
    );


/* =========================================================
   START APPLICATION
========================================================= */

document.addEventListener(
    "DOMContentLoaded",
    function(){

        const password =
            document.getElementById(
                "password"
            );


        if(
            !localStorage.getItem(
                LOGIN_STORAGE_KEY
            )
        ){

            password.focus();

        }


        checkLogin();

    }
);

</script>

</body>
</html>
