
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>浪貓不浪 🐾 中途之家</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Noto+Sans+TC:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  :root {
    --pink-light:#ffd6e7;--pink-mid:#ffb3d1;--pink-strong:#ff85b3;--pink-deep:#e8699a;
    --blue-light:#d0e8ff;--blue-mid:#a8d4ff;--blue-strong:#7ab8f5;--blue-deep:#4a90d9;
    --lavender:#e8d5ff;--cream:#fff9f5;
    --text-dark:#3d2c3f;--text-mid:#6b4f72;--text-soft:#9e7ea8;
    --shadow-card:0 4px 20px rgba(120,100,160,0.12);
    --radius:24px;--radius-sm:14px;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  body{font-family:'Noto Sans TC',sans-serif;background:var(--cream);color:var(--text-dark);min-height:100vh;overflow-x:hidden;}
  body::before{content:'';position:fixed;top:0;left:0;right:0;bottom:0;
    background:radial-gradient(ellipse at 15% 20%,rgba(255,180,210,.28) 0%,transparent 50%),
               radial-gradient(ellipse at 85% 10%,rgba(168,212,255,.28) 0%,transparent 50%),
               radial-gradient(ellipse at 50% 80%,rgba(232,213,255,.22) 0%,transparent 50%),
               radial-gradient(ellipse at 80% 70%,rgba(255,180,210,.18) 0%,transparent 40%);
    pointer-events:none;z-index:0;}

  /* HEADER */
  header{position:relative;z-index:10;text-align:center;padding:44px 20px 32px;
    background:linear-gradient(160deg,rgba(255,213,231,.6) 0%,rgba(208,232,255,.6) 100%);
    backdrop-filter:blur(12px);border-bottom:1px solid rgba(255,180,210,.3);}
  .header-paws{font-size:2rem;letter-spacing:8px;margin-bottom:12px;animation:float 3s ease-in-out infinite;}
  @keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-6px)}}
  header h1{font-family:'Nunito',sans-serif;font-size:clamp(1.9rem,6vw,3.2rem);font-weight:900;
    background:linear-gradient(135deg,var(--pink-deep) 0%,var(--blue-deep) 100%);
    -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1.2;margin-bottom:10px;}
  header p{color:var(--text-mid);font-size:1.02rem;font-weight:500;margin-bottom:22px;}
  .line-btn{display:inline-flex;align-items:center;gap:8px;background:linear-gradient(135deg,#06C755,#00B050);color:white;
    text-decoration:none;padding:12px 26px;border-radius:50px;font-weight:700;font-size:.95rem;
    box-shadow:0 4px 16px rgba(6,199,85,.35);transition:transform .2s,box-shadow .2s;}
  .line-btn:hover{transform:translateY(-2px);box-shadow:0 8px 24px rgba(6,199,85,.4);}
  .line-btn svg{width:20px;height:20px;}

  /* NAV */
  .nav-tabs{display:flex;justify-content:center;gap:8px;padding:16px 14px;position:relative;z-index:10;flex-wrap:wrap;}
  .tab-btn{padding:9px 18px;border-radius:50px;border:2px solid transparent;font-family:'Nunito',sans-serif;
    font-weight:700;font-size:.88rem;cursor:pointer;transition:all .25s;background:white;color:var(--text-mid);
    box-shadow:var(--shadow-card);}
  .tab-btn.active{background:linear-gradient(135deg,var(--pink-strong),var(--blue-strong));color:white;
    box-shadow:0 4px 18px rgba(180,130,200,.4);}
  .tab-btn:hover:not(.active){border-color:var(--pink-mid);transform:translateY(-1px);}

  /* FILTER + SEARCH */
  .filter-row{display:flex;gap:8px;padding:0 18px 14px;flex-wrap:wrap;justify-content:center;position:relative;z-index:10;}
  .filter-chip{padding:6px 15px;border-radius:50px;border:2px solid rgba(220,190,230,.4);background:white;
    font-size:.82rem;font-weight:700;cursor:pointer;transition:all .2s;color:var(--text-mid);font-family:'Nunito',sans-serif;}
  .filter-chip.active{background:linear-gradient(135deg,var(--pink-mid),var(--blue-mid));border-color:transparent;color:white;}
  .search-bar{padding:0 20px 18px;max-width:500px;margin:0 auto;position:relative;z-index:10;}
  .search-input{width:100%;padding:13px 48px 13px 20px;border-radius:50px;border:2px solid rgba(255,180,210,.4);
    background:white;font-size:.95rem;font-family:'Noto Sans TC',sans-serif;outline:none;
    box-shadow:var(--shadow-card);transition:border-color .2s;color:var(--text-dark);}
  .search-input:focus{border-color:var(--pink-strong);}
  .search-icon{position:absolute;right:34px;top:50%;transform:translateY(-50%);font-size:1.1rem;color:var(--text-soft);}

  /* VIEWS */
  .view{display:none;}.view.active{display:block;}

  /* CAT GRID */
  .cat-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(268px,1fr));gap:20px;
    padding:0 20px 60px;max-width:1200px;margin:0 auto;position:relative;z-index:10;}
  @keyframes fadeInUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}

  /* CAT CARD */
  .cat-card{background:white;border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow-card);
    transition:transform .3s,box-shadow .3s;cursor:pointer;animation:fadeInUp .4s ease both;}
  .cat-card:hover{transform:translateY(-6px);box-shadow:0 16px 48px rgba(180,120,160,.25);}
  .card-wrap{position:relative;}
  .cat-photo{width:100%;height:208px;object-fit:cover;}
  .cat-photo-placeholder{width:100%;height:208px;background:linear-gradient(135deg,var(--pink-light),var(--blue-light));
    display:flex;align-items:center;justify-content:center;font-size:4rem;}
  .cat-info{padding:15px 17px 17px;}
  .cat-name{font-family:'Nunito',sans-serif;font-size:1.3rem;font-weight:900;color:var(--text-dark);
    margin-bottom:6px;display:flex;align-items:center;gap:7px;flex-wrap:wrap;}
  .gender-badge{font-size:.71rem;padding:3px 9px;border-radius:20px;font-weight:700;font-family:'Nunito',sans-serif;}
  .gender-badge.male{background:var(--blue-light);color:var(--blue-deep);}
  .gender-badge.female{background:var(--pink-light);color:var(--pink-deep);}
  .cat-meta{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:8px;}
  .tag{font-size:.74rem;padding:3px 9px;border-radius:20px;background:var(--lavender);color:var(--text-mid);font-weight:600;}
  .cat-desc{font-size:.85rem;color:var(--text-soft);line-height:1.6;display:-webkit-box;-webkit-line-clamp:2;-webkit-box-orient:vertical;overflow:hidden;}
  .adopted-ribbon{position:absolute;top:13px;right:-8px;background:linear-gradient(135deg,var(--pink-deep),var(--blue-deep));
    color:white;font-size:.7rem;font-weight:700;padding:4px 16px 4px 12px;border-radius:4px 0 0 4px;
    box-shadow:0 4px 12px rgba(180,120,160,.25);font-family:'Nunito',sans-serif;z-index:2;}
  .photo-count-badge{position:absolute;bottom:213px;left:11px;background:rgba(0,0,0,.42);color:white;
    font-size:.7rem;font-weight:700;padding:3px 8px;border-radius:20px;backdrop-filter:blur(4px);z-index:2;
    font-family:'Nunito',sans-serif;}

  /* MODAL */
  .modal-overlay{display:none;position:fixed;inset:0;background:rgba(60,40,70,.5);backdrop-filter:blur(6px);
    z-index:100;align-items:center;justify-content:center;padding:16px;}
  .modal-overlay.open{display:flex;}
  .modal{background:white;border-radius:var(--radius);max-width:540px;width:100%;max-height:92vh;
    overflow-y:auto;box-shadow:0 24px 80px rgba(100,60,120,.3);animation:modalIn .3s ease;position:relative;}
  @keyframes modalIn{from{opacity:0;transform:scale(.92) translateY(20px)}to{opacity:1;transform:scale(1) translateY(0)}}

  /* CAROUSEL */
  .carousel{position:relative;width:100%;overflow:hidden;border-radius:var(--radius) var(--radius) 0 0;
    background:linear-gradient(135deg,var(--pink-light),var(--blue-light));}
  .carousel-track{display:flex;transition:transform .4s cubic-bezier(.4,0,.2,1);}
  .carousel-slide{min-width:100%;height:300px;flex-shrink:0;}
  .carousel-slide img{width:100%;height:100%;object-fit:cover;}
  .carousel-slide .empty-slide{width:100%;height:100%;display:flex;align-items:center;justify-content:center;font-size:6rem;}
  .carousel-btn{position:absolute;top:50%;transform:translateY(-50%);background:rgba(255,255,255,.85);
    border:none;border-radius:50%;width:36px;height:36px;font-size:1rem;cursor:pointer;
    display:flex;align-items:center;justify-content:center;box-shadow:var(--shadow-card);z-index:5;transition:background .2s;}
  .carousel-btn:hover{background:white;}
  .carousel-btn.prev{left:10px;}.carousel-btn.next{right:10px;}
  .carousel-dots{position:absolute;bottom:10px;left:50%;transform:translateX(-50%);display:flex;gap:6px;}
  .carousel-dot{width:7px;height:7px;border-radius:50%;background:rgba(255,255,255,.5);border:none;cursor:pointer;transition:all .2s;padding:0;}
  .carousel-dot.active{background:white;transform:scale(1.3);}
  .photo-label{position:absolute;top:12px;left:12px;font-size:.71rem;font-weight:700;padding:4px 10px;
    border-radius:20px;backdrop-filter:blur(6px);font-family:'Nunito',sans-serif;}
  .photo-label.avatar{background:rgba(255,133,179,.85);color:white;}
  .photo-label.gallery{background:rgba(122,184,245,.85);color:white;}

  .modal-body{padding:20px 24px 26px;}
  .modal-name{font-family:'Nunito',sans-serif;font-size:1.7rem;font-weight:900;color:var(--text-dark);
    margin-bottom:12px;display:flex;align-items:center;gap:8px;flex-wrap:wrap;}
  .modal-tags{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:13px;}
  .modal-desc{font-size:.93rem;line-height:1.8;color:var(--text-mid);margin-bottom:18px;white-space:pre-wrap;}
  .modal-adopt-btn{display:block;width:100%;padding:14px;background:linear-gradient(135deg,var(--pink-strong),var(--blue-strong));
    color:white;border:none;border-radius:50px;font-family:'Nunito',sans-serif;font-size:1rem;font-weight:800;
    cursor:pointer;text-align:center;text-decoration:none;transition:all .2s;box-shadow:0 4px 18px rgba(180,130,200,.4);}
  .modal-adopt-btn:hover{transform:translateY(-2px);box-shadow:0 8px 28px rgba(180,130,200,.5);}
  .modal-close{position:absolute;top:11px;right:11px;background:rgba(255,255,255,.9);border:none;border-radius:50%;
    width:34px;height:34px;font-size:1.1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;
    box-shadow:var(--shadow-card);z-index:10;transition:background .2s;}
  .modal-close:hover{background:white;}

  /* DIARY */
  .diary-container{max-width:620px;margin:0 auto;padding:0 18px 60px;position:relative;z-index:10;}
  .diary-post{background:white;border-radius:var(--radius);box-shadow:var(--shadow-card);margin-bottom:22px;overflow:hidden;animation:fadeInUp .4s ease both;}
  .diary-header{display:flex;align-items:center;gap:12px;padding:15px 17px 11px;}
  .diary-avatar{width:44px;height:44px;border-radius:50%;flex-shrink:0;overflow:hidden;
    background:linear-gradient(135deg,var(--pink-light),var(--blue-light));display:flex;align-items:center;justify-content:center;font-size:1.4rem;}
  .diary-avatar img{width:100%;height:100%;object-fit:cover;}
  .diary-meta{flex:1;}
  .diary-cat-name{font-family:'Nunito',sans-serif;font-weight:800;font-size:.98rem;color:var(--text-dark);}
  .diary-date{font-size:.76rem;color:var(--text-soft);}
  .diary-photos{display:grid;gap:2px;}
  .diary-photos.n1{grid-template-columns:1fr;}
  .diary-photos.n1 .dp{aspect-ratio:4/3;}
  .diary-photos.n2{grid-template-columns:1fr 1fr;}
  .diary-photos.n3{grid-template-columns:1fr 1fr;}
  .diary-photos.n3 .dp:first-child{grid-column:1/-1;}
  .diary-photos.n4{grid-template-columns:1fr 1fr;}
  .dp{width:100%;aspect-ratio:1;overflow:hidden;}
  .dp img{width:100%;height:100%;object-fit:cover;cursor:pointer;transition:transform .3s;}
  .dp img:hover{transform:scale(1.04);}
  .diary-content{padding:13px 17px 17px;}
  .diary-text{font-size:.92rem;line-height:1.75;color:var(--text-mid);white-space:pre-wrap;}
  .diary-tag-chip{display:inline-block;font-size:.73rem;font-weight:700;padding:3px 9px;border-radius:20px;
    background:var(--lavender);color:var(--text-mid);font-family:'Nunito',sans-serif;margin-bottom:7px;}

  /* ADMIN */
  .admin-panel{max-width:660px;margin:0 auto;padding:14px 18px 60px;position:relative;z-index:10;}
  .admin-login{background:white;border-radius:var(--radius);padding:32px 26px;box-shadow:var(--shadow-card);text-align:center;}
  .admin-login h2{font-family:'Nunito',sans-serif;font-size:1.45rem;font-weight:900;color:var(--text-dark);margin-bottom:6px;}
  .admin-login p{color:var(--text-soft);font-size:.86rem;margin-bottom:20px;}
  .admin-sub-tabs{display:flex;gap:7px;margin-bottom:14px;flex-wrap:wrap;}
  .admin-sub-btn{padding:8px 18px;border-radius:50px;border:2px solid rgba(220,190,230,.4);background:white;
    font-family:'Nunito',sans-serif;font-weight:700;font-size:.85rem;cursor:pointer;transition:all .2s;color:var(--text-mid);}
  .admin-sub-btn.active{background:linear-gradient(135deg,var(--pink-mid),var(--blue-mid));color:white;border-color:transparent;}
  .form-group{margin-bottom:15px;text-align:left;}
  .form-label{display:block;font-size:.84rem;font-weight:700;color:var(--text-mid);margin-bottom:5px;}
  .form-input,.form-textarea,.form-select{width:100%;padding:11px 14px;border-radius:var(--radius-sm);
    border:2px solid rgba(220,200,230,.5);font-size:.92rem;font-family:'Noto Sans TC',sans-serif;outline:none;
    background:white;transition:border-color .2s;color:var(--text-dark);}
  .form-input:focus,.form-textarea:focus,.form-select:focus{border-color:var(--pink-strong);}
  .form-textarea{resize:vertical;min-height:88px;}
  .add-form-card{background:white;border-radius:var(--radius);padding:22px 22px 26px;box-shadow:var(--shadow-card);margin-bottom:14px;}
  .add-form-card h3{font-family:'Nunito',sans-serif;font-size:1.15rem;font-weight:900;color:var(--text-dark);margin-bottom:17px;}
  .multi-upload-row{display:grid;grid-template-columns:1fr 1fr;gap:11px;margin-bottom:4px;}
  .photo-upload-zone{border:2.5px dashed var(--pink-mid);border-radius:var(--radius-sm);padding:18px 10px;text-align:center;
    cursor:pointer;transition:all .2s;background:rgba(255,213,231,.07);position:relative;min-height:108px;
    display:flex;flex-direction:column;align-items:center;justify-content:center;}
  .photo-upload-zone:hover{border-color:var(--pink-strong);background:rgba(255,213,231,.14);}
  .photo-upload-zone input[type="file"]{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%;height:100%;}
  .puz-icon{font-size:1.75rem;margin-bottom:3px;}
  .puz-label{font-size:.78rem;font-weight:700;color:var(--text-mid);}
  .puz-sub{font-size:.7rem;color:var(--text-soft);}
  .photo-preview-thumb{width:100%;height:76px;object-fit:cover;border-radius:10px;margin-top:8px;display:none;}
  .gallery-previews{display:flex;gap:7px;flex-wrap:wrap;margin-top:9px;}
  .gallery-thumb-wrap{position:relative;width:68px;height:68px;}
  .gallery-thumb-wrap img{width:68px;height:68px;object-fit:cover;border-radius:10px;}
  .gallery-thumb-wrap .rm-thumb{position:absolute;top:-6px;right:-6px;background:var(--pink-deep);color:white;
    border:none;border-radius:50%;width:20px;height:20px;font-size:.68rem;cursor:pointer;
    display:flex;align-items:center;justify-content:center;}
  .submit-btn{width:100%;padding:13px;background:linear-gradient(135deg,var(--pink-strong),var(--blue-strong));
    color:white;border:none;border-radius:50px;font-family:'Nunito',sans-serif;font-size:1rem;font-weight:800;
    cursor:pointer;box-shadow:0 4px 20px rgba(180,130,200,.4);transition:all .2s;margin-top:5px;}
  .submit-btn:hover{transform:translateY(-2px);box-shadow:0 8px 28px rgba(180,130,200,.5);}
  .cat-list-admin{display:flex;flex-direction:column;gap:9px;}
  .admin-cat-item{display:flex;align-items:center;gap:11px;background:white;border-radius:var(--radius-sm);
    padding:10px 13px;box-shadow:var(--shadow-card);}
  .admin-cat-thumb{width:50px;height:50px;border-radius:12px;object-fit:cover;flex-shrink:0;}
  .admin-cat-thumb-ph{width:50px;height:50px;border-radius:12px;background:linear-gradient(135deg,var(--pink-light),var(--blue-light));
    display:flex;align-items:center;justify-content:center;font-size:1.55rem;flex-shrink:0;}
  .admin-cat-info{flex:1;min-width:0;}
  .admin-cat-name{font-weight:800;font-family:'Nunito',sans-serif;color:var(--text-dark);font-size:.92rem;}
  .admin-cat-sub{font-size:.76rem;color:var(--text-soft);}
  .toggle-adopted-btn{background:rgba(168,212,255,.22);border:none;border-radius:10px;padding:6px 10px;
    cursor:pointer;color:var(--blue-deep);font-size:.74rem;font-weight:700;transition:background .2s;
    font-family:'Nunito',sans-serif;white-space:nowrap;}
  .toggle-adopted-btn:hover{background:rgba(120,180,250,.3);}
  .del-btn{background:rgba(255,180,200,.2);border:none;border-radius:10px;padding:6px 10px;cursor:pointer;
    color:var(--pink-deep);font-size:.9rem;transition:background .2s;}
  .del-btn:hover{background:rgba(255,130,160,.25);}

  /* DIARY ADMIN */
  .diary-cat-select-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(78px,1fr));gap:9px;margin-bottom:4px;}
  .diary-cat-option{border:2.5px solid rgba(220,190,230,.4);border-radius:13px;padding:8px 5px;text-align:center;cursor:pointer;transition:all .2s;background:white;}
  .diary-cat-option.selected{border-color:var(--pink-strong);background:var(--pink-light);}
  .dcopt-av{width:42px;height:42px;border-radius:50%;object-fit:cover;margin:0 auto 4px;display:block;}
  .dcopt-ph{width:42px;height:42px;border-radius:50%;background:linear-gradient(135deg,var(--pink-light),var(--blue-light));
    font-size:1.35rem;display:flex;align-items:center;justify-content:center;margin:0 auto 4px;}
  .dcopt-name{font-size:.73rem;font-weight:700;color:var(--text-mid);font-family:'Nunito',sans-serif;}
  .diary-upload-zone{border:2.5px dashed var(--blue-mid);border-radius:var(--radius-sm);padding:18px;text-align:center;
    cursor:pointer;position:relative;transition:all .2s;background:rgba(208,232,255,.1);}
  .diary-upload-zone:hover{border-color:var(--blue-strong);background:rgba(208,232,255,.18);}
  .diary-upload-zone input{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%;height:100%;}

  /* LIGHTBOX */
  .lightbox{display:none;position:fixed;inset:0;background:rgba(30,20,40,.88);z-index:200;align-items:center;justify-content:center;}
  .lightbox.open{display:flex;}
  .lightbox img{max-width:92vw;max-height:88vh;border-radius:16px;object-fit:contain;box-shadow:0 24px 80px rgba(0,0,0,.5);}
  .lightbox-close{position:absolute;top:16px;right:16px;background:rgba(255,255,255,.15);color:white;border:none;
    border-radius:50%;width:40px;height:40px;font-size:1.3rem;cursor:pointer;display:flex;align-items:center;justify-content:center;}
  .lightbox-close:hover{background:rgba(255,255,255,.25);}

  .empty-state{text-align:center;padding:52px 20px;color:var(--text-soft);}
  .empty-state .emoji{font-size:3.4rem;margin-bottom:13px;}
  .section-title{font-family:'Nunito',sans-serif;font-size:1rem;font-weight:800;color:var(--text-mid);margin-bottom:11px;}
  .toast{position:fixed;bottom:26px;left:50%;transform:translateX(-50%) translateY(20px);
    background:linear-gradient(135deg,var(--pink-strong),var(--blue-strong));color:white;
    padding:12px 24px;border-radius:50px;font-weight:700;font-family:'Nunito',sans-serif;font-size:.91rem;
    box-shadow:0 8px 24px rgba(180,130,200,.4);z-index:999;opacity:0;transition:all .35s;white-space:nowrap;}
  .toast.show{opacity:1;transform:translateX(-50%) translateY(0);}

  @media(max-width:480px){
    .cat-grid{grid-template-columns:1fr 1fr;gap:9px;padding:0 9px 40px;}
    .cat-info{padding:9px 11px 13px;}
    .cat-name{font-size:1rem;}
    .modal-body{padding:15px 16px 20px;}
    .multi-upload-row{grid-template-columns:1fr 1fr;}
    .admin-panel{padding:10px 10px 40px;}
    .add-form-card{padding:16px 14px 20px;}
  }
