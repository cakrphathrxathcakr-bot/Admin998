<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>TaeBank Admin</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700&family=Sarabun:wght@400;500;600&family=Outfit:wght@400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.3.2/papaparse.min.js"></script>
    <style>
        body { background: #070B19; color: #F0F6FC; font-family: 'Sarabun'; user-select: none; }
        .font-num { font-family: 'Outfit'; } .font-eng { font-family: 'Cinzel'; }
        .page-view { display: none; min-height: 100dvh; width: 100%; } .page-view.active { display: flex; flex-direction: column; }
        .glass-panel { background: #121C33; border: 1px solid #1E2B4D; border-radius: 20px; box-shadow: 0 10px 25px rgba(0,0,0,0.3); }
        .input-luxe { background: #0B1121; border: 1px solid #1E2B4D; color: #FFF; border-radius: 12px; padding: 14px; width: 100%; outline: none; }
        .input-luxe:focus { border-color: #D4AF37; }
        .btn-gold { background: linear-gradient(135deg, #BF953F, #FCF6BA, #B38728); color: #000; border-radius: 12px; padding: 14px; font-weight: bold; width: 100%; cursor: pointer; }
        .member-card { background: #121C33; border: 1px solid #1E2B4D; border-radius: 16px; padding: 16px; margin-bottom: 12px; display: flex; justify-content: space-between; align-items: center; }
        .mini-btn { background: #0B1121; border: 1px solid #1E2B4D; border-radius: 8px; height: 36px; display: flex; align-items: center; justify-content: center; color: #8B9BB4; width: 100%; cursor: pointer; }
        .swal2-popup { border-radius: 20px !important; background: #121C33 !important; color: #FFF !important; border: 1px solid #1E2B4D !important; }
    </style>
</head>
<body>

    <div id="page-login" class="page-view active items-center justify-center p-6">
        <div class="glass-panel p-8 w-full max-w-sm text-center border-t-2 border-[#D4AF37]">
            <div class="w-20 h-20 mx-auto mb-6 bg-[#0B1121] rounded-full flex items-center justify-center border border-[#1E2B4D]"><i class="fas fa-shield-halved text-4xl text-[#D4AF37]"></i></div>
            <h2 class="text-2xl font-eng tracking-[4px]">ADMIN</h2>
            <div class="mt-8 flex flex-col gap-4">
                <input type="password" id="adminPin" placeholder="Enter PIN" class="input-luxe text-center text-xl font-num tracking-[10px]">
                <button id="btnLogin" class="btn-gold">AUTHORIZE</button>
            </div>
        </div>
    </div>

    <div id="page-main" class="page-view pb-10">
        <div class="w-full max-w-3xl mx-auto p-4 md:p-6 flex flex-col gap-5">
            <header class="flex justify-between items-center glass-panel p-4">
                <div class="flex items-center gap-3"><i class="fas fa-crown text-[#D4AF37] text-2xl ml-2"></i><div><h1 class="text-lg font-bold font-eng">TAEBANK</h1></div></div>
                <button onclick="location.reload()" class="w-10 h-10 rounded-full bg-[#0B1121] text-[#8B9BB4] border border-[#1E2B4D]"><i class="fas fa-power-off"></i></button>
            </header>

            <div class="grid grid-cols-2 gap-4">
                <div class="glass-panel p-5"><p class="text-[10px] text-[#D4AF37]">Total Assets</p><h3 id="stat-balance" class="text-2xl font-bold font-num mt-1">0.00</h3></div>
                <div class="glass-panel p-5"><p class="text-[10px] text-[#D4AF37]">Members</p><h3 id="stat-members" class="text-2xl font-bold font-num mt-1">0</h3></div>
            </div>

            <div class="grid grid-cols-2 gap-4">
                <button id="btnAdd" class="glass-panel p-4 flex gap-2 items-center justify-center text-blue-400"><i class="fas fa-plus-circle"></i> เพิ่มบัญชี</button>
                <label class="glass-panel p-4 flex gap-2 items-center justify-center text-green-400 cursor-pointer"><i class="fas fa-file-excel"></i> นำเข้า CSV<input type="file" id="btnImport" accept=".csv" class="hidden"></label>
            </div>

            <div class="glass-panel p-5 min-h-[400px]">
                <input type="text" id="searchInput" placeholder="ค้นหาบัญชี..." class="input-luxe text-sm mb-4">
                <div id="listContainer"></div>
            </div>
        </div>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.0.2/firebase-app.js";
        import { getDatabase, ref, push, set, update, onValue, remove } from "https://www.gstatic.com/firebasejs/11.0.2/firebase-database.js";

        const app = initializeApp({
            apiKey: "AIzaSyAiCtKW-U5QWp3yUsvToJlh2pT7sjiQ4Iw", authDomain: "taebankwat.firebaseapp.com",
            databaseURL: "https://taebankwat-default-rtdb.asia-southeast1.firebasedatabase.app", projectId: "taebankwat",
            storageBucket: "taebankwat.firebasestorage.app", messagingSenderId: "134684838871", appId: "1:134684838871:web:4b47416599ed4ce95c5992"
        });
        const db = getDatabase(app);
        
        let DB_STATE = { members: {}, transactions: {} };
        const pass = "2598";

        // Login Logic
        const loginFn = () => {
            if (document.getElementById('adminPin').value === pass) {
                document.getElementById('page-login').classList.remove('active');
                document.getElementById('page-main').classList.add('active');
                fetchDB();
            } else Swal.fire({ icon: 'error', title: 'รหัสผิด' });
        };
        document.getElementById('btnLogin').addEventListener('click', loginFn);
        document.getElementById('adminPin').addEventListener('keyup', (e) => { if(e.key === 'Enter') loginFn(); });

        function fetchDB() {
            onValue(ref(db, 'members'), s => { DB_STATE.members = s.val() || {}; renderUI(); });
            onValue(ref(db, 'transactions'), s => { DB_STATE.transactions = s.val() || {}; renderUI(); });
        }

        function renderUI() {
            const search = document.getElementById('searchInput').value.toLowerCase().trim();
            const list = document.getElementById('listContainer');
            let tBal = 0; let tMem = 0; list.innerHTML = '';

            Object.keys(DB_STATE.members).sort().forEach(key => {
                const m = DB_STATE.members[key];
                if (search && !key.includes(search) && !(m.nick||'').toLowerCase().includes(search) && !(m.name||'').toLowerCase().includes(search)) return;

                tMem++; let mBal = 0;
                Object.keys(DB_STATE.transactions).forEach(txId => {
                    const tx = DB_STATE.transactions[txId];
                    if (tx.studentCode === key) mBal += (tx.type === 'deposit' ? parseFloat(tx.amount) : -parseFloat(tx.amount));
                });
                tBal += mBal;

                const card = document.createElement('div'); card.className = 'member-card';
                card.innerHTML = `
                    <div class="flex-1 pr-2">
                        <span class="font-num text-[11px] text-[#D4AF37] px-2 py-0.5 rounded bg-[#D4AF37]/10">${key}</span>
                        <h4 class="font-bold text-base mt-1">${m.nick || '-'}</h4>
                        <p class="text-[11px] text-[#8B9BB4] truncate">${m.name || '-'}</p>
                        <div class="mt-2 text-[20px] font-num font-bold ${mBal >= 0 ? 'text-[#10B981]' : 'text-[#EF4444]'}">฿${mBal.toLocaleString()}</div>
                    </div>
                    <div class="flex flex-col gap-2 w-28">
                        <button class="bg-[#D4AF37]/10 text-[#D4AF37] py-2 rounded-lg font-bold text-xs btn-tx"><i class="fas fa-bolt"></i> รายการ</button>
                        <div class="flex gap-1">
                            <button class="mini-btn btn-hist"><i class="fas fa-history"></i></button>
                            <button class="mini-btn btn-edit text-blue-400"><i class="fas fa-pen"></i></button>
                            <button class="mini-btn btn-del text-red-400"><i class="fas fa-trash"></i></button>
                        </div>
                    </div>
                `;

                card.querySelector('.btn-tx').addEventListener('click', async () => {
                    const res = await Swal.fire({ title: `ทำรายการ: ${m.nick}`, showDenyButton: true, confirmButtonText: 'ฝากเข้า', confirmButtonColor: '#10B981', denyButtonText: 'ถอนออก', denyButtonColor: '#EF4444' });
                    if(res.isConfirmed || res.isDenied) {
                        const amt = await Swal.fire({ title: 'ระบุจำนวนเงิน', input: 'number' });
                        if(amt.value) await push(ref(db, 'transactions'), { studentCode: key, type: res.isConfirmed ? 'deposit':'withdraw', amount: parseFloat(amt.value), date: new Date().toISOString() });
                    }
                });

                card.querySelector('.btn-hist').addEventListener('click', () => {
                    let hHTML = `<div class="max-h-60 overflow-y-auto">`;
                    Object.keys(DB_STATE.transactions).filter(txId => DB_STATE.transactions[txId].studentCode === key).forEach(txId => {
                        const t = DB_STATE.transactions[txId]; const isDep = t.type==='deposit';
                        hHTML += `<div class="flex justify-between border-b border-[#1E2B4D] py-2 text-sm">
                            <span class="${isDep?'text-green-400':'text-red-400'}">${isDep?'ฝาก':'ถอน'} ${t.amount} ฿</span>
                            <button class="text-red-500" onclick="window.delTx('${txId}')"><i class="fas fa-times"></i> ลบ</button>
                        </div>`;
                    });
                    Swal.fire({ title: 'ประวัติ', html: hHTML + '</div>', showConfirmButton: false });
                });

                card.querySelector('.btn-edit').addEventListener('click', async () => {
                    const res = await Swal.fire({ html: `<input id="enick" class="input-luxe mb-2" value="${m.nick}"><input id="ename" class="input-luxe" value="${m.name}">`, preConfirm: () => [document.getElementById('enick').value, document.getElementById('ename').value] });
                    if(res.value) await update(ref(db, 'members/'+key), { nick: res.value[0], name: res.value[1] });
                });

                card.querySelector('.btn-del').addEventListener('click', async () => {
                    if((await Swal.fire({title:'ลบถาวร?', showCancelButton:true, confirmButtonColor:'#EF4444'})).isConfirmed) {
                        await remove(ref(db, 'members/'+key));
                        Object.keys(DB_STATE.transactions).forEach(async txId => { if(DB_STATE.transactions[txId].studentCode===key) await remove(ref(db, 'transactions/'+txId)); });
                    }
                });

                list.appendChild(card);
            });
            document.getElementById('stat-members').innerText = tMem;
            document.getElementById('stat-balance').innerText = tBal.toLocaleString();
        }

        window.delTx = async (txId) => { await remove(ref(db, 'transactions/'+txId)); Swal.close(); };
        document.getElementById('searchInput').addEventListener('input', renderUI);

        document.getElementById('btnAdd').addEventListener('click', async () => {
            const res = await Swal.fire({ html: `<input id="scode" class="input-luxe mb-2" placeholder="เลขบัญชี"><input id="snick" class="input-luxe mb-2" placeholder="ชื่อเล่น"><input id="sname" class="input-luxe" placeholder="ชื่อจริง">`, preConfirm: () => [document.getElementById('scode').value.replace(/[^a-zA-Z0-9]/g,''), document.getElementById('snick').value, document.getElementById('sname').value] });
            if(res.value && res.value[0]) await set(ref(db, 'members/'+res.value[0]), { nick: res.value[1], name: res.value[2] });
        });

        document.getElementById('btnImport').addEventListener('change', (e) => {
            Papa.parse(e.target.files[0], { header: true, complete: async (res) => {
                for(let r of res.data) {
                    const code = String(r.เลขที่บัญชี||'').replace(/\s/g,'').replace(/[^a-zA-Z0-9]/g,'');
                    if(!code) continue;
                    await set(ref(db, 'members/'+code), { nick: r['นมัสการ สามเณร..']||'', name: r.ชื่อจริง||'' });
                    const amt = parseFloat(String(r.ยอดคงเหลือ||'').replace(/,/g,''));
                    if(amt>0) await push(ref(db, 'transactions'), { studentCode: code, type: 'deposit', amount: amt, date: new Date().toISOString() });
                }
                Swal.fire('สำเร็จ'); e.target.value='';
            }});
        });
    </script>
</body>
</html>
