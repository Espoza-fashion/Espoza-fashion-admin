<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Espoza Fashion — لوحة التحكم</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;500;600;700&family=Markazi+Text:wght@500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --wine:#641f34;
    --wine-dark:#4a1626;
    --cream:#faf6f3;
    --ink:#2b2320;
    --ink-soft:#6b5f5a;
    --line:#e7ddd7;
    --green:#2f9e57;
    --red:#c0392b;
    --card:#ffffff;
    --radius:10px;
  }

  *{box-sizing:border-box;}

  body{
    margin:0;
    font-family:'Cairo',sans-serif;
    background:var(--cream);
    color:var(--ink);
  }

  .hidden{display:none !important;}

  /* ---------- Toast ---------- */
  .toast{
    position:fixed;
    bottom:24px;
    left:50%;
    transform:translateX(-50%) translateY(20px);
    background:var(--ink);
    color:#fff;
    padding:12px 20px;
    border-radius:8px;
    font-size:14px;
    opacity:0;
    pointer-events:none;
    transition:opacity .25s ease, transform .25s ease;
    z-index:9999;
    max-width:90vw;
    text-align:center;
  }
  .toast.show{opacity:1; transform:translateX(-50%) translateY(0);}

  /* ---------- Shared form elements ---------- */
  .field{
    width:100%;
    padding:11px 13px;
    border:1px solid var(--line);
    border-radius:8px;
    font-family:inherit;
    font-size:14px;
    background:#fff;
    color:var(--ink);
  }
  .field:focus{outline:2px solid var(--wine); outline-offset:1px;}

  label{
    display:block;
    font-size:13px;
    color:var(--ink-soft);
    margin:14px 0 6px;
  }

  .btn{
    border:none;
    border-radius:8px;
    padding:11px 18px;
    font-family:inherit;
    font-size:14px;
    font-weight:600;
    cursor:pointer;
    transition:opacity .15s ease;
  }
  .btn:hover{opacity:.88;}
  .btn:disabled{opacity:.6; cursor:default;}
  .btn-primary{background:var(--wine); color:#fff;}
  .btn-soft{background:#f1e6e2; color:var(--wine-dark);}
  .btn-danger{background:#fbeaea; color:var(--red);}
  .btn-ghost{background:transparent; color:var(--ink-soft); border:1px solid var(--line);}
  .btn-block{width:100%; margin-top:18px;}

  .error-text{color:var(--red); font-size:13px; min-height:18px; margin-top:6px;}

  /* ---------- Login ---------- */
  .login-screen{
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:20px;
  }
  .login-card{
    width:100%;
    max-width:360px;
    background:var(--card);
    border:1px solid var(--line);
    border-radius:var(--radius);
    padding:36px 28px;
  }
  .brand{
    font-family:'Markazi Text',serif;
    font-size:30px;
    font-weight:700;
    color:var(--wine);
    letter-spacing:.5px;
    text-align:center;
  }
  .brand span{
    display:block;
    font-family:'Cairo',sans-serif;
    font-size:12px;
    font-weight:600;
    letter-spacing:3px;
    color:var(--ink-soft);
    margin-top:2px;
  }

  /* ---------- App shell ---------- */
  .app{
    display:flex;
    min-height:100vh;
  }

  .sidebar{
    width:230px;
    flex-shrink:0;
    background:var(--wine-dark);
    color:#f3e8e4;
    display:flex;
    flex-direction:column;
    padding:22px 16px;
  }
  .sidebar .brand{color:#fff; margin-bottom:26px;}
  .sidebar .brand span{color:#d8b9c0;}

  .nav{
    display:block;
    width:100%;
    text-align:right;
    background:transparent;
    border:none;
    color:#e9d7d3;
    font-family:inherit;
    font-size:14px;
    padding:11px 14px;
    border-radius:8px;
    cursor:pointer;
    margin-bottom:4px;
  }
  .nav:hover{background:rgba(255,255,255,.06);}
  .nav.active{background:#fff; color:var(--wine-dark); font-weight:700;}

  .logout-btn{margin-top:auto;}

  .main{
    flex:1;
    min-width:0;
    padding:26px 30px 60px;
  }

  .topbar h1{
    font-size:22px;
    margin:0 0 22px;
  }

  .page{display:none;}
  .page.active{display:block;}

  /* ---------- Dashboard ---------- */
  .stats-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(150px,1fr));
    gap:14px;
  }
  .stat-card{
    background:var(--card);
    border:1px solid var(--line);
    border-right:4px solid var(--wine);
    border-radius:var(--radius);
    padding:18px;
  }
  .stat-card span{display:block; font-size:28px; font-weight:700; color:var(--wine-dark);}
  .stat-card small{color:var(--ink-soft);}

  /* ---------- Toolbar ---------- */
  .toolbar{
    display:flex;
    gap:10px;
    margin-bottom:18px;
    flex-wrap:wrap;
  }
  .toolbar .field{flex:1; min-width:160px;}
  .toolbar select.field{flex:0 0 160px;}

  /* ---------- Products grid ---------- */
  .products-grid{
    display:grid;
    grid-template-columns:repeat(auto-fill,minmax(190px,1fr));
    gap:16px;
  }
  .product{
    background:var(--card);
    border:1px solid var(--line);
    border-radius:var(--radius);
    overflow:hidden;
  }
  .product img{width:100%; aspect-ratio:4/5; object-fit:cover; display:block; background:#f1e9e5;}
  .product-body{padding:12px;}
  .product-title{font-weight:600; margin-bottom:8px; font-size:14px;}
  .row-between{display:flex; justify-content:space-between; align-items:flex-start;}
  .price{color:var(--wine); font-weight:700;}
  .old{color:#a99; text-decoration:line-through; font-size:12px;}
  .actions{display:flex; gap:8px; margin-top:12px;}
  .actions .btn{flex:1; padding:9px; font-size:13px;}
  .empty{color:var(--ink-soft); padding:30px; text-align:center;}

  /* ---------- Table ---------- */
  .table-wrap{
    background:var(--card);
    border:1px solid var(--line);
    border-radius:var(--radius);
    overflow-x:auto;
  }
  table{width:100%; border-collapse:collapse; font-size:13px;}
  th,td{padding:12px 14px; text-align:right; border-bottom:1px solid var(--line); white-space:nowrap;}
  th{color:var(--ink-soft); font-weight:600;}

  /* ---------- Card form (slider / settings) ---------- */
  .card-form{
    background:var(--card);
    border:1px solid var(--line);
    border-radius:var(--radius);
    padding:20px;
    max-width:480px;
    margin-bottom:20px;
  }

  /* ---------- Slider list ---------- */
  .slider-list{display:flex; flex-direction:column; gap:10px;}
  .slider-item{
    display:flex;
    gap:14px;
    align-items:center;
    background:var(--card);
    border:1px solid var(--line);
    border-radius:var(--radius);
    padding:10px;
  }
  .slider-preview{width:70px; height:70px; border-radius:8px; object-fit:cover; flex-shrink:0; background:#f1e9e5;}
  .slider-preview.empty{display:flex; align-items:center; justify-content:center; font-size:11px; color:var(--ink-soft); padding:0;}
  .slider-info{flex:1; font-size:13px;}
  .slider-actions{margin-top:6px;}

  /* ---------- Delivery ---------- */
  .delivery-list{background:var(--card); border:1px solid var(--line); border-radius:var(--radius); overflow:hidden;}
  .setting-row{display:flex; justify-content:space-between; padding:14px 18px; border-bottom:1px solid var(--line); font-size:14px;}
  .setting-row:last-child{border-bottom:none;}

  /* ---------- Checkbox row ---------- */
  .check-row{display:flex; align-items:center; gap:8px; margin-top:14px;}
  .check-row label{margin:0; color:var(--ink);}

  /* ---------- Modal ---------- */
  .modal{
    display:none;
    position:fixed;
    inset:0;
    background:rgba(43,35,32,.5);
    align-items:flex-start;
    justify-content:center;
    padding:30px 16px;
    overflow-y:auto;
    z-index:500;
  }
  .modal.open{display:flex;}
  .modal-box{
    background:#fff;
    border-radius:var(--radius);
    width:100%;
    max-width:560px;
    padding:24px;
  }
  .modal-head{display:flex; justify-content:space-between; align-items:center;}
  .modal-head h2{margin:0; font-size:19px;}
  .modal-close{
    background:none; border:none; font-size:22px; line-height:1;
    cursor:pointer; color:var(--ink-soft);
  }

  .images-list{display:flex; flex-direction:column; gap:10px; margin:14px 0;}
  .image-editor{
    display:flex; align-items:center; gap:12px;
    border:1px solid var(--line); border-radius:8px; padding:8px;
  }
  .image-editor img{width:56px; height:56px; object-fit:cover; border-radius:6px; flex-shrink:0; background:#f1e9e5;}
  .image-editor > div{flex:1;}
  .tiny{font-size:11px; color:var(--ink-soft); margin-top:4px;}

  @media(max-width:820px){
    .app{flex-direction:column;}
    .sidebar{width:100%; flex-direction:row; align-items:center; overflow-x:auto; padding:12px;}
    .sidebar .brand{display:none;}
    .nav{white-space:nowrap; margin-bottom:0;}
    .logout-btn{margin-top:0;}
    .main{padding:18px;}
  }
</style>
</head>
<body>

<div id="toast" class="toast"></div>

<!-- ============ LOGIN ============ -->
<div id="loginScreen" class="login-screen">
  <div class="login-card">
    <div class="brand">ESPOZA<span>ADMIN PANEL</span></div>
    <form id="loginForm">
      <label for="loginEmail">البريد الإلكتروني</label>
      <input id="loginEmail" class="field" type="email" autocomplete="username" required>

      <label for="loginPassword">كلمة المرور</label>
      <input id="loginPassword" class="field" type="password" autocomplete="current-password" required>

      <div id="loginError" class="error-text"></div>

      <button type="submit" class="btn btn-primary btn-block">دخول لوحة التحكم</button>
    </form>
  </div>
</div>

<!-- ============ APP ============ -->
<div id="app" class="app hidden">

  <aside class="sidebar">
    <div class="brand">ESPOZA<span>ADMIN PANEL</span></div>

    <nav>
      <button type="button" class="nav active" data-page="dashboard">الرئيسية</button>
      <button type="button" class="nav" data-page="products">المنتجات</button>
      <button type="button" class="nav" data-page="orders">الطلبات</button>
      <button type="button" class="nav" data-page="slides">السلايدر</button>
      <button type="button" class="nav" data-page="delivery">التوصيل</button>
      <button type="button" class="nav" data-page="settings">إعدادات المتجر</button>
    </nav>

    <button id="logoutBtn" type="button" class="btn btn-ghost logout-btn">تسجيل الخروج</button>
  </aside>

  <main class="main">
    <header class="topbar">
      <h1 id="pageTitle">الرئيسية</h1>
    </header>

    <!-- Dashboard -->
    <section id="page-dashboard" class="page active">
      <div class="stats-grid">
        <div class="stat-card"><span id="statProducts">0</span><small>عدد المنتجات</small></div>
        <div class="stat-card"><span id="statOffers">0</span><small>عروضات نشطة</small></div>
        <div class="stat-card"><span id="statOrders">0</span><small>الطلبات</small></div>
        <div class="stat-card"><span id="statSlides">0</span><small>شرائح فعّالة</small></div>
      </div>
    </section>

    <!-- Products -->
    <section id="page-products" class="page">
      <div class="toolbar">
        <input id="productSearch" class="field" placeholder="ابحث بالاسم أو رمز المنتج...">
        <select id="productCategoryFilter" class="field">
          <option value="all">كل الأصناف</option>
          <option value="dresses">فساتين</option>
          <option value="sets">أطقم</option>
          <option value="offers">عروضات</option>
        </select>
        <button type="button" class="btn btn-primary" onclick="openProductModal()">+ إضافة منتج</button>
      </div>
      <div id="productsGrid" class="products-grid"></div>
    </section>

    <!-- Orders -->
    <section id="page-orders" class="page">
      <div class="table-wrap">
        <table>
          <thead>
            <tr>
              <th>الاسم</th><th>الهاتف</th><th>المنتج</th><th>الخيارات</th>
              <th>الإجمالي</th><th>الحالة</th><th>التاريخ</th><th></th>
            </tr>
          </thead>
          <tbody id="ordersBody"></tbody>
        </table>
      </div>
    </section>

    <!-- Slider -->
    <section id="page-slides" class="page">
      <form id="sliderForm" class="card-form">
        <label for="sliderTitle">عنوان الشريحة</label>
        <input id="sliderTitle" class="field" placeholder="مثال: تشكيلة الصيف">

        <label for="sliderSubtitle">نص فرعي (اختياري)</label>
        <input id="sliderSubtitle" class="field">

        <label for="sliderOrder">ترتيب الظهور</label>
        <input id="sliderOrder" class="field" type="number" value="0">

        <label for="sliderImage">الصورة</label>
        <input id="sliderImage" type="file" accept="image/*">

        <button type="submit" class="btn btn-primary btn-block">إضافة للسلايدر</button>
      </form>

      <div id="sliderList" class="slider-list"></div>
    </section>

    <!-- Delivery -->
    <section id="page-delivery" class="page">
      <div id="deliveryList" class="delivery-list"></div>
    </section>

    <!-- Settings -->
    <section id="page-settings" class="page">
      <form id="settingsForm" class="card-form">
        <label for="setWhatsapp">رقم واتساب المتجر</label>
        <input id="setWhatsapp" class="field" placeholder="9705xxxxxxxx">

        <label for="setWestBank">سعر التوصيل — الضفة الغربية (₪)</label>
        <input id="setWestBank" class="field" type="number">

        <label for="setJerusalem">سعر التوصيل — القدس (₪)</label>
        <input id="setJerusalem" class="field" type="number">

        <label for="setInside">سعر التوصيل — الداخل (₪)</label>
        <input id="setInside" class="field" type="number">

        <label for="setFacebook">متابعين فيسبوك</label>
        <input id="setFacebook" class="field" type="number">

        <label for="setInstagram">متابعين انستغرام</label>
        <input id="setInstagram" class="field" type="number">

        <label for="setTikTok">متابعين تيك توك</label>
        <input id="setTikTok" class="field" type="number">

        <label for="setSnapchat">متابعين سناب شات</label>
        <input id="setSnapchat" class="field" type="number">

        <button type="submit" class="btn btn-primary btn-block">حفظ الإعدادات</button>
      </form>
    </section>
  </main>
</div>

<!-- ============ PRODUCT MODAL ============ -->
<div id="productModal" class="modal">
  <div class="modal-box">
    <div class="modal-head">
      <h2 id="productModalTitle">إضافة منتج</h2>
      <button type="button" class="modal-close" onclick="closeProductModal()">×</button>
    </div>

    <form id="productForm">
      <input type="hidden" id="productId">

      <label for="productName">اسم المنتج</label>
      <input id="productName" class="field" required>

      <label for="productSku">رمز المنتج (SKU) — اختياري</label>
      <input id="productSku" class="field">

      <label for="productCategory">التصنيف</label>
      <select id="productCategory" class="field">
        <option value="dresses">فساتين</option>
        <option value="sets">أطقم</option>
        <option value="offers">عروضات</option>
      </select>

      <label for="productPrice">السعر (₪)</label>
      <input id="productPrice" class="field" type="number" step="0.01" required>

      <label for="productOldPrice">السعر القديم (اختياري)</label>
      <input id="productOldPrice" class="field" type="number" step="0.01">

      <label for="productDescription">الوصف</label>
      <textarea id="productDescription" class="field" rows="3"></textarea>

      <label for="productSizes">المقاسات (افصل بينها بفاصلة)</label>
      <input id="productSizes" class="field" placeholder="S, M, L, XL">

      <label>صور المنتج</label>
      <div id="productImagesList" class="images-list"></div>
      <input id="productImagesInput" type="file" accept="image/*" multiple>

      <div class="check-row">
        <input type="checkbox" id="productOffer">
        <label for="productOffer">عرض خاص</label>
      </div>
      <div class="check-row">
        <input type="checkbox" id="productAvailable" checked>
        <label for="productAvailable">متوفر للطلب</label>
      </div>
      <div class="check-row">
        <input type="checkbox" id="productActive" checked>
        <label for="productActive">ظاهر في المتجر</label>
      </div>

      <button type="submit" class="btn btn-primary btn-block">حفظ المنتج</button>
    </form>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
<script src="admin-fixed.js"></script>
</body>
</html>