</style>
</head>
<body>

<header>
  <div class="header-paws">🐾 🐱 🐾</div>
  <h1>浪貓不浪中途之家</h1>
  <p>每一隻貓咪都在等待牠專屬的家 💕</p>
  <a href="https://line.me/R/ti/p/@151ffkpg" target="_blank" class="line-btn">
    <svg viewBox="0 0 24 24" fill="white"><path d="M12 2C6.48 2 2 6.22 2 11.4c0 2.9 1.54 5.5 3.96 7.24L5 22l3.44-1.7C9.56 20.73 10.77 21 12 21c5.52 0 10-4.22 10-9.4S17.52 2 12 2z"/></svg>
    LINE 聯絡我們 @151ffkpg
  </a>
</header>

<div class="nav-tabs">
  <button class="tab-btn active" onclick="switchTab('all')">🐾 全部貓咪</button>
  <button class="tab-btn" onclick="switchTab('available')">💛 待領養</button>
  <button class="tab-btn" onclick="switchTab('adopted')">🏠 已領養</button>
  <button class="tab-btn" onclick="switchTab('diary')">📸 日常動態</button>
  <button class="tab-btn" onclick="switchTab('admin')">⚙️ 管理</button>
</div>

<div class="filter-row" id="filterRow">
  <span class="filter-chip active" onclick="filterCats(this,'all')">全部</span>
  <span class="filter-chip" onclick="filterCats(this,'公')">🐱 公貓</span>
  <span class="filter-chip" onclick="filterCats(this,'母')">🐈 母貓</span>
  <span class="filter-chip" onclick="filterCats(this,'幼貓')">🍼 幼貓</span>
  <span class="filter-chip" onclick="filterCats(this,'成貓')">✨ 成貓</span>
