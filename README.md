
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#ffffff">
<title>学校案内 | 퍽을 향해!</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@400;500;600;700&family=Noto+Sans+KR:wght@400;500;600;700&family=Noto+Serif+JP:wght@400;500;600;700&display=swap');

:root{
  --navy:#203c57;--accent:#8f3342;--gold:#b29a6b;
  --ink:#25313b;--muted:#72808c;--line:#e2e6e9;
  --bg:#f7f8fa;--white:#fff;--max:1160px;
}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;background:var(--bg);color:var(--ink);font-family:"Noto Sans KR","Noto Sans JP",sans-serif;font-size:14px}
body.koga{--navy:#35312e;--accent:#bb672f;--gold:#a7895d}
button{font:inherit;cursor:pointer}
a{text-decoration:none;color:inherit}
img{max-width:100%}
.hidden{display:none!important}
.serif{font-family:"Noto Serif JP",serif}
.wrap{width:min(var(--max),calc(100% - 44px));margin:auto}
.eyebrow{font-size:11px;letter-spacing:2px;color:var(--muted)}
.line{height:1px;background:var(--line)}
.fade{animation:fade .25s ease}
@keyframes fade{from{opacity:.35;transform:translateY(5px)}to{opacity:1;transform:none}}

/* 학교 선택 포털 */
#portal{min-height:100vh;background:#fff}
.portal-top{height:5px;background:linear-gradient(90deg,#203c57 50%,#bd6b34 50%)}
.portal-header{padding:28px 0;border-bottom:1px solid var(--line)}
.portal-header .wrap{display:flex;align-items:center;justify-content:space-between;gap:15px}
.portal-header strong{font-size:16px;letter-spacing:.6px}
.portal-header small{color:#7e8790;font-size:11px}
.portal-main{padding:75px 0 90px}
.portal-heading{text-align:center;margin-bottom:55px}
.portal-heading .serif{font-size:clamp(25px,4vw,38px);font-weight:600;letter-spacing:2px;margin:16px 0}
.portal-heading p{color:var(--muted);line-height:1.9}
.school-list{display:grid;grid-template-columns:1fr 1fr;gap:26px}
.school-link{background:#fff;border:1px solid #dce1e5;min-height:345px;padding:38px 30px 30px;display:flex;flex-direction:column;align-items:center;text-align:center;transition:.2s;position:relative}
.school-link:hover{border-color:#9aa9b7;box-shadow:0 12px 32px #1b32450e;transform:translateY(-3px)}
.school-link:before{content:"";position:absolute;top:0;left:0;right:0;height:3px;background:#284864}
.school-link.orange:before{background:#bc6b34}
.school-link img{width:118px;height:118px;object-fit:contain;margin-bottom:21px}
.school-link .serif{font-size:25px;letter-spacing:1px}
.school-link .kr{color:#697681;font-size:13px;margin-top:7px}
.school-link .meta{font-size:11px;color:#9aa3aa;letter-spacing:1px;margin-top:17px}
.school-link .visit{font-size:12px;color:#536578;margin-top:auto;padding-top:25px}
.school-link .visit:after{content:" →";margin-left:8px}
.portal-footer{border-top:1px solid var(--line);padding:25px 0;color:#8b949d;font-size:11px;text-align:center;line-height:1.9}

/* 학교 공식 사이트 */
.site-top{background:var(--navy);color:#fff;font-size:11px;letter-spacing:.7px}
.site-top .wrap{height:34px;display:flex;align-items:center;justify-content:space-between}
.site-top button{border:0;background:none;color:#fff;font-size:11px}
.site-header{background:white}
.site-header .wrap{min-height:112px;display:flex;align-items:center;justify-content:space-between;gap:20px}
.identity{display:flex;align-items:center;gap:19px;cursor:pointer}
.identity img{width:79px;height:79px;object-fit:contain}
.identity small{display:block;font-size:10px;color:#89939c;letter-spacing:2px;margin-bottom:6px}
.identity h1{font-size:clamp(21px,2.6vw,29px);font-weight:600;letter-spacing:1px;margin:0}
.identity .kr{font-size:12px;color:#7a8690;margin-top:4px}
.header-side{text-align:right;color:#78838d;font-size:12px;line-height:2}
.header-side .motto{font-family:"Noto Serif JP",serif;font-size:15px;color:var(--navy)}
.menu-toggle{display:none;border:1px solid #d7dfe5;background:#fff;padding:11px 14px;font-size:12px;letter-spacing:1px}
.navigation{background:var(--navy)}
.navigation .wrap{display:flex;align-items:stretch}
.navigation button{border:0;border-right:1px solid #ffffff1a;background:none;color:#f5f6f8;min-height:52px;padding:0 20px;font-size:12px;letter-spacing:.2px}
.navigation button:first-child{border-left:1px solid #ffffff1a}
.navigation button:hover,.navigation button.active{background:#ffffff1d}
.site-banner{background:linear-gradient(110deg,#e8eef3,#f8f9fa);border-bottom:1px solid #e0e5e9;position:relative}
body.koga .site-banner{background:linear-gradient(110deg,#eee9e5,#faf8f5)}
.site-banner .wrap{min-height:285px;display:flex;align-items:center;justify-content:space-between;gap:30px}
.banner-copy{max-width:620px;padding:40px 0}
.banner-copy small{font-size:11px;letter-spacing:3px;color:var(--accent)}
.banner-copy h2{font-family:"Noto Serif JP",serif;font-weight:600;font-size:clamp(26px,4vw,43px);line-height:1.5;margin:15px 0}
.banner-copy p{color:#63717e;line-height:2;font-size:13px}
.banner-emblem{width:220px;height:220px;object-fit:contain;opacity:.14}
.breadcrumb{background:#fff;border-bottom:1px solid var(--line)}
.breadcrumb .wrap{padding:13px 0;color:#89939c;font-size:11px}
main{padding:44px 0 85px}
.section-heading{margin-bottom:27px}
.section-heading .en{font-size:11px;color:var(--accent);letter-spacing:2px;font-weight:700}
.section-heading h2{font-family:"Noto Serif JP",serif;font-size:28px;font-weight:600;margin:7px 0}
.section-heading p{color:#84909a;font-size:12px;margin:0}
.box{background:#fff;border:1px solid var(--line);padding:30px;margin-bottom:23px}
.box h3{font-size:17px;margin:0 0 18px;padding-bottom:15px;border-bottom:1px solid var(--line)}
.box p{color:#606d78;line-height:2}
.intro-grid{display:grid;grid-template-columns:1.3fr 1fr;gap:23px}
.overview{display:grid;grid-template-columns:130px 1fr;border-top:1px solid var(--line)}
.overview dt,.overview dd{margin:0;padding:13px 12px;border-bottom:1px solid var(--line);font-size:13px}
.overview dt{background:#f8f9fa;color:#687684}
.overview dd{line-height:1.8}
.quick-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin:23px 0}
.quick{border:1px solid var(--line);background:#fff;text-align:left;padding:24px;min-height:135px;transition:.2s}
.quick:hover{border-color:var(--accent);transform:translateY(-2px)}
.quick .num{font-size:11px;letter-spacing:2px;color:var(--accent)}
.quick strong{display:block;margin:16px 0 6px;font-size:17px}
.quick span{font-size:12px;color:#89939c}
.news-row{display:flex;gap:24px;border-bottom:1px solid var(--line);padding:15px 0;align-items:flex-start}
.news-row time{font-size:12px;color:#87929c;white-space:nowrap}
.news-row span{font-size:13px;line-height:1.8}
.photo-panel{background:#fff;border:1px solid var(--line);padding:22px;margin-bottom:24px}
.photo-panel img{display:block;max-width:100%;max-height:900px;width:auto;height:auto;object-fit:contain;margin:auto;cursor:zoom-in}
.photo-panel .image-label{display:flex;justify-content:space-between;align-items:center;gap:10px;margin-bottom:18px;padding-bottom:13px;border-bottom:1px solid var(--line)}
.image-label strong{font-size:15px}
.image-label small{font-size:11px;color:#8a959e}
.image-caption{text-align:center;color:#88949d;font-size:11px;margin:16px 0 2px}
.uniform-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px}
.uniform-grid .photo-panel{margin:0}
.uniform-grid .photo-panel img{max-height:620px}
.players{display:grid;grid-template-columns:repeat(3,1fr);gap:19px}
.player{background:#fff;border:1px solid var(--line);padding:23px;position:relative}
.player .number{position:absolute;right:20px;top:13px;font-family:Georgia,serif;font-size:49px;color:#e5e9ec}
body.koga .player .number{color:#efe5dd}
.player .school-label{font-size:10px;letter-spacing:1px;color:var(--accent);position:relative}
.player h3{font-size:19px;margin:15px 0 3px;position:relative}
.player .jp{font-size:12px;color:#929ca5;margin-bottom:16px}
.player .tags{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:13px}
.player .tags span{background:#f1f3f5;padding:5px 8px;font-size:11px;color:#5f6d78}
.player p{font-size:12px;color:#67747e;line-height:1.9;margin:0}
.info-note{font-size:12px;color:#88939e;line-height:1.9;margin:17px 0}
.school-footer{background:#24303b;color:#c6cdd3;padding:37px 0}
body.koga .school-footer{background:#302a27}
.school-footer .wrap{display:flex;align-items:center;gap:18px}
.school-footer img{width:55px;height:55px;object-fit:contain}
.school-footer strong{color:#fff;font-size:15px}
.school-footer p{font-size:11px;line-height:1.9;margin:6px 0;color:#aab5bf}

/* 주변 생활권 지도 */
.map-toolbar{display:flex;gap:7px;flex-wrap:wrap;margin-bottom:16px}
.map-toolbar button{border:1px solid #dce2e7;background:white;padding:9px 14px;font-size:12px;color:#596773}
.map-toolbar button.active{background:var(--navy);border-color:var(--navy);color:white}
.map-layout{display:grid;grid-template-columns:minmax(0,1fr) 290px;gap:18px}
.map-canvas{height:520px;overflow:hidden;position:relative;border:1px solid #dce3e7;background:#eef0eb;touch-action:none;cursor:grab}
.map-canvas:active{cursor:grabbing}
.map-world{position:absolute;inset:0;width:100%;height:100%;transform-origin:center}
.map-world svg{width:100%;height:100%;display:block}
.map-pin{position:absolute;transform:translate(-50%,-100%);border:2px solid #fff;border-radius:5px;background:#fff;color:#3c5569;padding:8px 10px;font-size:11px;box-shadow:0 2px 8px #0002;white-space:nowrap}
.map-pin:before{content:"";position:absolute;bottom:-8px;left:calc(50% - 5px);border-left:5px solid transparent;border-right:5px solid transparent;border-top:7px solid #fff}
.map-pin.selected{background:var(--navy);color:#fff;z-index:3}
.map-pin.selected:before{border-top-color:var(--navy)}
.map-zoom{position:absolute;right:13px;top:13px;display:grid;gap:4px}
.map-zoom button{border:1px solid #dbe0e4;background:#fff;width:35px;height:35px;font-size:18px}
.map-detail{background:#fff;border:1px solid var(--line);padding:25px}
.map-detail .type{color:var(--accent);font-size:11px;letter-spacing:1px}
.map-detail h3{font-size:20px;margin:12px 0}
.map-detail p{font-size:13px;line-height:2;color:#67737d}
.map-detail .fiction{border-top:1px solid var(--line);padding-top:15px;font-size:11px;color:#98a2ab}
.map-legend{font-size:11px;color:#89959d;line-height:1.9;margin-top:14px}

/* 이미지 확대 */
.lightbox{position:fixed;inset:0;background:#0d141be9;z-index:100;display:flex;align-items:center;justify-content:center;padding:55px 20px 20px}
.lightbox img{max-width:96vw;max-height:86vh;object-fit:contain}
.lightbox button{position:absolute;right:20px;top:15px;color:#fff;background:none;border:0;font-size:30px}

/* 모바일 */
@media(max-width:900px){
.navigation button{padding:0 12px}
.intro-grid{grid-template-columns:1fr}
.players{grid-template-columns:repeat(2,1fr)}
.map-layout{grid-template-columns:1fr}
.map-canvas{height:450px}
}
@media(max-width:650px){
.wrap{width:calc(100% - 32px)}
.portal-header{padding:20px 0}
.portal-main{padding:48px 0 65px}
.portal-heading{margin-bottom:35px}
.school-list{grid-template-columns:1fr;gap:15px}
.school-link{min-height:260px;padding:25px 20px}
.school-link img{width:91px;height:91px;margin-bottom:12px}
.school-link .serif{font-size:23px}
.school-link .visit{padding-top:13px}
.site-header .wrap{min-height:84px}
.identity{gap:11px}
.identity img{width:57px;height:57px}
.identity h1{font-size:20px}
.identity small{font-size:9px;letter-spacing:1px}
.header-side{display:none}
.menu-toggle{display:block}
.navigation{display:none}
.navigation.open{display:block}
.navigation .wrap{width:100%;display:grid;grid-template-columns:1fr 1fr}
.navigation button{min-height:49px;border:1px solid #ffffff16;text-align:left;padding-left:19px}
.site-banner .wrap{min-height:230px}
.banner-copy{padding:35px 0}
.banner-copy h2{font-size:28px}
.banner-emblem{width:105px;height:105px}
main{padding:29px 0 60px}
.box{padding:21px}
.section-heading h2{font-size:24px}
.quick-grid{grid-template-columns:1fr 1fr;gap:10px}
.quick{padding:17px;min-height:120px}
.quick strong{font-size:14px}
.uniform-grid{grid-template-columns:1fr}
.players{grid-template-columns:1fr}
.photo-panel{padding:13px}
.photo-panel .image-label{padding:5px 3px 12px}
.map-canvas{height:390px}
.news-row{gap:12px}
.school-footer .wrap{align-items:flex-start}
}
@media(max-width:390px){
.banner-emblem{display:none}
.quick-grid{grid-template-columns:1fr}
}
</style>
</head>
<body>

<!-- 학교 선택 -->
<div id="portal">
  <div class="portal-top"></div>
  <div class="portal-header">
    <div class="wrap">
      <strong>PUCK WO MEZASHITE! <span style="font-weight:400;color:#8c969e">｜学校案内</span></strong>
      <small>OFFICIAL SCHOOL GUIDE</small>
    </div>
  </div>
  <div class="portal-main">
    <div class="wrap">
      <div class="portal-heading">
        <div class="eyebrow">SCHOOL INFORMATION</div>
        <h1 class="serif">学校案内</h1>
        <p>학교를 선택하시면 각 학교의 공식 안내 페이지로 이동합니다.</p>
      </div>
      <div class="school-list">
        <button class="school-link" onclick="enterSchool('hokurei')">
          <img id="portalHLogo" alt="호쿠레이학원 엠블럼">
          <div class="serif">北嶺学園高等学校</div>
          <div class="kr">호쿠레이학원</div>
          <div class="meta">EST. 1970 · KUSHIRO, HOKKAIDO</div>
          <span class="visit">공식 홈페이지 방문</span>
        </button>
        <button class="school-link orange" onclick="enterSchool('koga')">
          <img id="portalKLogo" alt="코가학원 엠블럼">
          <div class="serif">虎牙学園高等学校</div>
          <div class="kr">코가학원</div>
          <div class="meta">EST. 2018 · SAPPORO, HOKKAIDO</div>
          <span class="visit">공식 홈페이지 방문</span>
        </button>
      </div>
    </div>
  </div>
  <div class="portal-footer">
    PUCK WO MEZASHITE! · SCHOOL INFORMATION PORTAL<br>
    본 사이트는 창작 작품 《퍽을 향해!》의 가상 학교 안내 사이트입니다.
  </div>
</div>

<!-- 학교 홈페이지 -->
<div id="schoolSite" class="hidden">
  <div class="site-top">
    <div class="wrap">
      <span>HOKKAIDO · JAPAN</span>
      <button onclick="goPortal()">학교 선택으로 돌아가기 ↗</button>
    </div>
  </div>
  <div class="site-header">
    <div class="wrap">
      <div class="identity" onclick="showPage('home')">
        <img id="siteLogo" alt="학교 엠블럼">
        <div>
          <small>PRIVATE HIGH SCHOOL</small>
          <h1 class="serif" id="siteName"></h1>
          <div class="kr" id="siteKr"></div>
        </div>
      </div>
      <div class="header-side">
        <div class="motto" id="headerMotto"></div>
        <div id="headerLocation"></div>
      </div>
      <button class="menu-toggle" id="menuToggle" onclick="toggleMenu()">☰ MENU</button>
    </div>
  </div>
  <nav class="navigation" id="navigation">
    <div class="wrap">
      <button data-page="home" onclick="showPage('home')">홈</button>
      <button data-page="about" onclick="showPage('about')">학교 소개</button>
      <button data-page="campus" onclick="showPage('campus')">캠퍼스 안내</button>
      <button data-page="map" onclick="showPage('map')">주변 지역 안내</button>
      <button data-page="uniform" onclick="showPage('uniform')">교복·체육복</button>
      <button data-page="hockey" onclick="showPage('hockey')">아이스하키부</button>
      <button data-page="players" onclick="showPage('players')">선수 소개</button>
    </div>
  </nav>
  <section class="site-banner">
    <div class="wrap">
      <div class="banner-copy">
        <small id="bannerSmall"></small>
        <h2 id="bannerTitle"></h2>
        <p id="bannerText"></p>
      </div>
      <img class="banner-emblem" id="bannerEmblem" alt="">
    </div>
  </section>
  <div class="breadcrumb">
    <div class="wrap" id="breadcrumb">HOME</div>
  </div>
  <main class="wrap fade" id="content"></main>
  <footer class="school-footer">
    <div class="wrap">
      <img id="footerLogo" alt="">
      <div>
        <strong id="footerName"></strong>
        <p id="footerInfo"></p>
        <p>© 2020 PUCK WO MEZASHITE! · FICTIONAL SCHOOL WEBSITE</p>
      </div>
    </div>
  </footer>
</div>

<!-- 이미지 확대 -->
<div class="lightbox hidden" id="lightbox" onclick="closeImage()">
  <button aria-label="닫기">×</button>
  <img id="lightboxImage" alt="확대 이미지" onclick="event.stopPropagation()">
</div>

<script>
/* 제공된 Cloudflare R2 이미지 주소 */
const ASSET_BASE =
 "https://pub-19e3891ce94f4c209eb7264ad1339087.r2.dev/";
const ASSET_FOLDER="퍽을 향해/";
function asset(filename){
 return ASSET_BASE+encodeURIComponent("퍽을 향해")+"/"+encodeURIComponent(filename);
}

const DATA={
 hokurei:{
  name:"北嶺学園高等学校",
  short:"北嶺学園",
  kr:"호쿠레이학원",
  en:"HOKUREI ACADEMY",
  location:"홋카이도 구시로 인근",
  founded:"1970년",
  mascot:"참수리",
  colors:"남색 · 흰색 · 진홍색",
  motto:"전통이, 앞으로도 날개가 된다",
  description:"홋카이도 구시로 인근에 위치한 전통 사립 고등학교. 협동과 책임감을 중시하며 오랜 역사 속에서 학교의 전통을 이어가고 있습니다.",
  team:"조직적인 수비, 정확한 패스, 협동을 바탕으로 경기를 풀어가는 전통 강호. 선수들 사이에는 가족 같은 유대감과 장난스러운 분위기가 공존합니다.",
  coach:"사에키 토시오 (佐伯 俊夫)",
  coachDetail:"56세 · 기본기, 팀워크, 스포츠맨십을 중시하는 베테랑 감독",
  rink:"교내 아이스링크 없음. 구시로 인근 지역 공용 링크를 이용합니다.",
  logo:asset("호쿠레이_엠블럼.png"),
  campus:asset("호쿠레이_캠퍼스.jpg"),
  uniform:asset("호쿠레이_교복·체육복.png"),
  jersey:asset("호쿠레이_유니폼.jpg"),
  jerseyWear:asset("호쿠레이_유니폼2.jpg"),
  players:[
   {name:"후지사와 소우타",jp:"藤沢 蒼太",grade:"3학년",pos:"C",no:10,birth:"2002.08.18",person:"다정하고 책임감 강한 주장. 남을 돌보지만 자신의 어려움은 숨긴다.",play:"넓은 시야·패스·연계·지휘"},
   {name:"미야자키 슈헤이",jp:"宮崎 修平",grade:"3학년",pos:"LW",no:17,birth:"2002.11.06",person:"성실하고 엄격한 노력파. 무뚝뚝하지만 배려 깊다.",play:"정확한 슛·지구력·위치 선정"},
   {name:"아사히나 나기",jp:"朝比奈 凪",grade:"2학년",pos:"G",no:30,birth:"2003.07.23",person:"나른하고 능청스러운 장난꾸러기. 관찰력이 뛰어나다.",play:"빠른 반사신경·예측형 골리"},
   {name:"하세가와 아오이",jp:"長谷川 葵",grade:"2학년",pos:"LD",no:4,birth:"2003.09.14",person:"수줍고 상냥한 평화주의자. 지켜야 할 때는 단호하다.",play:"안정적인 수비·세심한 커버"},
   {name:"오가와 리쿠",jp:"小川 陸",grade:"2학년",pos:"RW",no:19,birth:"2003.12.05",person:"시끄럽고 장난 많은 분위기 메이커. 외로움과 진심에 약하다.",play:"빠른 측면 돌파·기회 포착"},
   {name:"키리시마 레이",jp:"霧島 怜",grade:"1학년",pos:"RD",no:6,birth:"2004.10.28",person:"냉정하고 꼼꼼한 원칙주의 막내. 선배에게도 잔소리를 한다.",play:"위치 선정·위험 차단·효율적 패스"}
  ],
  places:[
   {name:"호쿠레이학원",type:"학교",x:44,y:45,desc:"구시로 인근 외곽에 자리한 전통 사립 고등학교."},
   {name:"학교 기숙사",type:"학교",x:30,y:31,desc:"학생들이 생활하는 기숙사."},
   {name:"지역 공용 링크",type:"하키",x:71,y:27,desc:"호쿠레이 하키부가 훈련하는 공용 빙상장. 지역 주민들도 이용합니다."},
   {name:"단골 식당",type:"음식",x:63,y:63,desc:"훈련을 마친 선수들이 들를 수 있는 작은 식당. 세부 설정은 추후 확정합니다."},
   {name:"작은 상점가",type:"상업",x:26,y:67,desc:"오래된 가게와 편의점이 모인 조용한 상점가."},
   {name:"산책 공원",type:"자연",x:80,y:77,desc:"숲길과 쉼터가 있는 한적한 녹지 공간."}
  ]
 },
 koga:{
  name:"虎牙学園高等学校",
  short:"虎牙学園",
  kr:"코가학원",
  en:"KOGA ACADEMY",
  location:"홋카이도 삿포로 중심부",
  founded:"2018년",
  mascot:"호랑이",
  colors:"주황색 · 검정색 · 금색",
  motto:"새로운 승자로, 시대를 물어뜯는다",
  description:"2018년 삿포로 중심부에 설립된 신생 사립 스포츠학교. 기업 지원을 바탕으로 현대적인 시설과 전문적인 스포츠 교육 환경을 갖추고 있습니다.",
  team:"빠른 공격과 개인기, 과감한 돌파를 중시하는 신생 강호. 선수들의 강한 개성을 바탕으로 팀워크를 발전시켜 나가고 있습니다.",
  coach:"나루세 켄토 (成瀬 健斗)",
  coachDetail:"41세 · 영상 분석과 전술을 중시하는 냉철한 감독",
  rink:"교내 전용 아이스하키 링크 운영. 외부 대여는 허용되지 않습니다.",
  logo:asset("코가_엠블럼.png"),
  campus:asset("코가_캠퍼스.jpg"),
  uniform:asset("코가_교복·체육복.png"),
  jersey:asset("코가_유니폼.png"),
  jerseyWear:asset("코가_유니폼2.jpg"),
  players:[
   {name:"쿠로사키 타이가",jp:"黒崎 大河",grade:"3학년",pos:"C",no:9,birth:"2002.07.17",person:"호탕하고 직설적인 승부사. 도전을 즐기며 동료를 아낀다.",play:"강력한 돌파·몸싸움·공격적 지휘"},
   {name:"이치노세 아키토",jp:"一ノ瀬 晃人",grade:"3학년",pos:"RD",no:27,birth:"2002.12.12",person:"사교적이고 여유로운 계산형 전략가.",play:"전술 분석·흐름 통제·정교한 수비 전환"},
   {name:"미나미 하루",jp:"南 晴",grade:"2학년",pos:"RW",no:11,birth:"2003.06.21",person:"밝고 사교적이며 유행에 민감하다. 공감을 잘한다.",play:"경쾌한 스케이팅·빠른 연계·즉흥 공격"},
   {name:"쿠라모토 세이",jp:"倉本 誠",grade:"2학년",pos:"G",no:1,birth:"2003.11.19",person:"까칠하고 예민한 완벽주의자. 책임감이 강하다.",play:"정확한 자세·각도 계산·집중력 높은 골리"},
   {name:"토도 에이스케",jp:"藤堂 瑛介",grade:"1학년",pos:"LW",no:10,birth:"2004.08.08",person:"겁 없고 시끄러운 천재형 신입. 인정욕구가 강하다.",play:"폭발적 가속·변칙 돌파·본능적 공격"},
   {name:"츠키시로 이오리",jp:"月城 伊織",grade:"1학년",pos:"C",no:16,birth:"2004.12.24",person:"조용하고 무표정한 분석가. 호기심이 많고 감정 표현이 서툴다.",play:"패턴 분석·정확한 타이밍·효율적 움직임"}
  ],
  places:[
   {name:"코가학원",type:"학교",x:44,y:45,desc:"삿포로 중심부에 위치한 신생 스포츠 특화 사립학교."},
   {name:"교내 전용 링크",type:"하키",x:54,y:35,desc:"학교 내부에 있는 하키부 전용 링크. 외부 대여는 금지됩니다."},
   {name:"대형 쇼핑몰",type:"상업",x:73,y:25,desc:"쇼핑과 식사를 즐길 수 있는 도심 복합 상업시설. 가상 장소 시안."},
   {name:"영화관",type:"상업",x:78,y:64,desc:"방과 후 여가를 즐길 수 있는 영화관. 가상 장소 시안."},
   {name:"카페 거리",type:"음식",x:27,y:65,desc:"카페와 음식점이 모여 있는 번화가. 가상 장소 시안."},
   {name:"중앙 공원",type:"자연",x:18,y:26,desc:"도심 한가운데 자리한 공원과 산책로."}
  ]
 }
};

let school="hokurei",page="home",category="전체",chosen=0;
let scale=1,offsetX=0,offsetY=0;

const el=id=>document.getElementById(id);
const d=()=>DATA[school];

el("portalHLogo").src=DATA.hokurei.logo;
el("portalKLogo").src=DATA.koga.logo;

function enterSchool(key){
 school=key;
 document.body.classList.toggle("koga",key==="koga");
 el("portal").classList.add("hidden");
 el("schoolSite").classList.remove("hidden");
 const s=d();
 el("siteLogo").src=s.logo;
 el("bannerEmblem").src=s.logo;
 el("footerLogo").src=s.logo;
 el("siteName").textContent=s.short;
 el("siteKr").textContent=s.kr;
 el("headerMotto").textContent="「"+s.motto+"」";
 el("headerLocation").textContent=s.location;
 el("footerName").textContent=s.name;
 el("footerInfo").textContent=s.location+" · "+s.founded+" 설립";
 el("navigation").classList.remove("open");
 showPage("home");
}
function goPortal(){
 el("schoolSite").classList.add("hidden");
 el("portal").classList.remove("hidden");
 el("navigation").classList.remove("open");
 window.scrollTo(0,0);
}
function toggleMenu(){
 const nav=el("navigation");
 nav.classList.toggle("open");
 el("menuToggle").textContent=nav.classList.contains("open")?"✕ CLOSE":"☰ MENU";
}
const pageNames={
 home:"학교 홈",about:"학교 소개",campus:"캠퍼스 안내",
 map:"주변 지역 안내",uniform:"교복·체육복",
 hockey:"아이스하키부",players:"선수 소개"
};
function heading(en,kr,sub=""){
 return `<div class="section-heading"><div class="en">${en}</div><h2>${kr}</h2><p>${sub}</p></div>`;
}
function infoRows(rows){
 return `<dl class="overview">${rows.map(r=>`<dt>${r[0]}</dt><dd>${r[1]}</dd>`).join("")}</dl>`;
}
function photo(src,title,sub=""){
 return `<div class="photo-panel">
 <div class="image-label"><strong>${title}</strong><small>클릭하여 확대</small></div>
 <img src="${src}" alt="${title}" loading="lazy" onclick="openImage(this.src)">
 ${sub?`<p class="image-caption">${sub}</p>`:""}
 </div>`;
}
function openImage(src){
 el("lightboxImage").src=src;
 el("lightbox").classList.remove("hidden");
 document.body.style.overflow="hidden";
}
function closeImage(){
 el("lightbox").classList.add("hidden");
 document.body.style.overflow="";
}
document.addEventListener("keydown",e=>{
 if(e.key==="Escape")closeImage();
});

function showPage(next){
 page=next;
 const s=d();
 document.querySelectorAll("[data-page]").forEach(b=>
  b.classList.toggle("active",b.dataset.page===next));
 el("navigation").classList.remove("open");
 el("menuToggle").textContent="☰ MENU";
 el("breadcrumb").textContent="HOME / "+pageNames[next];
 el("bannerSmall").textContent=s.en+" · OFFICIAL WEBSITE";
 el("bannerTitle").textContent=
  next==="home"?"「"+s.motto+"」":pageNames[next];
 el("bannerText").textContent=
  next==="home"?s.description:
  s.kr+"의 "+pageNames[next]+" 페이지입니다.";
 let html="";

 if(next==="home"){
  html=heading("WELCOME",s.kr+"에 오신 것을 환영합니다",
   "학교 소개와 캠퍼스, 학생 활동을 안내합니다.")+
  `<div class="intro-grid">
   <div class="box"><h3>학교 소개</h3>
   <p>${s.description}</p>
   <p style="font-family:'Noto Serif JP',serif;color:var(--navy)">
   「${s.motto}」</p></div>
   <div class="box"><h3>학교 기본 정보</h3>
   ${infoRows([
    ["학교명",s.name],
    ["소재지",s.location],
    ["설립",s.founded],
    ["학교 상징",s.mascot]
   ])}</div>
  </div>
  <div class="quick-grid">
   ${[
    ["01","학교 소개","학교의 역사와 교육 환경","about"],
    ["02","캠퍼스 안내","교내 시설과 학교 지도","campus"],
    ["03","주변 지역","학교 주변 생활권","map"],
    ["04","교복 안내","교복과 체육복","uniform"],
    ["05","아이스하키부","팀 소개와 유니폼","hockey"],
    ["06","선수 소개","아이스하키부 선수 명단","players"]
   ].map(x=>`<button class="quick" onclick="showPage('${x[3]}')">
    <div class="num">${x[0]} / SCHOOL GUIDE</div>
    <strong>${x[1]} →</strong><span>${x[2]}</span></button>`).join("")}
  </div>
  <div class="box"><h3>학교 공지사항</h3>
   <div class="news-row"><time>2020.04</time><span>2020학년도 학교 안내 페이지를 공개합니다.</span></div>
   <div class="news-row"><time>2020.04</time><span>아이스하키부 선수 소개 페이지를 확인하실 수 있습니다.</span></div>
   <p class="info-note">※ 작품 세계관에 맞춘 가상의 학교 안내입니다. 상세 행사 공지는 추후 추가됩니다.</p>
  </div>`;
 }

 if(next==="about"){
  html=heading("ABOUT SCHOOL","학교 개요","学校概要")+
  `<div class="box"><h3>학교 기본 정보</h3>
  ${infoRows([
   ["정식 명칭",s.name],
   ["한국어 명칭",s.kr],
   ["소재지",s.location],
   ["설립 연도",s.founded],
   ["학교 상징",s.mascot],
   ["학교 색상",s.colors],
   ["학교 표어",s.motto]
  ])}</div>
  <div class="box"><h3>학교 소개</h3><p>${s.description}</p></div>
  <div class="box"><h3>아이스하키부 운영</h3><p>${s.team}</p><p>${s.rink}</p></div>`;
 }

 if(next==="campus"){
  html=heading("CAMPUS GUIDE","캠퍼스 안내","校内案内図")+
   photo(s.campus,s.kr+" 캠퍼스 안내도",
    "학교 내부 시설을 안내하는 공식 캠퍼스 지도")+
   `<p class="info-note">학교 주변의 식당·상점가·빙상장 등은 '주변 지역 안내' 메뉴에서 확인할 수 있습니다.</p>`;
 }

 if(next==="uniform"){
  html=heading("SCHOOL UNIFORM","교복·체육복 안내","制服・体育着")+
   photo(s.uniform,s.kr+" 교복 및 체육복",
    "공식 복장 자료 · 이미지를 클릭하면 크게 볼 수 있습니다.")+
   `<div class="box"><h3>복장 안내</h3>
    <p>본 페이지의 복장 이미지는 학교별 공식 설정 자료를 사용합니다.</p>
   </div>`;
 }

 if(next==="hockey"){
  html=heading("ICE HOCKEY CLUB","아이스하키부","アイスホッケー部")+
   `<div class="box"><h3>하키부 소개</h3><p>${s.team}</p>
    ${infoRows([
     ["지도 감독",s.coach],
     ["감독 소개",s.coachDetail],
     ["훈련 시설",s.rink],
     ["소속 선수","주요 선수 6명"]
    ])}</div>`+
   heading("TEAM UNIFORM","하키 유니폼","HOME / AWAY")+
   `<div class="uniform-grid">
    ${photo(s.jersey,"유니폼 디자인 · 설명")}
    ${photo(s.jerseyWear,"유니폼 착장")}
   </div>`;
 }

 if(next==="players"){
  html=heading("PLAYER ROSTER","아이스하키부 선수 소개",
   "2020학년도 주요 선수 6명")+
   `<div class="players">${s.players.map(p=>`
    <article class="player">
     <div class="number">${p.no}</div>
     <div class="school-label">${s.en} · HOCKEY CLUB</div>
     <h3>${p.name}</h3><div class="jp">${p.jp}</div>
     <div class="tags">
      <span>${p.grade}</span><span>${p.pos}</span>
      <span>NO. ${p.no}</span>
     </div>
     <p><strong>생년월일</strong> · ${p.birth}</p>
     <p><strong>성격</strong> · ${p.person}</p>
     <p><strong>플레이</strong> · ${p.play}</p>
    </article>`).join("")}</div>
   <p class="info-note">선수 이미지와 상세 프로필은 추후 추가할 수 있습니다.</p>`;
 }

 if(next==="map"){
  html=heading("NEIGHBORHOOD MAP","주변 지역 안내",
   "학교와 학생들의 주요 생활권")+
  `<div class="map-toolbar" id="mapFilters"></div>
   <div class="map-layout">
    <div class="map-canvas" id="mapCanvas">
     <div class="map-world" id="mapWorld">
      ${drawMap()}
      <div id="mapPins"></div>
     </div>
     <div class="map-zoom">
      <button onclick="changeScale(.2)" aria-label="확대">+</button>
      <button onclick="changeScale(-.2)" aria-label="축소">−</button>
      <button onclick="resetMap()" aria-label="초기화">⌖</button>
     </div>
    </div>
    <div class="map-detail" id="mapDetail"></div>
   </div>
   <p class="map-legend">
    ※ 이 지도는 실제 Google Maps가 아닌 창작 세계관 지도입니다.
    실제 구시로·삿포로의 지리적 분위기를 참고한 디자인 시안이며,
    장소와 도로 위치는 현실의 위치를 나타내지 않습니다.
   </p>`;
 }

 el("content").innerHTML=html;
 el("content").classList.remove("fade");
 void el("content").offsetWidth;
 el("content").classList.add("fade");
 if(next==="map"){
  category="전체";chosen=0;resetValues();
  renderMap();
  enableMapDrag();
 }
 window.scrollTo(0,0);
}

/* 가상 생활권 지도 */
function drawMap(){
 const urban=school==="koga";
 let buildings="";
 for(let i=0;i<(urban?92:30);i++){
  const x=(i*139+27)%960;
  const y=(i*83+49)%625;
  buildings+=`<rect x="${x}" y="${y}" width="${urban?42:27}"
   height="${urban?26:19}" rx="2"
   fill="${urban?'#d8dbde':'#dbe0d8'}"/>`;
 }
 const roads=urban?`
  <path d="M0 95H1000 M0 205H1000 M0 325H1000
   M0 455H1000 M0 575H1000 M110 0V650
   M255 0V650 M430 0V650 M605 0V650
   M805 0V650" stroke="#fff" stroke-width="34" fill="none"/>
  <path d="M0 325H1000 M430 0V650"
   stroke="#f5d18d" stroke-width="20" fill="none"/>
 `:`
  <path d="M0 175Q420 260 1000 80
   M0 505Q430 385 1000 530
   M290 0Q400 310 230 650
   M710 0Q590 350 825 650"
   stroke="#fff" stroke-width="31" fill="none"/>
  <path d="M0 505Q430 385 1000 530"
   stroke="#f4d79a" stroke-width="18" fill="none"/>
 `;
 return `<svg viewBox="0 0 1000 650"
  preserveAspectRatio="xMidYMid slice"
  xmlns="http://www.w3.org/2000/svg">
  <rect width="1000" height="650" fill="${urban?'#f1f0ee':'#edf1e8'}"/>
  <path d="${urban?
   'M0 0H245V150H0Z M735 485H1000V650H720Z':
   'M0 0H355V255H0Z M720 370H1000V650H710Z'}"
   fill="#cce5c3"/>
  ${buildings}
  ${roads}
  <path d="${urban?
   'M950 0Q885 275 1000 650':
   'M0 55Q110 170 55 340Q15 470 115 650'}"
   stroke="#b4ddf1" stroke-width="${urban?28:62}" fill="none"/>
  <g font-family="Noto Sans JP,sans-serif" fill="#85929a"
   font-size="18">
   <text x="65" y="110">${urban?'中央公園':'緑の丘'}</text>
   <text x="510" y="120">${urban?'商業地区':'郊外住宅地'}</text>
   <text x="680" y="560">${urban?'駅前通り':'地域道路'}</text>
  </g>
 </svg>`;
}
function renderMap(){
 const filters=["전체","학교","하키","음식","상업","자연"];
 el("mapFilters").innerHTML=filters.map(t=>
  `<button class="${category===t?'active':''}"
   onclick="changeCategory('${t}')">${t}</button>`).join("");
 el("mapPins").innerHTML=d().places.map((p,i)=>
  (category==="전체"||category===p.type)?
  `<button class="map-pin ${chosen===i?'selected':''}"
   style="left:${p.x}%;top:${p.y}%"
   onclick="selectPlace(${i})">${p.name}</button>`:"").join("");
 const p=d().places[chosen];
 el("mapDetail").innerHTML=`
  <div class="type">${p.type.toUpperCase()} · LOCATION</div>
  <h3>${p.name}</h3><p>${p.desc}</p>
  <div class="fiction">창작 세계관의 가상 장소입니다.</div>`;
}
function selectPlace(i){chosen=i;renderMap();}
function changeCategory(t){
 category=t;
 const i=d().places.findIndex(p=>t==="전체"||p.type===t);
 if(i>=0)chosen=i;
 renderMap();
}
function resetValues(){scale=1;offsetX=0;offsetY=0;}
function applyMapTransform(){
 el("mapWorld").style.transform=
  `translate(${offsetX}px,${offsetY}px) scale(${scale})`;
}
function changeScale(n){
 scale=Math.min(2.4,Math.max(.8,scale+n));
 applyMapTransform();
}
function resetMap(){resetValues();applyMapTransform();}
function enableMapDrag(){
 const canvas=el("mapCanvas");
 let drag=null;
 canvas.onpointerdown=e=>{
  if(e.target.closest("button"))return;
  drag={x:e.clientX-offsetX,y:e.clientY-offsetY};
  canvas.setPointerCapture(e.pointerId);
 };
 canvas.onpointermove=e=>{
  if(!drag)return;
  offsetX=e.clientX-drag.x;
  offsetY=e.clientY-drag.y;
  applyMapTransform();
 };
 canvas.onpointerup=()=>drag=null;
 canvas.onpointercancel=()=>drag=null;
 canvas.onwheel=e=>{
  e.preventDefault();
  changeScale(e.deltaY<0?.12:-.12);
 };
}
</script>
</body>
</html>
