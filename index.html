<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>استطلاعات</title>
<script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2/dist/umd/supabase.min.js"></script>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;900&display=swap" rel="stylesheet">
<style>
  * { font-family: 'Tajawal', sans-serif; }
  ::-webkit-scrollbar { width: 8px; }
  ::-webkit-scrollbar-thumb { background: #3f3f46; border-radius: 10px; }
  .fade-in { animation: fadeIn .35s ease both; }
  @keyframes fadeIn { from { opacity:0; transform: translateY(6px);} to {opacity:1; transform:none;} }
  .spinner { border-top-color: transparent; animation: spin 0.8s linear infinite; }
  @keyframes spin { to { transform: rotate(360deg);} }
  .bar-fill { transition: width .6s cubic-bezier(.4,0,.2,1); }
</style>
</head>
<body class="bg-[#0b0d12] min-h-screen text-zinc-100 pb-24">

<!-- شاشة التحميل الأولية -->
<div id="bootLoader" class="fixed inset-0 z-50 flex flex-col items-center justify-center bg-[#0b0d12] gap-4">
  <div class="w-8 h-8 rounded-full border-2 border-violet-500 spinner"></div>
  <p id="bootError" class="hidden text-red-400 text-sm text-center px-6 max-w-sm"></p>
</div>

<!-- الرأس -->
<header class="border-b border-zinc-800 sticky top-0 bg-[#0b0d12]/90 backdrop-blur z-20">
  <div class="max-w-2xl mx-auto px-4 py-4 flex items-center justify-between">
    <button id="homeBtn" class="flex items-center gap-2">
      <div class="w-8 h-8 rounded-lg bg-violet-500 flex items-center justify-center text-[#0b0d12] font-black text-sm">ص</div>
      <span class="font-black text-white">صوّت</span>
    </button>
    <button id="newPollBtn" class="bg-violet-500 hover:bg-violet-400 text-[#0b0d12] font-bold rounded-lg px-4 py-2 text-sm transition">
      + استطلاع جديد
    </button>
  </div>
</header>

<main class="max-w-2xl mx-auto px-4 py-6">

  <!-- ============ قائمة الاستطلاعات ============ -->
  <section id="listView">
    <div id="listLoading" class="flex justify-center py-16">
      <div class="w-6 h-6 rounded-full border-2 border-violet-500 border-t-transparent spinner"></div>
    </div>

    <div id="listEmpty" class="hidden flex-col items-center justify-center text-center py-20 text-zinc-600">
      <svg class="w-10 h-10 mb-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14"/>
      </svg>
      <p class="text-sm">لا توجد استطلاعات بعد.</p>
      <p class="text-xs mt-1 text-zinc-700">اضغط "استطلاع جديد" لإنشاء أول استطلاع.</p>
    </div>

    <div id="pollsList" class="space-y-3"></div>
  </section>

  <!-- ============ صفحة إنشاء استطلاع ============ -->
  <section id="createView" class="hidden fade-in">
    <button id="backFromCreate" class="text-sm text-zinc-500 hover:text-violet-400 mb-4 flex items-center gap-1">
      <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l-7 7 7 7M2 12h20"/></svg>
      رجوع
    </button>

    <h2 class="font-black text-white text-lg mb-4">إنشاء استطلاع جديد</h2>

    <form id="createForm" class="space-y-4">
      <div>
        <label class="text-xs text-zinc-500 mb-1 block">سؤال الاستطلاع</label>
        <input id="questionInput" type="text" required placeholder="مثال: ما هو أفضل يوم للاجتماع؟"
          class="w-full bg-[#14171d] border border-zinc-800 rounded-lg px-4 py-3 text-sm placeholder-zinc-600 focus:outline-none focus:border-violet-500 transition">
      </div>

      <div>
        <label class="text-xs text-zinc-500 mb-1 block">الخيارات (من 2 إلى 6)</label>
        <div id="optionsWrap" class="space-y-2">
          <input type="text" required placeholder="الخيار 1" class="optionInput w-full bg-[#14171d] border border-zinc-800 rounded-lg px-4 py-3 text-sm placeholder-zinc-600 focus:outline-none focus:border-violet-500 transition">
          <input type="text" required placeholder="الخيار 2" class="optionInput w-full bg-[#14171d] border border-zinc-800 rounded-lg px-4 py-3 text-sm placeholder-zinc-600 focus:outline-none focus:border-violet-500 transition">
        </div>
        <button type="button" id="addOptionBtn" class="mt-2 text-sm text-violet-400 hover:text-violet-300 flex items-center gap-1">
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4"/></svg>
          إضافة خيار
        </button>
      </div>

      <button id="createSubmit" type="submit"
        class="w-full bg-violet-500 hover:bg-violet-400 text-[#0b0d12] font-bold rounded-lg py-3 text-sm transition flex items-center justify-center gap-2">
        <span id="createSubmitText">إنشاء الاستطلاع</span>
        <div id="createSpinner" class="hidden w-4 h-4 rounded-full border-2 border-[#0b0d12] border-t-transparent spinner"></div>
      </button>
      <p id="createMsg" class="hidden text-sm text-center"></p>
    </form>
  </section>

  <!-- ============ صفحة التصويت / النتائج ============ -->
  <section id="pollView" class="hidden fade-in">
    <button id="backFromPoll" class="text-sm text-zinc-500 hover:text-violet-400 mb-4 flex items-center gap-1">
      <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l-7 7 7 7M2 12h20"/></svg>
      كل الاستطلاعات
    </button>

    <div id="pollLoading" class="flex justify-center py-16">
      <div class="w-6 h-6 rounded-full border-2 border-violet-500 border-t-transparent spinner"></div>
    </div>

    <div id="pollContent" class="hidden">
      <h2 id="pollQuestion" class="font-black text-white text-xl mb-1"></h2>
      <p id="pollMeta" class="text-xs text-zinc-500 mb-5"></p>

      <div id="pollOptions" class="space-y-3"></div>

      <div id="votedNote" class="hidden mt-5 text-xs text-zinc-500 text-center">✓ لقد صوّتت في هذا الاستطلاع</div>

      <div class="mt-6 flex items-center gap-2">
        <input id="shareLinkInput" readonly class="flex-1 bg-[#14171d] border border-zinc-800 rounded-lg px-3 py-2 text-xs text-zinc-400">
        <button id="copyLinkBtn" class="bg-zinc-800 hover:bg-zinc-700 text-xs font-bold rounded-lg px-3 py-2 transition">نسخ الرابط</button>
      </div>
    </div>
  </section>

</main>

<script>
// ==================== إعدادات Supabase ====================
const SUPABASE_URL = 'https://qocnnsxtvfgkdgffryax.supabase.co';
const SUPABASE_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InFvY25uc3h0dmZna2RnZmZyeWF4Iiwicm9sZSI6ImFub24iLCJpYXQiOjE3ODMzMTc0NTQsImV4cCI6MjA5ODg5MzQ1NH0.QZC_EM2eKjdYL-8daYDUSJwOXzlxAz51YLrilu9bf-8';

function showBootError(msg) {
  const loader = document.getElementById('bootLoader');
  const spinner = loader.querySelector('.spinner');
  const errEl = document.getElementById('bootError');
  if (spinner) spinner.classList.add('hidden');
  errEl.textContent = msg;
  errEl.classList.remove('hidden');
}

if (typeof supabase === 'undefined') {
  showBootError('تعذر تحميل مكتبة Supabase. تحقق من اتصال الإنترنت وأعد فتح الصفحة.');
  throw new Error('supabase-js failed to load');
}

let supabaseClient;
try {
  supabaseClient = supabase.createClient(SUPABASE_URL, SUPABASE_KEY);
} catch (e) {
  showBootError('خطأ في إعداد الاتصال بـ Supabase: ' + e.message);
  throw e;
}

// ==================== عناصر DOM ====================
const bootLoader   = document.getElementById('bootLoader');
const listView     = document.getElementById('listView');
const createView   = document.getElementById('createView');
const pollView     = document.getElementById('pollView');

const listLoading  = document.getElementById('listLoading');
const listEmpty    = document.getElementById('listEmpty');
const pollsList    = document.getElementById('pollsList');

const newPollBtn      = document.getElementById('newPollBtn');
const homeBtn          = document.getElementById('homeBtn');
const backFromCreate  = document.getElementById('backFromCreate');
const backFromPoll    = document.getElementById('backFromPoll');

const createForm      = document.getElementById('createForm');
const questionInput   = document.getElementById('questionInput');
const optionsWrap     = document.getElementById('optionsWrap');
const addOptionBtn    = document.getElementById('addOptionBtn');
const createSubmit    = document.getElementById('createSubmit');
const createSubmitText = document.getElementById('createSubmitText');
const createSpinner   = document.getElementById('createSpinner');
const createMsg       = document.getElementById('createMsg');

const pollLoading  = document.getElementById('pollLoading');
const pollContent  = document.getElementById('pollContent');
const pollQuestion = document.getElementById('pollQuestion');
const pollMeta     = document.getElementById('pollMeta');
const pollOptions  = document.getElementById('pollOptions');
const votedNote    = document.getElementById('votedNote');
const shareLinkInput = document.getElementById('shareLinkInput');
const copyLinkBtn  = document.getElementById('copyLinkBtn');

let currentPollId = null;

// ==================== تخزين محلي لمنع التصويت المكرر ====================
function getVotedPolls() {
  try { return JSON.parse(localStorage.getItem('voted_polls') || '{}'); }
  catch { return {}; }
}
function markVoted(pollId, optionId) {
  const v = getVotedPolls();
  v[pollId] = optionId;
  localStorage.setItem('voted_polls', JSON.stringify(v));
}

// ==================== التنقل بين الشاشات ====================
function showView(view) {
  [listView, createView, pollView].forEach(v => v.classList.add('hidden'));
  view.classList.remove('hidden');
}

function goHome() {
  currentPollId = null;
  history.replaceState(null, '', location.pathname);
  showView(listView);
  loadPolls();
}

homeBtn.addEventListener('click', goHome);
backFromPoll.addEventListener('click', goHome);

newPollBtn.addEventListener('click', () => {
  createForm.reset();
  optionsWrap.innerHTML = `
    <input type="text" required placeholder="الخيار 1" class="optionInput w-full bg-[#14171d] border border-zinc-800 rounded-lg px-4 py-3 text-sm placeholder-zinc-600 focus:outline-none focus:border-violet-500 transition">
    <input type="text" required placeholder="الخيار 2" class="optionInput w-full bg-[#14171d] border border-zinc-800 rounded-lg px-4 py-3 text-sm placeholder-zinc-600 focus:outline-none focus:border-violet-500 transition">
  `;
  createMsg.classList.add('hidden');
  showView(createView);
});

backFromCreate.addEventListener('click', () => showView(listView));

// ==================== إضافة خيار جديد في نموذج الإنشاء ====================
addOptionBtn.addEventListener('click', () => {
  const count = optionsWrap.querySelectorAll('.optionInput').length;
  if (count >= 6) return;
  const input = document.createElement('input');
  input.type = 'text';
  input.required = true;
  input.placeholder = `الخيار ${count + 1}`;
  input.className = 'optionInput w-full bg-[#14171d] border border-zinc-800 rounded-lg px-4 py-3 text-sm placeholder-zinc-600 focus:outline-none focus:border-violet-500 transition';
  optionsWrap.appendChild(input);
});

// ==================== إنشاء استطلاع جديد ====================
createForm.addEventListener('submit', async (e) => {
  e.preventDefault();
  const question = questionInput.value.trim();
  const options = Array.from(document.querySelectorAll('.optionInput'))
    .map(i => i.value.trim())
    .filter(Boolean);

  if (options.length < 2) {
    showCreateMsg('أدخل خيارين على الأقل.', true);
    return;
  }

  createSubmit.disabled = true;
  createSpinner.classList.remove('hidden');
  createMsg.classList.add('hidden');

  try {
    const { data: poll, error: pollError } = await supabaseClient
      .from('polls')
      .insert({ question })
      .select()
      .single();
    if (pollError) throw pollError;

    const optionRows = options.map(text => ({ poll_id: poll.id, option_text: text }));
    const { error: optError } = await supabaseClient.from('poll_options').insert(optionRows);
    if (optError) throw optError;

    openPoll(poll.id);
  } catch (err) {
    showCreateMsg('فشل الإنشاء: ' + err.message, true);
  } finally {
    createSubmit.disabled = false;
    createSpinner.classList.add('hidden');
  }
});

function showCreateMsg(text, isError) {
  createMsg.textContent = text;
  createMsg.className = 'text-sm text-center ' + (isError ? 'text-red-400' : 'text-emerald-400');
  createMsg.classList.remove('hidden');
}

// ==================== تحميل قائمة الاستطلاعات ====================
async function loadPolls() {
  listLoading.classList.remove('hidden');
  listEmpty.classList.add('hidden');
  pollsList.innerHTML = '';

  try {
    const { data: polls, error } = await supabaseClient
      .from('polls')
      .select('id, question, created_at, poll_options(votes)')
      .order('created_at', { ascending: false });
    if (error) throw error;

    if (!polls.length) {
      listEmpty.classList.remove('hidden');
      listEmpty.classList.add('flex');
      return;
    }

    polls.forEach((poll, i) => {
      const totalVotes = (poll.poll_options || []).reduce((s, o) => s + o.votes, 0);
      const card = document.createElement('button');
      card.className = 'fade-in w-full text-right bg-[#14171d] border border-zinc-800 hover:border-violet-500 rounded-xl p-4 transition';
      card.style.animationDelay = `${i * 30}ms`;
      card.innerHTML = `
        <p class="font-bold text-white mb-1">${escapeHtml(poll.question)}</p>
        <p class="text-xs text-zinc-500">${totalVotes} صوت</p>
      `;
      card.addEventListener('click', () => openPoll(poll.id));
      pollsList.appendChild(card);
    });
  } catch (err) {
    pollsList.innerHTML = `<p class="text-center text-sm text-red-400 py-8">تعذر تحميل الاستطلاعات: ${err.message}</p>`;
  } finally {
    listLoading.classList.add('hidden');
  }
}

// ==================== فتح استطلاع للتصويت ====================
async function openPoll(pollId) {
  currentPollId = pollId;
  history.replaceState(null, '', `?poll=${pollId}`);
  showView(pollView);
  pollLoading.classList.remove('hidden');
  pollContent.classList.add('hidden');

  await renderPoll(pollId);
  pollLoading.classList.add('hidden');
  pollContent.classList.remove('hidden');
}

async function renderPoll(pollId) {
  try {
    const { data: poll, error: pollError } = await supabaseClient
      .from('polls')
      .select('id, question, created_at')
      .eq('id', pollId)
      .single();
    if (pollError) throw pollError;

    const { data: options, error: optError } = await supabaseClient
      .from('poll_options')
      .select('id, option_text, votes')
      .eq('poll_id', pollId)
      .order('created_at', { ascending: true });
    if (optError) throw optError;

    const totalVotes = options.reduce((s, o) => s + o.votes, 0);
    const votedMap = getVotedPolls();
    const votedOptionId = votedMap[pollId];

    pollQuestion.textContent = poll.question;
    pollMeta.textContent = `${totalVotes} صوت إجمالاً`;
    shareLinkInput.value = location.href;

    pollOptions.innerHTML = '';
    options.forEach(opt => {
      const pct = totalVotes ? Math.round((opt.votes / totalVotes) * 100) : 0;
      const isChosen = votedOptionId === opt.id;

      const row = document.createElement('div');

      if (votedOptionId) {
        // عرض النتائج فقط
        row.className = 'relative rounded-lg overflow-hidden border ' + (isChosen ? 'border-violet-500' : 'border-zinc-800');
        row.innerHTML = `
          <div class="absolute inset-y-0 right-0 bg-violet-500/20 bar-fill" style="width:${pct}%"></div>
          <div class="relative flex items-center justify-between px-4 py-3">
            <span class="text-sm font-bold ${isChosen ? 'text-violet-300' : 'text-zinc-200'}">${escapeHtml(opt.option_text)} ${isChosen ? '✓' : ''}</span>
            <span class="text-xs text-zinc-400">${pct}% (${opt.votes})</span>
          </div>
        `;
      } else {
        // زر تصويت
        row.innerHTML = `
          <button class="voteBtn w-full text-right bg-[#14171d] hover:bg-[#1c202a] border border-zinc-800 hover:border-violet-500 rounded-lg px-4 py-3 text-sm font-bold text-zinc-200 transition">
            ${escapeHtml(opt.option_text)}
          </button>
        `;
        row.querySelector('.voteBtn').addEventListener('click', () => castVote(pollId, opt.id));
      }
      pollOptions.appendChild(row);
    });

    votedNote.classList.toggle('hidden', !votedOptionId);
  } catch (err) {
    pollOptions.innerHTML = `<p class="text-center text-sm text-red-400 py-8">تعذر تحميل الاستطلاع: ${err.message}</p>`;
  }
}

// ==================== التصويت ====================
async function castVote(pollId, optionId) {
  try {
    const { error } = await supabaseClient.rpc('increment_option_votes', { option_id: optionId });
    if (error) throw error;
    markVoted(pollId, optionId);
    await renderPoll(pollId);
  } catch (err) {
    alert('تعذر التصويت: ' + err.message);
  }
}

// ==================== نسخ رابط المشاركة ====================
copyLinkBtn.addEventListener('click', async () => {
  try {
    await navigator.clipboard.writeText(shareLinkInput.value);
    copyLinkBtn.textContent = 'تم النسخ ✓';
    setTimeout(() => copyLinkBtn.textContent = 'نسخ الرابط', 1500);
  } catch {
    shareLinkInput.select();
  }
});

// ==================== أداة أمان بسيطة ====================
function escapeHtml(str) {
  const div = document.createElement('div');
  div.textContent = str;
  return div.innerHTML;
}

// ==================== بدء التشغيل ====================
bootLoader.classList.add('hidden');

const params = new URLSearchParams(location.search);
const pollFromUrl = params.get('poll');
if (pollFromUrl) {
  openPoll(pollFromUrl);
} else {
  loadPolls();
}
</script>
</body>
</html>