</div>
<div class="search-bar" id="searchBarWrap">
  <input class="search-input" id="searchInput" type="text" placeholder="搜尋貓咪名字或特徵…" oninput="renderCats()">
  <span class="search-icon">🔍</span>
</div>

<div class="view active" id="view-all">
  <div class="cat-grid" id="catGrid"></div>
</div>

<div class="view" id="view-diary">
  <div class="diary-container" id="diaryFeed"></div>
</div>

<div class="view" id="view-admin">
  <div class="admin-panel">
    <div id="adminLoginBox" class="admin-login">
      <div style="font-size:2.3rem;margin-bottom:10px;">🔑</div>
      <h2>管理員登入</h2>
      <p>請輸入管理密碼</p>
      <div class="form-group">
        <input class="form-input" type="password" id="pwdInput" placeholder="輸入密碼" onkeydown="if(event.key==='Enter')adminLogin()">
      </div>
      <button class="submit-btn" onclick="adminLogin()">登入管理</button>
    </div>

    <div id="adminContent" style="display:none;">
      <div class="admin-sub-tabs">
        <button class="admin-sub-btn active" onclick="switchAdminTab('cat',this)">🐱 新增貓咪</button>
        <button class="admin-sub-btn" onclick="switchAdminTab('diary',this)">📸 發布動態</button>
        <button class="admin-sub-btn" onclick="switchAdminTab('list',this)">📋 管理貓咪</button>
        <button class="admin-sub-btn" onclick="switchAdminTab('diarylist',this)">📝 管理動態</button>
      </div>

      <!-- ADD CAT -->
      <div id="adminTab-cat">
        <div class="add-form-card">
          <h3>🐾 新增貓咪資料</h3>
          <div class="form-group">
            <label class="form-label">📷 照片上傳</label>
            <div class="multi-upload-row">
              <div>
                <div class="photo-upload-zone" id="avatarZone">
                  <input type="file" accept="image/*" capture="environment" onchange="handleAvatar(event)" id="avatarFileInput">
                  <div class="puz-icon">🐱</div>
                  <div class="puz-label">大頭照</div>
                  <div class="puz-sub">封面用</div>
                </div>
                <img id="avatarPreview" class="photo-preview-thumb" alt="">
              </div>
              <div>
                <div class="photo-upload-zone" style="border-color:var(--blue-mid);">
                  <input type="file" accept="image/*" multiple capture="environment" onchange="handleGallery(event)" id="galleryFileInput">
                  <div class="puz-icon" style="color:var(--blue-deep)">🖼️</div>
                  <div class="puz-label">生活照</div>
                  <div class="puz-sub">可多張選取</div>
                </div>
                <div class="gallery-previews" id="galleryPreviews"></div>
              </div>
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">🐱 貓咪名字</label>
            <input class="form-input" id="f_name" type="text" placeholder="例：小橘、奶茶">
          </div>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;">
            <div class="form-group">
              <label class="form-label">♀♂ 性別</label>
              <select class="form-select" id="f_gender"><option value="公">公</option><option value="母">母</option></select>
            </div>
            <div class="form-group">
              <label class="form-label">🎂 年齡</label>
              <input class="form-input" id="f_age" type="text" placeholder="例：3個月">
            </div>
          </div>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;">
            <div class="form-group">
              <label class="form-label">🎨 花色</label>
              <input class="form-input" id="f_color" type="text" placeholder="例：橘白">
            </div>
            <div class="form-group">
              <label class="form-label">✂️ 結紮</label>
              <select class="form-select" id="f_sterilized"><option value="已結紮">已結紮</option><option value="未結紮">未結紮</option></select>
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">💉 疫苗</label>
            <select class="form-select" id="f_vaccine"><option value="已施打">已施打</option><option value="未施打">未施打</option><option value="施打中">施打中</option></select>
          </div>
          <div class="form-group">
            <label class="form-label">💬 個性介紹</label>
            <textarea class="form-textarea" id="f_desc" placeholder="描述這隻貓咪的個性、習慣、特色…"></textarea>
          </div>
          <button class="submit-btn" onclick="addCat()">✨ 儲存上傳</button>
        </div>
      </div>

      <!-- POST DIARY -->
      <div id="adminTab-diary" style="display:none;">
        <div class="add-form-card">
          <h3>📸 發布日常動態</h3>
          <div class="form-group">
            <label class="form-label">選擇貓咪（可多選）</label>
            <div class="diary-cat-select-grid" id="diaryCatSelect"></div>
          </div>
          <div class="form-group">
            <label class="form-label">📝 內容</label>
            <textarea class="form-textarea" id="d_text" placeholder="分享今天的日常、有趣的事…" style="min-height:108px;"></textarea>
          </div>
          <div class="form-group">
            <label class="form-label">🖼️ 上傳照片（可多張）</label>
            <div class="diary-upload-zone">
              <input type="file" accept="image/*" multiple capture="environment" onchange="handleDiaryPhotos(event)" id="diaryPhotoInput">
              <div style="font-size:1.75rem;margin-bottom:4px;">📷</div>
              <div style="font-size:.82rem;font-weight:700;color:var(--text-mid);">點我上傳照片（支援手機拍照）</div>
              <div style="font-size:.72rem;color:var(--text-soft);margin-top:2px;">可一次選多張</div>
            </div>
            <div class="gallery-previews" id="diaryPhotoPreviews"></div>
          </div>
          <button class="submit-btn" onclick="postDiary()">🌟 發布動態</button>
        </div>
      </div>

      <!-- CAT LIST -->
      <div id="adminTab-list" style="display:none;">
        <div id="adminCatList" class="cat-list-admin"></div>
      </div>

      <!-- DIARY LIST -->
      <div id="adminTab-diarylist" style="display:none;">
        <div id="adminDiaryList" class="cat-list-admin"></div>
      </div>
    </div>
  </div>
