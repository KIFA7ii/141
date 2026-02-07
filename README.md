
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>باقة الذكاء الاصطناعي — تصميم فاخر</title>

  <style>
    :root{
      --bg0:#05060b;
      --bg1:#0a0c18;
      --card:rgba(255,255,255,.06);
      --stroke:rgba(255,255,255,.14);
      --text:#f5f7ff;
      --muted:rgba(245,247,255,.72);
      --gold:#d6b56c;
      --gold2:#f2da9a;
      --accent:#7c5cff;
      --ok:#22c55e;
      --shadow: 0 30px 90px rgba(0,0,0,.55);
      --radius:22px;
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: system-ui, -apple-system, "Segoe UI", Tahoma, Arial, sans-serif;
      color:var(--text);
      background:
        radial-gradient(900px 500px at 15% 10%, rgba(214,181,108,.22), transparent 55%),
        radial-gradient(900px 500px at 85% 20%, rgba(124,92,255,.18), transparent 55%),
        radial-gradient(800px 500px at 60% 85%, rgba(34,197,94,.12), transparent 55%),
        linear-gradient(180deg, var(--bg0), var(--bg1));
      overflow-x:hidden;
    }

    /* floating blobs */
    .blob{
      position:fixed;
      width:420px;height:420px;
      border-radius:999px;
      filter: blur(35px);
      opacity:.22;
      pointer-events:none;
      z-index:-1;
      animation: float 10s ease-in-out infinite;
    }
    .b1{left:-120px; top:40px; background:radial-gradient(circle at 30% 30%, var(--gold), transparent 60%);}
    .b2{right:-140px; top:120px; background:radial-gradient(circle at 30% 30%, var(--accent), transparent 60%); animation-duration: 12s;}
    .b3{left:30%; bottom:-180px; background:radial-gradient(circle at 30% 30%, var(--ok), transparent 60%); animation-duration: 14s;}
    @keyframes float{
      0%,100%{transform: translate(0,0) scale(1);}
      50%{transform: translate(0,-18px) scale(1.03);}
    }

    .container{
      width:min(1150px, 92%);
      margin-inline:auto;
      padding:42px 0 70px;
      position:relative;
    }

    /* subtle grid */
    .container::before{
      content:"";
      position:absolute;
      inset:-200px -120px auto -120px;
      height:520px;
      background:
        linear-gradient(to right, rgba(255,255,255,.06) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(255,255,255,.06) 1px, transparent 1px);
      background-size: 42px 42px;
      mask-image: radial-gradient(closest-side, rgba(0,0,0,.9), transparent 75%);
      opacity:.23;
      pointer-events:none;
    }

    .topbar{
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:16px;
      margin-bottom:26px;
      position:relative;
      z-index:1;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:10px;
      font-weight:900;
      letter-spacing:.2px;
    }
    .brand .dot{
      width:10px;height:10px;border-radius:999px;
      background:linear-gradient(135deg,var(--gold),var(--gold2));
      box-shadow:0 0 0 6px rgba(214,181,108,.12);
      animation: pulse 2.2s ease-in-out infinite;
    }
    @keyframes pulse{
      0%,100%{transform:scale(1); box-shadow:0 0 0 6px rgba(214,181,108,.12);}
      50%{transform:scale(1.15); box-shadow:0 0 0 10px rgba(214,181,108,.10);}
    }

    .pill{
      display:inline-flex;
      gap:10px;
      align-items:center;
      padding:9px 12px;
      border:1px solid var(--stroke);
      border-radius:999px;
      background:rgba(255,255,255,.04);
      color:var(--muted);
      font-size:13px;
      backdrop-filter: blur(10px);
    }

    .hero{
      display:grid;
      grid-template-columns: 1.25fr .75fr;
      gap:18px;
      align-items:stretch;
      position:relative;
      z-index:1;
    }
    @media (max-width: 980px){ .hero{grid-template-columns:1fr} }

    .card{
      background: linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.04));
      border:1px solid var(--stroke);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
      padding:20px;
      backdrop-filter: blur(14px);
      transform: translateY(10px);
      opacity:0;
      transition: .7s cubic-bezier(.2,.8,.2,1);
    }
    .card.reveal{transform: translateY(0); opacity:1;}

    .heroMain{padding:26px; position:relative; overflow:hidden;}
    .heroMain::after{
      content:"";
      position:absolute;
      inset:-80px -120px auto auto;
      width:360px;height:360px;
      background: radial-gradient(circle at 30% 30%, rgba(214,181,108,.25), transparent 60%),
                  radial-gradient(circle at 70% 70%, rgba(124,92,255,.18), transparent 60%);
      transform: rotate(10deg);
      pointer-events:none;
      animation: shimmerBlob 6s ease-in-out infinite;
      opacity:.9;
    }
    @keyframes shimmerBlob{
      0%,100%{transform: rotate(10deg) translateY(0);}
      50%{transform: rotate(14deg) translateY(-10px);}
    }

    h1{
      margin:0 0 10px;
      font-size: clamp(28px, 3.6vw, 46px);
      line-height:1.2;
      letter-spacing:.2px;
    }
    .subtitle{
      margin:0;
      color:var(--muted);
      font-size: clamp(14px, 1.4vw, 18px);
      max-width: 60ch;
    }

    .highlights{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:12px;
      margin-top:18px;
    }
    @media (max-width: 820px){ .highlights{grid-template-columns:1fr} }

    .hl{
      border:1px solid rgba(255,255,255,.12);
      background:rgba(255,255,255,.03);
      border-radius:18px;
      padding:12px;
      transition: .2s ease;
    }
    .hl:hover{
      transform: translateY(-2px);
      border-color: rgba(214,181,108,.35);
    }
    .hl b{display:block;font-size:15px}
    .hl small{color:var(--muted)}

    .sectionTitle{margin:0 0 10px; font-size:18px; letter-spacing:.2px;}
    .grid2{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:12px;
      margin-top:14px;
    }
    @media (max-width: 820px){ .grid2{grid-template-columns:1fr} }

    ul{margin:0; padding:0 18px 0 0; color:var(--muted);}
    li{margin:8px 0}

    /* Offer */
    .offer{
      padding:22px;
      position:sticky;
      top:16px;
      align-self:start;
    }
    @media (max-width: 980px){ .offer{position:relative; top:auto} }

    .priceRow{
      display:flex;
      align-items:baseline;
      gap:10px;
      flex-wrap:wrap;
      margin:10px 0 0;
    }
    .price{
      font-size:40px;
      font-weight:950;
      background: linear-gradient(135deg, var(--gold), var(--gold2));
      -webkit-background-clip:text;
      background-clip:text;
      color:transparent;
      letter-spacing:.3px;
    }
    .per{color:var(--muted); font-size:13px;}

    /* animated counters */
    .kpis{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:10px;
      margin-top:14px;
    }
    @media (max-width: 980px){ .kpis{grid-template-columns:1fr} }
    .kpi{
      border:1px solid rgba(255,255,255,.12);
      background:rgba(255,255,255,.03);
      border-radius:18px;
      padding:12px;
      transition:.2s ease;
    }
    .kpi:hover{transform:translateY(-2px); border-color:rgba(124,92,255,.35);}
    .kpi .num{font-size:20px; font-weight:900;}
    .kpi small{color:var(--muted);}

    label{display:block; margin-top:10px; font-size:13px; color:var(--muted);}
    input, textarea{
      width:100%;
      margin-top:7px;
      padding:12px 12px;
      border-radius:14px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.20);
      color:var(--text);
      outline:none;
      transition:.15s ease;
    }
    textarea{min-height:92px; resize:vertical;}
    input:focus, textarea:focus{
      border-color: rgba(214,181,108,.55);
      box-shadow: 0 0 0 4px rgba(214,181,108,.14);
    }

    .btn{
      width:100%;
      border:0;
      border-radius:16px;
      padding:13px 14px;
      font-weight:950;
      cursor:pointer;
      margin-top:12px;
      transition: .15s ease;
      display:inline-flex;
      justify-content:center;
      align-items:center;
      gap:10px;
      font-size:15px;
      position:relative;
      overflow:hidden;
    }
    .btn::after{
      content:"";
      position:absolute;
      inset:-60% -40%;
      background: linear-gradient(120deg, transparent, rgba(255,255,255,.18), transparent);
      transform: translateX(-80%);
      transition: transform .6s ease;
    }
    .btn:hover::after{transform: translateX(80%);}
    .btn:hover{transform: translateY(-1px); filter: brightness(1.06);}

    .btnEmail{background: linear-gradient(135deg, #4f46e5, var(--accent)); color:white;}
    .btnWA{background: linear-gradient(135deg, #16a34a, #22c55e); color:white;}

    .fineprint{
      margin:10px 0 0;
      color:rgba(245,247,255,.62);
      font-size:12px;
      line-height:1.6;
    }

    /* CTA top */
    .ctaTop{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:16px;
    }
    .miniBtn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:8px;
      padding:10px 12px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.14);
      background:rgba(255,255,255,.04);
      color:var(--text);
      text-decoration:none;
      font-weight:800;
      transition:.15s ease;
    }
    .miniBtn:hover{transform: translateY(-1px); border-color: rgba(214,181,108,.35);}

    /* FAQ */
    details{
      border:1px solid rgba(255,255,255,.12);
      background:rgba(255,255,255,.03);
      border-radius:16px;
      padding:12px 14px;
      margin:10px 0;
    }
    summary{cursor:pointer; font-weight:900;}
    details p{color:var(--muted); margin:10px 0 0}

    /* reduced motion */
    @media (prefers-reduced-motion: reduce){
      .blob, .brand .dot, .heroMain::after {animation:none}
      .card{transition:none}
      .btn::after{transition:none}
    }

    footer{
      margin-top:26px;
      text-align:center;
      color:rgba(245,247,255,.58);
      font-size:12px;
    }
  </style>
</head>

<body>
  <div class="blob b1"></div>
  <div class="blob b2"></div>
  <div class="blob b3"></div>

  <div class="container">
    <div class="topbar">
      <div class="brand"><span class="dot"></span> Luxury AI Pack</div>
      <div class="pill">✨ Animations • نموذج مزدوج • جاهز للرفع</div>
    </div>

    <section class="hero">
      <div class="card heroMain" data-reveal>
        <div class="pill" style="width:fit-content;border-color:rgba(214,181,108,.26);">
          💎 باقة دعم + قوالب (خدمة قانونية)
        </div>

        <h1>🚀 باقة الذكاء الاصطناعي لتسهيل دراستك وعملك — بسعر مناسب</h1>
        <p class="subtitle">
          خدمة تدريب/دعم واستعمال احترافي للذكاء الاصطناعي: قوالب جاهزة، نصائح تطبيقية، ومساعدة في تحويل أفكارك لنتائج سريعة
          (محتوى، دراسة، عمل، تنظيم).
        </p>

        <div class="ctaTop">
          <a class="miniBtn" href="#order">📝 اطلب الآن</a>
          <a class="miniBtn" href="#faq">❓ أسئلة شائعة</a>
          <a class="miniBtn" href="#details">📌 ماذا ستحصل عليه؟</a>
        </div>

        <div class="highlights">
          <div class="hl">
            <b>نتائج أسرع</b>
            <small>اختصار الوقت بشكل كبير</small>
          </div>
          <div class="hl">
            <b>قوالب جاهزة</b>
            <small>جاهزة للنسخ والتعديل</small>
          </div>
          <div class="hl">
            <b>دعم مباشر</b>
            <small>مساعدة خطوة بخطوة</small>
          </div>
        </div>

        <div class="kpis" style="margin-top:16px;">
          <div class="kpi">
            <div class="num" data-count="12">0</div>
            <small>شهر دعم/متابعة (حسب باقتك)</small>
          </div>
          <div class="kpi">
            <div class="num" data-count="50">0</div>
            <small>DH سعر العرض</small>
          </div>
          <div class="kpi">
            <div class="num" data-count="24">0</div>
            <small>ساعة/24 تفاعل سريع (تقديري)</small>
          </div>
        </div>

        <div class="grid2" id="details" style="margin-top:16px;">
          <div class="card" style="padding:14px;" data-reveal>
            <h2 class="sectionTitle">ستستفيد من</h2>
            <ul>
              <li>✍️ قوالب: سيرة ذاتية، رسائل، إعلانات، محتوى</li>
              <li>📚 طرق فعّالة للشرح والتلخيص وحل الأسئلة</li>
              <li>💡 توليد أفكار للمشاريع والمحتوى</li>
              <li>🧩 تنظيم المهام وخطة عمل واضحة</li>
            </ul>
          </div>

          <div class="card" style="padding:14px;" data-reveal>
            <h2 class="sectionTitle">لماذا نحن؟</h2>
            <ul>
              <li>✅ تواصل سريع واحترافي</li>
              <li>🔒 خصوصية البيانات للتواصل فقط</li>
              <li>⚡ بدء الخدمة بسرعة</li>
              <li>🙋 دعم بعد الطلب</li>
            </ul>
          </div>
        </div>

        <div class="card" style="margin-top:14px; padding:14px;" data-reveal>
          <h2 class="sectionTitle">❓ أسئلة شائعة</h2>
          <div id="faq">
            <details>
              <summary>شنو غادي ناخد بالضبط؟</summary>
              <p>قوالب جاهزة + إرشادات استعمال + دعم لتطبيقها على احتياجك (دراسة/عمل/محتوى).</p>
            </details>
            <details>
              <summary>كيفاش غادي نتواصل؟</summary>
              <p>عبر واتساب أو الإيميل حسب الزر اللي تختار.</p>
            </details>
            <details>
              <summary>واش هادي خدمة رسمية تابعة لـ OpenAI؟</summary>
              <p>لا، هادي خدمة تدريب/دعم واستعمال، وماشي جهة رسمية تابعة.</p>
            </details>
          </div>
        </div>
      </div>

      <aside class="card offer" id="order" data-reveal>
        <div class="pill">💰 عرض خاص</div>
        <div class="priceRow">
          <div class="price">50 DH</div>
          <div class="per">/ باقة دعم + قوالب</div>
        </div>
        <p class="fineprint">
          ✍️ بدّل وصف الباقة حسب خدمتك الحقيقية (تدريب/قوالب/دعم). هذا مثال قانوني.
        </p>

        <!-- Email via FormSubmit (بدون سيرفر) -->
        <form id="orderForm" action="https://formsubmit.co/kifa7i.x.x.kifa7i@gmail.com" method="POST">
          <input type="hidden" name="_subject" value="طلب جديد — باقة الذكاء الاصطناعي (50 DH)">
          <input type="hidden" name="_template" value="table">
          <input type="hidden" name="_captcha" value="true">

          <label>الاسم الكامل *</label>
          <input id="name" name="الاسم" required placeholder="مثال: محمد أحمد"/>

          <label>رقم الهاتف (واتساب) *</label>
          <input id="phone" name="الهاتف" required placeholder="مثال: 06XXXXXXXX"/>

          <label>البريد الإلكتروني *</label>
          <input id="email" type="email" name="الإيميل" required placeholder="name@example.com"/>

          <label>نوع الاحتياج</label>
          <input id="need" name="الاحتياج" placeholder="دراسة / عمل / محتوى"/>

          <label>ملاحظة (اختياري)</label>
          <textarea id="note" name="ملاحظة" placeholder="اكتب طلبك باختصار..."></textarea>

          <button class="btn btnEmail" type="submit">📩 إرسال الطلب إلى الإيميل</button>
          <button class="btn btnWA" type="button" onclick="sendWhatsApp()">💬 إرسال الطلب عبر واتساب</button>

          <p class="fineprint">
            بإرسالك الطلب، أنت توافق على مشاركة هذه البيانات للتواصل بخصوص الخدمة فقط.
          </p>
        </form>
      </aside>
    </section>

    <footer>© <span id="y"></span> — تصميم فاخر مع Animations</footer>
  </div>

  <script>
    document.getElementById("y").textContent = new Date().getFullYear();

    // ✅ ضع رقم الواتساب ديالك بصيغة دولية بدون +
    const WHATSAPP_NUMBER = "212675958697";

    function val(id){ return (document.getElementById(id).value || "").trim(); }

    function sendWhatsApp(){
      const name = val("name");
      const phone = val("phone");
      const email = val("email");
      const need = val("need");
      const note = val("note");

      if(!name || !phone || !email){
        alert("المرجو ملء الاسم + الهاتف + الإيميل أولًا");
        return;
      }

      const msg =
`طلب باقة الذكاء الاصطناعي (50 DH)
-----------------------------
الاسم: ${name}
الهاتف: ${phone}
الإيميل: ${email}
الاحتياج: ${need || "-"}
ملاحظة: ${note || "-"}

أرجو التواصل لتأكيد التفاصيل.`;

      const url = "https://wa.me/" + encodeURIComponent(WHATSAPP_NUMBER) + "?text=" + encodeURIComponent(msg);
      window.open(url, "_blank");
    }

    // Reveal on scroll (IntersectionObserver)
    const revealEls = document.querySelectorAll("[data-reveal], .card");
    const io = new IntersectionObserver((entries)=>{
      entries.forEach(e=>{
        if(e.isIntersecting){
          e.target.classList.add("reveal");
          io.unobserve(e.target);
        }
      });
    }, {threshold: 0.12});
    revealEls.forEach(el => io.observe(el));

    // Animated counters when visible
    const counters = document.querySelectorAll("[data-count]");
    const counterIO = new IntersectionObserver((entries)=>{
      entries.forEach(e=>{
        if(!e.isIntersecting) return;
        const el = e.target;
        const target = Number(el.getAttribute("data-count") || "0");
        const duration = 900; // ms
        const start = performance.now();
        const from = 0;

        function tick(now){
          const t = Math.min(1, (now - start) / duration);
          const val = Math.floor(from + (target - from) * (t * (2 - t))); // easeOut
          el.textContent = val;
          if(t < 1) requestAnimationFrame(tick);
        }
        requestAnimationFrame(tick);
        counterIO.unobserve(el);
      });
    }, {threshold: 0.6});
    counters.forEach(c => counterIO.observe(c));
  </script>
</body>
</html>
