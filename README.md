<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>StudyHub — قائمة الانتظار</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Almarai:wght@700;800&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --paper:#FAF6EC;
    --ink:#20263B;
    --rule:#D9D2BF;
    --accent:#E1912B;
    --accent-ink:#5A3A0E;
    --sage:#7C9A82;
    --danger:#B0473E;
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    min-height:100vh;
    background:var(--paper);
    background-image:
      linear-gradient(var(--rule) 1px, transparent 1px);
    background-size: 100% 42px;
    background-position: 0 160px;
    font-family:'Tajawal', sans-serif;
    color:var(--ink);
    display:flex;
    justify-content:center;
    padding: 48px 20px 64px;
  }
  .wrap{ width:100%; max-width:640px; }

  .brand{
    font-family:'Almarai', sans-serif;
    font-weight:800;
    font-size:15px;
    letter-spacing:.02em;
    color:var(--accent-ink);
    margin-bottom:10px;
  }
  h1{
    font-family:'Almarai', sans-serif;
    font-weight:800;
    font-size:clamp(30px,6vw,42px);
    line-height:1.25;
    margin:0 0 14px;
  }
  .lede{
    font-size:16px;
    line-height:1.8;
    color:#454C63;
    max-width:52ch;
    margin:0 0 30px;
  }

  .features{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:10px;
    margin-bottom:34px;
  }
  .feature{
    background:#fff;
    border:1px solid var(--rule);
    border-radius:10px;
    padding:14px 12px;
    text-align:center;
  }
  .feature .ic{ font-size:20px; display:block; margin-bottom:6px; }
  .feature span{ font-size:13px; line-height:1.5; color:#454C63; }

  .card{
    background:#fff;
    border:1px solid var(--rule);
    border-radius:14px;
    padding:30px 26px;
    box-shadow:0 1px 0 var(--rule);
  }
  .card h2{
    font-family:'Almarai', sans-serif;
    font-size:20px;
    margin:0 0 6px;
  }
  .card p.sub{
    margin:0 0 22px;
    color:#6B7280;
    font-size:14px;
  }

  .field{ margin-bottom:16px; }
  label{
    display:block;
    font-size:13px;
    font-weight:700;
    color:#454C63;
    margin-bottom:6px;
  }
  input{
    width:100%;
    padding:12px 14px;
    border:1.5px solid var(--rule);
    border-radius:8px;
    font-family:'Tajawal', sans-serif;
    font-size:15px;
    background:#FEFCF7;
    color:var(--ink);
    transition:border-color .15s ease;
  }
  input:focus{
    outline:none;
    border-color:var(--accent);
  }
  input::placeholder{ color:#A8AAB8; }

  button{
    width:100%;
    padding:13px;
    margin-top:6px;
    background:var(--accent);
    color:#fff;
    border:none;
    border-radius:8px;
    font-family:'Tajawal', sans-serif;
    font-weight:700;
    font-size:16px;
    cursor:pointer;
    transition:background .15s ease, opacity .15s ease;
  }
  button:hover{ background:#C97E1F; }
  button:disabled{ opacity:.6; cursor:default; }

  .msg{
    margin-top:14px;
    font-size:14px;
    line-height:1.6;
    border-radius:8px;
    padding:10px 12px;
    display:none;
  }
  .msg.ok{ display:block; background:#EEF4EE; color:#3E5B44; border:1px solid var(--sage); }
  .msg.err{ display:block; background:#FBEEEC; color:var(--danger); border:1px solid #E0A9A2; }

  footer{
    text-align:center;
    color:#9AA0B2;
    font-size:12px;
    margin-top:28px;
  }

  @media (max-width:420px){
    .features{ grid-template-columns:1fr; }
    .card{ padding:24px 18px; }
  }
</style>
</head>
<body>
<div class="wrap">

  <div class="brand">StudyHub</div>
  <h1>خطّط لدراستك، وتابع مهامك، بذكاء</h1>
  <p class="lede">منصة إدارة الدراسة الذكية التي تساعدك على تنظيم جدولك اليومي، متابعة مهامك الأكاديمية، والحصول على ملخصات دراسية جاهزة. انضم إلى قائمة الانتظار للوصول المبكر.</p>

  <div class="features">
    <div class="feature"><span class="ic">🗓️</span><span>جدول يومي منظم</span></div>
    <div class="feature"><span class="ic">✅</span><span>تتبع المهام الدراسية</span></div>
    <div class="feature"><span class="ic">📝</span><span>ملخصات ومذكرات</span></div>
  </div>

  <div class="card">
    <h2>سجّل اهتمامك</h2>
    <p class="sub">كن من أوائل الطلاب الذين يجربون StudyHub ويستلمون الموارد الدراسية.</p>

    <form id="waitlist-form" novalidate>
      <div class="field">
        <label for="name">الاسم</label>
        <input type="text" id="name" name="name" placeholder="اسمك الكامل" required>
      </div>
      <div class="field">
        <label for="email">البريد الإلكتروني</label>
        <input type="email" id="email" name="email" placeholder="example@email.com" required>
      </div>
      <button type="submit" id="submit-btn">انضم لقائمة الانتظار</button>
      <div class="msg ok" id="msg-ok">✓ تم تسجيلك بنجاح! سنراسلك عند إطلاق StudyHub.</div>
      <div class="msg err" id="msg-err">حدث خطأ أثناء التسجيل. حاول مرة أخرى.</div>
    </form>
  </div>

  <footer>StudyHub — منصة تعليمية لإدارة الدراسة</footer>
</div>

<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2/dist/umd/supabase.js"></script>
<script>
  const SUPABASE_URL = 'https://meqdsnupysvqssqtjpoo.supabase.co';
  const SUPABASE_ANON_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im1lcWRzbnVweXN2cXNzcXRqcG9vIiwicm9sZSI6ImFub24iLCJpYXQiOjE3OTA0MDgyODgsImV4cCI6MjEwNTk4NDI4OH0.3H8hltV6D8i6Cv3iuMnsQWOLVYh8ekpTPacmTsPcCVA';

  const sb = supabase.createClient(SUPABASE_URL, SUPABASE_ANON_KEY);

  const form = document.getElementById('waitlist-form');
  const btn = document.getElementById('submit-btn');
  const okMsg = document.getElementById('msg-ok');
  const errMsg = document.getElementById('msg-err');

  form.addEventListener('submit', async (e) => {
    e.preventDefault();
    okMsg.style.display = 'none';
    errMsg.style.display = 'none';

    const name = document.getElementById('name').value.trim();
    const email = document.getElementById('email').value.trim();
    if(!name || !email){ return; }

    btn.disabled = true;
    btn.textContent = 'جاري التسجيل...';

    try{
      const { error } = await sb.from('user-list').insert([{ name, email }]);
      if(error) throw error;
      okMsg.style.display = 'block';
      form.reset();
    }catch(err){
      console.error(err);
      errMsg.textContent = err.message ? ('حدث خطأ: ' + err.message) : 'حدث خطأ أثناء التسجيل. حاول مرة أخرى.';
      errMsg.style.display = 'block';
    }finally{
      btn.disabled = false;
      btn.textContent = 'انضم لقائمة الانتظار';
    }
  });
</script>
</body>
</html>