</div>

<!-- MODAL -->
<div class="modal-overlay" id="modal" onclick="closeModal(event)">
  <div class="modal">
    <button class="modal-close" onclick="closeModalDirect()">✕</button>
    <div id="modalInner"></div>
  </div>
</div>

<!-- LIGHTBOX -->
<div class="lightbox" id="lightbox" onclick="closeLightbox()">
  <button class="lightbox-close" onclick="closeLightbox()">✕</button>
  <img id="lightboxImg" src="" alt="">
</div>

<div class="toast" id="toast"></div>

<script>
const CATS_KEY  = 'nolangcat_v3';
const DIARY_KEY = 'nolangcat_diary_v1';
const ADMIN_PWD = 'chch715715'; // ← 可修改密碼

function loadCats()  { try{return JSON.parse(localStorage.getItem(CATS_KEY)) ||[];}catch{return[];} }
function loadDiary() { try{return JSON.parse(localStorage.getItem(DIARY_KEY))||[];}catch{return[];} }
function saveCats(d)  { localStorage.setItem(CATS_KEY, JSON.stringify(d)); }
function saveDiary(d) { localStorage.setItem(DIARY_KEY,JSON.stringify(d)); }

let cats  = loadCats();
let diary = loadDiary();
let currentFilter = 'all', currentTab = 'all';
let avatarDataUrl = null, galleryDataUrls = [], diaryPhotoDataUrls = [];
let selectedDiaryCats = [], isLoggedIn = false;
let carouselSlides = [], carouselIdx = 0;

// Seed
if(!cats.length){
  cats=[
    {id:1,name:'小橘',gender:'公',age:'8個月',color:'橘白',sterilized:'已結紮',vaccine:'已施打',desc:'活潑好動的小男孩，超級愛撒嬌！會主動跑來蹭人，對其他貓咪也很友善 🧡',avatar:null,gallery:[],adopted:false,addedAt:Date.now()},
    {id:2,name:'奶茶',gender:'母',age:'2歲',color:'乳白',sterilized:'已結紮',vaccine:'已施打',desc:'安靜優雅的女孩，喜歡窩在暖暖的地方睡覺，跟熟悉的人很黏 🤍',avatar:null,gallery:[],adopted:false,addedAt:Date.now()+1},
    {id:3,name:'黑糖',gender:'公',age:'1歲半',color:'純黑',sterilized:'已結紮',vaccine:'已施打',desc:'帥氣的黑貓弟弟，其實超溫柔！熟悉後會一直跟在你身邊當小尾巴 🖤',avatar:null,gallery:[],adopted:true,addedAt:Date.now()+2}
  ];
  saveCats(cats);
}

// TAB
function switchTab(tab){
  currentTab=tab;
  const order=['all','available','adopted','diary','admin'];
  document.querySelectorAll('.tab-btn').forEach((b,i)=>b.classList.toggle('active',order[i]===tab));
  const fr=document.getElementById('filterRow'), sw=document.getElementById('searchBarWrap');
  order.forEach(t=>{const el=document.getElementById('view-'+t);if(el)el.classList.remove('active');});
  if(tab==='admin'){
    document.getElementById('view-admin').classList.add('active');
    fr.style.display='none'; sw.style.display='none';
    if(isLoggedIn){renderAdminList();renderAdminDiaryList();}
  } else if(tab==='diary'){
    document.getElementById('view-diary').classList.add('active');
    fr.style.display='none'; sw.style.display='none';
    renderDiary();
  } else {
    document.getElementById('view-all').classList.add('active');
    fr.style.display='flex'; sw.style.display='block';
    renderCats();
  }
}

function filterCats(el,val){
  document.querySelectorAll('.filter-chip').forEach(c=>c.classList.remove('active'));
  el.classList.add('active'); currentFilter=val; renderCats();
}

// RENDER CATS
function renderCats(){
  const grid=document.getElementById('catGrid');
  const q=document.getElementById('searchInput').value.toLowerCase();
  let list=cats.filter(c=>{
    if(currentTab==='available'&&c.adopted) return false;
    if(currentTab==='adopted'&&!c.adopted)  return false;
    if(currentFilter==='公'&&c.gender!=='公') return false;
    if(currentFilter==='母'&&c.gender!=='母') return false;
    if(currentFilter==='幼貓'&&!isKitten(c.age)) return false;
    if(currentFilter==='成貓'&& isKitten(c.age)) return false;
    if(q&&!c.name.toLowerCase().includes(q)&&!(c.desc||'').toLowerCase().includes(q)&&!(c.color||'').toLowerCase().includes(q)) return false;
    return true;
  });
  if(!list.length){grid.innerHTML=`<div class="empty-state" style="grid-column:1/-1"><div class="emoji">🐾</div><p>這裡還沒有符合的貓咪</p></div>`;return;}
  const cover=c=>c.avatar||(c.gallery&&c.gallery[0])||null;
  const total=c=>(c.avatar?1:0)+(c.gallery?.length||0);
  grid.innerHTML=list.map((c,i)=>`
    <div class="card-wrap" onclick="openModal(${c.id})" style="animation-delay:${i*.055}s">
      ${c.adopted?'<div class="adopted-ribbon">已領養 🏠</div>':''}
      ${total(c)>1?`<div class="photo-count-badge">📷 ${total(c)}</div>`:''}
      <div class="cat-card">
        ${cover(c)?`<img class="cat-photo" src="${cover(c)}" alt="${c.name}" loading="lazy">`:`<div class="cat-photo-placeholder">🐱</div>`}
        <div class="cat-info">
          <div class="cat-name">${c.name}<span class="gender-badge ${c.gender==='公'?'male':'female'}">${c.gender}</span></div>
          <div class="cat-meta">
            ${c.age?`<span class="tag">🎂 ${c.age}`:``}${c.age?'</span>':''}
            ${c.color?`<span class="tag">🎨 ${c.color}</span>`:''}
            ${c.sterilized?`<span class="tag">✂️ ${c.sterilized}</span>`:''}
          </div>
          <div class="cat-desc">${c.desc||'尚無介紹'}</div>
        </div>
      </div>
    </div>`).join('');
}

function isKitten(a){if(!a)return false;const m=a.match(/(\d+)/);if(!m)return false;const n=+m[1];if(a.includes('個月')||a.includes('月'))return n<12;if(a.includes('歲'))return n<1;return false;}

// MODAL + CAROUSEL
function openModal(id){
  const c=cats.find(c=>c.id===id); if(!c)return;
  carouselSlides=[];
  if(c.avatar) carouselSlides.push({src:c.avatar,label:'大頭照',type:'avatar'});
  (c.gallery||[]).forEach(g=>carouselSlides.push({src:g,label:'生活照',type:'gallery'}));
  carouselIdx=0;
  const slides=carouselSlides.length
    ? carouselSlides.map(s=>`<div class="carousel-slide"><img src="${s.src}" alt=""></div>`).join('')
    : `<div class="carousel-slide"><div class="empty-slide">🐱</div></div>`;
  const dots=carouselSlides.length>1?`<div class="carousel-dots">${carouselSlides.map((_,i)=>`<button class="carousel-dot ${i===0?'active':''}" onclick="gotoSlide(${i})"></button>`).join('')}</div>`:'';
  const nav=carouselSlides.length>1?`<button class="carousel-btn prev" onclick="shiftSlide(-1)">‹</button><button class="carousel-btn next" onclick="shiftSlide(1)">›</button>`:'';
  const lbl=carouselSlides.length?`<span class="photo-label ${carouselSlides[0].type}" id="carouselLabel">${carouselSlides[0].label}</span>`:'';
  document.getElementById('modalInner').innerHTML=`
    <div class="carousel">${`<div class="carousel-track" id="carouselTrack">${slides}</div>`}${nav}${dots}${lbl}</div>
    <div class="modal-body">
      <div class="modal-name">${c.name}<span class="gender-badge ${c.gender==='公'?'male':'female'}">${c.gender}</span>${c.adopted?'<span class="gender-badge" style="background:#d0e8ff;color:#4a90d9;">🏠 已領養</span>':''}</div>
      <div class="modal-tags">
        ${c.age?`<span class="tag">🎂 ${c.age}</span>`:''}
        ${c.color?`<span class="tag">🎨 ${c.color}</span>`:''}
        ${c.sterilized?`<span class="tag">✂️ ${c.sterilized}</span>`:''}
        ${c.vaccine?`<span class="tag">💉 ${c.vaccine}</span>`:''}
      </div>
      <div class="modal-desc">${c.desc||'尚無介紹'}</div>
      ${!c.adopted?`<a href="https://line.me/R/ti/p/@151ffkpg" target="_blank" class="modal-adopt-btn">💌 聯絡LINE詢問領養 @151ffkpg</a>`:''}
    </div>`;
  document.getElementById('modal').classList.add('open');
  document.body.style.overflow='hidden';
}
function shiftSlide(d){carouselIdx=(carouselIdx+d+carouselSlides.length)%carouselSlides.length;updateCarousel();}
function gotoSlide(i){carouselIdx=i;updateCarousel();}
function updateCarousel(){
  const t=document.getElementById('carouselTrack');
  if(t)t.style.transform=`translateX(-${carouselIdx*100}%)`;
  document.querySelectorAll('.carousel-dot').forEach((d,i)=>d.classList.toggle('active',i===carouselIdx));
  const l=document.getElementById('carouselLabel');
  if(l&&carouselSlides[carouselIdx]){l.textContent=carouselSlides[carouselIdx].label;l.className='photo-label '+carouselSlides[carouselIdx].type;}
}
function closeModal(e){if(e.target===document.getElementById('modal'))closeModalDirect();}
function closeModalDirect(){document.getElementById('modal').classList.remove('open');document.body.style.overflow='';}

// LIGHTBOX
function openLightbox(src){document.getElementById('lightboxImg').src=src;document.getElementById('lightbox').classList.add('open');document.body.style.overflow='hidden';}
function closeLightbox(){document.getElementById('lightbox').classList.remove('open');document.body.style.overflow='';}

// DIARY
function renderDiary(){
  const feed=document.getElementById('diaryFeed');
  if(!diary.length){feed.innerHTML=`<div class="empty-state"><div class="emoji">📷</div><p>還沒有日常動態<br>快去管理頁面發布第一篇！</p></div>`;return;}
  const sorted=[...diary].sort((a,b)=>b.createdAt-a.createdAt);
  feed.innerHTML=sorted.map((post,pi)=>{
    const n=post.photos?.length||0;
    const cls=n>=4?'n4':n===3?'n3':n===2?'n2':n===1?'n1':'';
    const photosHtml=n?`<div class="diary-photos ${cls}">${post.photos.map(src=>`<div class="dp"><img src="${src}" loading="lazy" onclick="event.stopPropagation();openLightbox('${src}')"></div>`).join('')}</div>`:'';
    const catNames=(post.catIds||[]).map(id=>{const c=cats.find(c=>c.id===id);return c?c.name:'';}).filter(Boolean);
    const ac=post.catIds?.length?cats.find(c=>c.id===post.catIds[0]):null;
    const avHtml=ac?.avatar?`<img src="${ac.avatar}" style="width:100%;height:100%;object-fit:cover;">`:'🐱';
    const ds=new Date(post.createdAt).toLocaleDateString('zh-TW',{month:'numeric',day:'numeric',hour:'2-digit',minute:'2-digit'});
    return `<div class="diary-post" style="animation-delay:${pi*.07}s">
      <div class="diary-header">
        <div class="diary-avatar">${avHtml}</div>
        <div class="diary-meta"><div class="diary-cat-name">${catNames.length?catNames.join('、'):'浪貓不浪'} 🐾</div><div class="diary-date">${ds}</div></div>
      </div>
      ${photosHtml}
      <div class="diary-content">
        ${catNames.length?catNames.map(n=>`<span class="diary-tag-chip">#${n}</span>`).join(' ')+'<br>':''}
        <div class="diary-text">${escHtml(post.text||'')}</div>
      </div>
    </div>`;
  }).join('');
}
function escHtml(t){return t.replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');}

// ADMIN LOGIN
function adminLogin(){
  const p=document.getElementById('pwdInput').value;
  if(p===ADMIN_PWD){
    isLoggedIn=true;
    document.getElementById('adminLoginBox').style.display='none';
    document.getElementById('adminContent').style.display='block';
    renderAdminList();renderAdminDiaryList();renderDiaryCatSelect();
    showToast('✅ 登入成功！');
  } else showToast('❌ 密碼錯誤，請重試');
}

function switchAdminTab(tab,btn){
  document.querySelectorAll('.admin-sub-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  ['cat','diary','list','diarylist'].forEach(t=>{const el=document.getElementById('adminTab-'+t);if(el)el.style.display=t===tab?'block':'none';});
  if(tab==='list')renderAdminList();
  if(tab==='diarylist')renderAdminDiaryList();
  if(tab==='diary')renderDiaryCatSelect();
}

// IMAGE COMPRESS
function compressImage(file,mw,mh,q){
  return new Promise(res=>{
    const reader=new FileReader();
    reader.onload=ev=>{
      const img=new Image();
      img.onload=()=>{
        let w=img.width,h=img.height;
        if(w>mw||h>mh){const r=Math.min(mw/w,mh/h);w=Math.round(w*r);h=Math.round(h*r);}
        const canvas=document.createElement('canvas');canvas.width=w;canvas.height=h;
        canvas.getContext('2d').drawImage(img,0,0,w,h);
        res(canvas.toDataURL('image/jpeg',q||.82));
      };
      img.src=ev.target.result;
    };
    reader.readAsDataURL(file);
  });
}

async function handleAvatar(e){
  const f=e.target.files[0];if(!f)return;
  avatarDataUrl=await compressImage(f,800,800,.85);
  const p=document.getElementById('avatarPreview');p.src=avatarDataUrl;p.style.display='block';
  document.getElementById('avatarZone').style.borderColor='var(--pink-strong)';
}
async function handleGallery(e){
  for(const f of Array.from(e.target.files)){galleryDataUrls.push(await compressImage(f,1200,1200,.82));}
  renderGalleryPreviews();
}
function renderGalleryPreviews(){
  document.getElementById('galleryPreviews').innerHTML=galleryDataUrls.map((s,i)=>`<div class="gallery-thumb-wrap"><img src="${s}"><button class="rm-thumb" onclick="removeGallery(${i})">✕</button></div>`).join('');
}
function removeGallery(i){galleryDataUrls.splice(i,1);renderGalleryPreviews();}

async function handleDiaryPhotos(e){
  for(const f of Array.from(e.target.files)){diaryPhotoDataUrls.push(await compressImage(f,1200,1200,.82));}
  renderDiaryPreviews();
}
function renderDiaryPreviews(){
  document.getElementById('diaryPhotoPreviews').innerHTML=diaryPhotoDataUrls.map((s,i)=>`<div class="gallery-thumb-wrap"><img src="${s}"><button class="rm-thumb" onclick="removeDiaryPhoto(${i})">✕</button></div>`).join('');
}
function removeDiaryPhoto(i){diaryPhotoDataUrls.splice(i,1);renderDiaryPreviews();}

// ADD CAT
function addCat(){
  const name=document.getElementById('f_name').value.trim();
  if(!name){showToast('⚠️ 請輸入貓咪名字');return;}
  cats.unshift({id:Date.now(),name,gender:document.getElementById('f_gender').value,
    age:document.getElementById('f_age').value.trim(),color:document.getElementById('f_color').value.trim(),
    sterilized:document.getElementById('f_sterilized').value,vaccine:document.getElementById('f_vaccine').value,
    desc:document.getElementById('f_desc').value.trim(),avatar:avatarDataUrl,gallery:[...galleryDataUrls],
    adopted:false,addedAt:Date.now()});
  saveCats(cats);renderCats();renderAdminList();renderDiaryCatSelect();
  ['f_name','f_age','f_color','f_desc'].forEach(id=>document.getElementById(id).value='');
  document.getElementById('avatarPreview').style.display='none';
  document.getElementById('avatarFileInput').value='';
  document.getElementById('galleryFileInput').value='';
  document.getElementById('galleryPreviews').innerHTML='';
  document.getElementById('avatarZone').style.borderColor='';
  avatarDataUrl=null;galleryDataUrls=[];
  showToast(`🐱 ${name} 已成功新增！`);
}

// DIARY CAT SELECT
function renderDiaryCatSelect(){
  const w=document.getElementById('diaryCatSelect');
  if(!cats.length){w.innerHTML='<p style="font-size:.83rem;color:var(--text-soft);">請先新增貓咪</p>';return;}
  w.innerHTML=cats.map(c=>`
    <div class="diary-cat-option ${selectedDiaryCats.includes(c.id)?'selected':''}" onclick="toggleDiaryCat(${c.id},this)">
      ${c.avatar?`<img class="dcopt-av" src="${c.avatar}" alt="${c.name}">`:`<div class="dcopt-ph">🐱</div>`}
      <div class="dcopt-name">${c.name}</div>
    </div>`).join('');
}
function toggleDiaryCat(id,el){
  const i=selectedDiaryCats.indexOf(id);
  if(i>-1){selectedDiaryCats.splice(i,1);el.classList.remove('selected');}
  else{selectedDiaryCats.push(id);el.classList.add('selected');}
}

// POST DIARY
function postDiary(){
  const text=document.getElementById('d_text').value.trim();
  if(!text&&!diaryPhotoDataUrls.length){showToast('⚠️ 請填寫內容或上傳照片');return;}
  diary.unshift({id:Date.now(),catIds:[...selectedDiaryCats],text,photos:[...diaryPhotoDataUrls],createdAt:Date.now()});
  saveDiary(diary);renderDiary();renderAdminDiaryList();
  document.getElementById('d_text').value='';
  document.getElementById('diaryPhotoInput').value='';
  document.getElementById('diaryPhotoPreviews').innerHTML='';
  diaryPhotoDataUrls=[];selectedDiaryCats=[];renderDiaryCatSelect();
  showToast('🌟 動態已發布！');
}

// ADMIN LIST
function renderAdminList(){
  if(!isLoggedIn)return;
  const list=document.getElementById('adminCatList');
  if(!cats.length){list.innerHTML='<div class="empty-state"><div class="emoji">🐾</div><p>尚未新增任何貓咪</p></div>';return;}
  list.innerHTML=`<p class="section-title">📋 目前貓咪（${cats.length}隻）</p>`+
    cats.map(c=>`<div class="admin-cat-item">
      ${c.avatar?`<img class="admin-cat-thumb" src="${c.avatar}" alt="${c.name}">`:`<div class="admin-cat-thumb-ph">🐱</div>`}
      <div class="admin-cat-info"><div class="admin-cat-name">${c.name} ${c.adopted?'🏠':'💛'}</div><div class="admin-cat-sub">${c.gender} · ${c.age||'-'} · 📷${(c.avatar?1:0)+(c.gallery?.length||0)}張</div></div>
      <button class="toggle-adopted-btn" onclick="toggleAdopted(${c.id})">${c.adopted?'改回待養':'已領養'}</button>
      <button class="del-btn" onclick="deleteCat(${c.id})">🗑️</button>
    </div>`).join('');
}
function toggleAdopted(id){const c=cats.find(c=>c.id===id);if(!c)return;c.adopted=!c.adopted;saveCats(cats);renderAdminList();renderCats();showToast(c.adopted?`🏠 ${c.name} 已領養！`:`💛 ${c.name} 改回待領養`);}
function deleteCat(id){if(!confirm('確定要刪除？'))return;cats=cats.filter(c=>c.id!==id);saveCats(cats);renderAdminList();renderCats();renderDiaryCatSelect();showToast('🗑️ 已刪除');}

// ADMIN DIARY LIST
function renderAdminDiaryList(){
  if(!isLoggedIn)return;
  const list=document.getElementById('adminDiaryList');
  if(!diary.length){list.innerHTML='<div class="empty-state"><div class="emoji">📷</div><p>尚未發布任何動態</p></div>';return;}
  list.innerHTML=`<p class="section-title">📝 已發布動態（${diary.length}則）</p>`+
    diary.map(p=>{
      const names=(p.catIds||[]).map(id=>{const c=cats.find(c=>c.id===id);return c?c.name:'';}).filter(Boolean);
      const ds=new Date(p.createdAt).toLocaleDateString('zh-TW',{month:'numeric',day:'numeric'});
      const th=p.photos?.[0];
      return `<div class="admin-cat-item">
        ${th?`<img class="admin-cat-thumb" src="${th}" alt="">`:`<div class="admin-cat-thumb-ph">📷</div>`}
        <div class="admin-cat-info"><div class="admin-cat-name">${names.join('、')||'未標記貓咪'}</div><div class="admin-cat-sub">${ds} · ${p.photos?.length||0}張 · ${(p.text||'').slice(0,20)}${(p.text||'').length>20?'…':''}</div></div>
        <button class="del-btn" onclick="deleteDiary(${p.id})">🗑️</button>
      </div>`;
    }).join('');
}
function deleteDiary(id){if(!confirm('確定要刪除這篇動態嗎？'))return;diary=diary.filter(p=>p.id!==id);saveDiary(diary);renderAdminDiaryList();renderDiary();showToast('🗑️ 動態已刪除');}

function showToast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),2800);}

renderCats();
</script>
</body>
</html>
