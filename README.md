<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Salawa Cafe</title>
<style>
:root{color-scheme:light;--bg:#faf6f0;--panel:#fff;--text:#2a211b;--muted:#7a6c60;--line:#e9dfd2;--brand:#a4521f;--brand-h:#8a4318;--brand-t:#fff;--soft:#f5e6d6;--ok:#2f7a3e;--warn:#b45309;--bad:#b42318;--shadow:0 6px 20px rgba(60,35,15,.1)}
@media(prefers-color-scheme:dark){:root:not([data-theme="light"]){color-scheme:dark;--bg:#17120e;--panel:#221b15;--text:#f3ebe2;--muted:#a99a8b;--line:#3a2f26;--brand:#d9803f;--brand-h:#e8964f;--brand-t:#1b120a;--soft:#3a2a1c;--ok:#6fcf86;--warn:#f2b458;--bad:#ff8f86;--shadow:0 6px 20px rgba(0,0,0,.5)}}
:root[data-theme="dark"]{color-scheme:dark;--bg:#17120e;--panel:#221b15;--text:#f3ebe2;--muted:#a99a8b;--line:#3a2f26;--brand:#d9803f;--brand-h:#e8964f;--brand-t:#1b120a;--soft:#3a2a1c;--ok:#6fcf86;--warn:#f2b458;--bad:#ff8f86;--shadow:0 6px 20px rgba(0,0,0,.5)}
:root{box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*,*::before,*::after{box-sizing:inherit}
body{margin:0;background:var(--bg);color:var(--text);font-family:system-ui,-apple-system,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;line-height:1.45}
button,input,select{font:inherit;color:inherit}
button{cursor:pointer;border:0;border-radius:10px;padding:9px 14px;background:var(--soft);color:var(--text)}
button.p{background:var(--brand);color:var(--brand-t);font-weight:600}
button.p:hover{background:var(--brand-h)}
button:disabled{opacity:.45;cursor:not-allowed}
input,select{background:var(--panel);border:1px solid var(--line);border-radius:10px;padding:8px 10px;width:100%}
header{display:flex;align-items:center;justify-content:space-between;gap:12px;padding:16px 20px;background:var(--panel);border-bottom:1px solid var(--line);position:sticky;top:0;z-index:5}
.logo{font-size:1.35rem;font-weight:700;color:var(--brand)}
.logo small{display:block;font-size:.75rem;font-weight:400;color:var(--muted)}
.hr{display:flex;gap:8px}
main{max-width:980px;margin:0 auto;padding:20px}
.tabs{display:flex;gap:8px;margin-bottom:18px;flex-wrap:wrap}
.tabs button{padding:9px 18px}
.tabs button.on{background:var(--brand);color:var(--brand-t);font-weight:600}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(210px,1fr));gap:14px}
.card{background:var(--panel);border:1px solid var(--line);border-radius:14px;padding:16px;display:flex;flex-direction:column;gap:6px}
.card h3{margin:0;font-size:1.05rem}
.price{font-weight:700;color:var(--brand)}
.rem{font-size:.85rem;color:var(--ok)}
.rem.low{color:var(--warn)}.rem.out{color:var(--bad)}
.card button{margin-top:auto}
.note{color:var(--muted);font-size:.9rem;margin:0 0 14px}
.drawer{position:fixed;top:0;right:0;bottom:0;width:min(380px,100%);background:var(--panel);box-shadow:var(--shadow);z-index:10;transform:translateX(100%);transition:transform .2s;display:flex;flex-direction:column;padding:18px;padding-top:calc(18px + env(safe-area-inset-top,0px));padding-bottom:calc(18px + env(safe-area-inset-bottom,0px));overflow-y:auto}
.drawer.open{transform:none}
.drawer h2{margin:0 0 12px;font-size:1.15rem;display:flex;justify-content:space-between;align-items:center}
.row{display:flex;justify-content:space-between;align-items:center;gap:8px;padding:10px 0;border-bottom:1px solid var(--line)}
.qty{display:flex;align-items:center;gap:6px}
.qty button{padding:2px 10px}
.total{display:flex;justify-content:space-between;font-weight:700;margin:14px 0}
.empty{text-align:center;color:var(--muted);padding:30px 0}
.empty button{margin-top:10px}
.ok{background:var(--soft);border-radius:12px;padding:14px;text-align:center}
.ok b{font-size:1.5rem;color:var(--brand);letter-spacing:.06em}
.msg{color:var(--bad);font-size:.9rem;min-height:1.2em}
.admin{background:var(--panel);border:1px solid var(--line);border-radius:14px;padding:16px;margin-bottom:20px}
.admin h2{margin:0 0 10px;font-size:1.1rem}
.admin table{width:100%;border-collapse:collapse;font-size:.9rem}
.admin th,.admin td{text-align:left;padding:6px 4px;border-bottom:1px solid var(--line)}
.admin td input{padding:5px 6px;width:80px}
.form{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:8px;margin:12px 0}
.scrim{position:fixed;inset:0;background:rgba(0,0,0,.4);z-index:9;display:none}
.scrim.on{display:block}
.modal{position:fixed;inset:0;background:rgba(0,0,0,.55);z-index:20;display:none;align-items:center;justify-content:center;padding:16px}.modal.on{display:flex}.box{background:var(--panel);border-radius:16px;padding:22px;max-width:360px;width:100%;box-shadow:var(--shadow);text-align:center}.lbl{display:block;font-size:.85rem;color:var(--muted);margin:10px 0 4px;text-align:left}.mp{color:var(--ok);font-weight:700;letter-spacing:.08em}
.pic{background:var(--soft);border-radius:10px;overflow:hidden;line-height:0}.pic svg{width:100%;height:auto;display:block}.pic.sm{width:56px;flex:none}
.up{display:inline-block;background:var(--soft);border-radius:10px;padding:9px 14px;cursor:pointer}
.hide{display:none}
.scroll{overflow-x:auto}
</style>
</head>
<body>
<header>
  <div class="logo">Salawa Cafe<small>Order ahead, skip the queue</small></div>
  <div class="hr">
    <button id="adminBtn">Admin</button>
    <button id="cartBtn" class="p">Cart (<span id="cnt">0</span>)</button>
  </div>
</header>
<main>
  <section id="adminBox" class="admin hide">
    <div id="pinStep">
      <h2>Admin portal</h2>
      <p class="note">Enter the admin PIN (demo PIN: 1234).</p>
      <div style="display:flex;gap:8px;max-width:260px"><input id="pin" type="password" inputmode="numeric" placeholder="PIN"><button class="p" id="pinGo">Unlock</button></div>
      <div class="msg" id="pinMsg"></div>
    </div>
    <div id="adminBody" class="hide">
      <h2>Stock &amp; prices</h2>
      <div class="scroll"><table><thead><tr><th>Dish</th><th>Meal</th><th>Price (Ksh)</th><th>Remaining</th><th></th></tr></thead><tbody id="atb"></tbody></table></div>
      <h2 style="margin-top:16px">Add a new dish</h2>
      <div class="form">
        <input id="nName" placeholder="Dish name">
        <select id="nType"><option value="Breakfast">Breakfast</option><option value="Lunch">Lunch</option><option value="Supper">Supper</option></select>
        <select id="nImg" title="Picture"><option value='plate'>Picture: plate</option><option value='tea'>Tea</option><option value='coffee'>Coffee</option><option value='bread14'>Bread 1/4</option><option value='bread14m'>Bread 1/4 margarine</option><option value='bread12'>Bread 1/2</option><option value='bread12m'>Bread 1/2 margarine</option><option value='sandwich'>Sandwich</option><option value='bun'>Bun</option><option value='mandazi'>Mandazi</option><option value='chapati'>Chapati</option><option value='rice'>Rice</option><option value='beans'>Beans stew</option><option value='chapmix'>Chapati mix</option><option value='ndengu'>Ndengu</option><option value='sukuma'>Sukuma</option><option value='beefstew'>Beef stew</option><option value='githeri'>Githeri</option><option value='beef'>Beef</option><option value='ugali'>Ugali</option><option value='sukbeef'>Sukuma beef</option></select>
        <input id="nPrice" type="number" min="0" placeholder="Price (Ksh)">
        <input id="nStock" type="number" min="0" placeholder="Stock">
        <button class="p" id="nAdd">Add dish</button>
      </div>
      <h2>Sales summary</h2>
      <p class="note" id="sales"></p>
      <div class="scroll"><table><thead><tr><th>Token</th><th>Customer</th><th>Items</th><th>Total (Ksh)</th></tr></thead><tbody id="otb"></tbody></table></div>
      <div style="margin-top:12px;display:flex;gap:8px"><button id="resetBtn">Reset demo data</button><button id="lockBtn">Lock admin</button></div>
    </div>
  </section>

  <div class="tabs" id="tabs"></div>
  <p class="note" id="status"></p>
  <div class="grid" id="grid"></div>
</main>

<div class="scrim" id="scrim"></div>
<div class="modal" id="modal"><div class="box" id="modalBox"></div></div>
<aside class="drawer" id="drawer" aria-label="Cart">
  <h2>Your cart <button id="closeCart">Close</button></h2>
  <div id="cartBody"></div>
</aside>

<script>
const KEY="salawa-cafe-v2";
const SEED=[
 {id:1,name:'Tea',type:'Breakfast',price:10,stock:40,img:'tea'},
 {id:2,name:'Coffee',type:'Breakfast',price:10,stock:40,img:'coffee'},
 {id:3,name:'1/4 bread plain',type:'Breakfast',price:25,stock:40,img:'bread14'},
 {id:4,name:'1/4 bread margarine',type:'Breakfast',price:30,stock:40,img:'bread14m'},
 {id:5,name:'1/2 bread plain',type:'Breakfast',price:35,stock:40,img:'bread12'},
 {id:6,name:'1/2 bread margarine',type:'Breakfast',price:40,stock:40,img:'bread12m'},
 {id:7,name:'Vegetable sandwich',type:'Breakfast',price:15,stock:40,img:'sandwich'},
 {id:8,name:'Bun',type:'Breakfast',price:10,stock:40,img:'bun'},
 {id:9,name:'Mandazi',type:'Breakfast',price:10,stock:40,img:'mandazi'},
 {id:10,name:'Chapati',type:'Breakfast',price:15,stock:40,img:'chapati'},
 {id:11,name:'Rice',type:'Lunch',price:25,stock:40,img:'rice'},
 {id:12,name:'Beans stew',type:'Lunch',price:20,stock:40,img:'beans'},
 {id:13,name:'Chapati mix',type:'Lunch',price:50,stock:40,img:'chapmix'},
 {id:14,name:'Chapati',type:'Lunch',price:15,stock:40,img:'chapati'},
 {id:15,name:'Ndengu',type:'Lunch',price:20,stock:40,img:'ndengu'},
 {id:16,name:'Sukuma',type:'Lunch',price:15,stock:40,img:'sukuma'},
 {id:17,name:'Beef stew',type:'Lunch',price:25,stock:40,img:'beefstew'},
 {id:18,name:'Githeri',type:'Lunch',price:25,stock:40,img:'githeri'},
 {id:19,name:'Beef',type:'Supper',price:40,stock:30,img:'beef'},
 {id:20,name:'Ugali',type:'Supper',price:20,stock:30,img:'ugali'},
 {id:21,name:'Sukuma beef',type:'Supper',price:25,stock:30,img:'sukbeef'},
 {id:22,name:'Chapati',type:'Supper',price:15,stock:30,img:'chapati'},
 {id:23,name:'Ndengu',type:'Supper',price:20,stock:30,img:'ndengu'},
 {id:24,name:'Chapati mix',type:'Supper',price:50,stock:30,img:'chapmix'}
];
const W=c=>`<svg viewBox='0 0 120 90' xmlns='http://www.w3.org/2000/svg' role='img' aria-hidden='true'>${c}</svg>`;
const E=(x,y,a,b,f,s)=>`<ellipse cx='${x}' cy='${y}' rx='${a}' ry='${b}' fill='${f}'${s?` stroke='${s}' stroke-width='2'`:''}/>`;
const DOTS=(n,cx,cy,rx,ry,f,r)=>{let o='';for(let i=0;i<n;i++){const a=i*2.399,d=Math.sqrt((i+.5)/n);o+=`<circle cx='${(cx+rx*d*Math.cos(a)).toFixed(1)}' cy='${(cy+ry*d*Math.sin(a)).toFixed(1)}' r='${r}' fill='${f}'/>`;}return o;};
const PL=i=>E(60,54,52,30,'#f1ede4','#d8d0c0')+E(60,52,40,22,'#fffdf8','#e8e1d4')+i;
const CUP=c=>E(58,72,40,9,'#d9d2c5')+`<path d='M28 36h60v14a30 22 0 0 1-60 0z' fill='#fff' stroke='#cfc7b8' stroke-width='2'/>`+E(58,36,30,7,c)+`<path d='M88 40h6a9 9 0 0 1 0 18h-8' fill='none' stroke='#cfc7b8' stroke-width='4'/><path d='M48 24q-5-7 0-13M60 24q-5-7 0-13M72 24q-5-7 0-13' fill='none' stroke='#b9b2a5' stroke-width='2.5' stroke-linecap='round'/>`;
const SL=x=>`<g transform='translate(${x},0)'><path d='M10 40q-4-20 20-20q8-6 16 0q24 0 20 20v28q0 6-6 6h-44q-6 0-6-6z' fill='#e9bf7a' stroke='#b9853d' stroke-width='3'/><path d='M16 42q0-12 14-12h24q12 0 12 12v26h-50z' fill='#f8e6bf'/></g>`;
const BR=(n,m)=>{const xs=n===1?[26]:[8,40];let o='';xs.forEach(x=>o+=SL(x));const f=xs[xs.length-1];if(m)o+=`<rect x='${f+26}' y='42' width='24' height='16' rx='5' fill='#ffd34d' stroke='#e0b21f' stroke-width='2'/><rect x='${f+30}' y='45' width='9' height='3' rx='1.5' fill='#fff2a8'/>`;return o+`<text x='60' y='87' text-anchor='middle' font-size='9' fill='#8a7a6a'>${n===1?'1/4':'1/2'} loaf</text>`;};
const LEAF=(a,c)=>`<g transform='rotate(${a} 60 50)'><ellipse cx='60' cy='40' rx='7' ry='14' fill='${c}'/></g>`;
const ART={
 tea:()=>W(CUP('#b8651b')),
 coffee:()=>W(CUP('#3b2314')),
 bread14:()=>W(BR(1,0)),
 bread14m:()=>W(BR(1,1)),
 bread12:()=>W(BR(2,0)),
 bread12m:()=>W(BR(2,1)),
 sandwich:()=>W(`<rect x='24' y='54' width='72' height='14' rx='6' fill='#e9bf7a' stroke='#b9853d' stroke-width='2'/><path d='M22 54q7-9 14 0t14 0t14 0t14 0t14 0v-3h-70z' fill='#5fae4b'/><circle cx='44' cy='48' r='7' fill='#e5483a'/><circle cx='76' cy='48' r='7' fill='#e5483a'/><rect x='24' y='30' width='72' height='16' rx='7' fill='#e9bf7a' stroke='#b9853d' stroke-width='2'/>`),
 bun:()=>W(E(60,56,40,26,'#b8742f')+E(60,50,38,24,'#d99a4a')+DOTS(12,60,42,22,9,'#f6e3b4',1.8)+`<path d='M34 44q10-16 30-14' fill='none' stroke='#f0c27a' stroke-width='3' stroke-linecap='round'/>`),
 mandazi:()=>W(`<polygon points='18,68 50,68 34,34' fill='#e0a43a' stroke='#b97a1b' stroke-width='3' stroke-linejoin='round'/><polygon points='62,70 98,70 80,36' fill='#e9b24a' stroke='#b97a1b' stroke-width='3' stroke-linejoin='round'/><polygon points='34,80 68,80 51,50' fill='#d99a30' stroke='#b97a1b' stroke-width='3' stroke-linejoin='round'/>`),
 chapati:()=>W(E(60,64,46,17,'#b97f33')+E(60,58,46,17,'#e7b565','#b8812f')+E(60,46,46,17,'#b97f33')+E(60,40,46,17,'#efc177','#b8812f')+DOTS(10,60,40,34,10,'#b8742a',2.4)),
 rice:()=>W(PL(E(60,50,28,15,'#fbfaf5','#e3dccb')+DOTS(26,60,48,24,10,'#d9d3bf',1.6))),
 beans:()=>W(PL(E(60,50,30,17,'#8e3f1d')+DOTS(14,60,50,24,11,'#b9652f',3.4)+E(48,42,8,3,'#c97a42'))),
 ndengu:()=>W(PL(E(60,50,30,17,'#5f6e2a')+DOTS(16,60,50,25,12,'#889a3d',3))),
 sukuma:()=>W(PL(LEAF(0,'#2e8b3d')+LEAF(60,'#3fa04d')+LEAF(120,'#2e8b3d')+LEAF(180,'#3fa04d')+LEAF(240,'#2e8b3d')+LEAF(300,'#3fa04d')+E(60,50,5,4,'#1f6b2c'))),
 beefstew:()=>W(PL(E(60,50,30,17,'#7d3a17')+DOTS(7,60,50,20,9,'#4e220d',5.5)+DOTS(5,60,50,22,10,'#e58a2b',2.6))),
 githeri:()=>W(PL(E(60,50,30,17,'#d8a43e')+DOTS(22,60,50,25,12,'#f4d35a',3)+DOTS(10,60,50,24,11,'#8e3f1d',2.8))),
 beef:()=>W(PL(DOTS(7,60,50,20,9,'#6b3418',7)+DOTS(5,58,48,18,8,'#8a4b25',4))),
 ugali:()=>W(PL(`<path d='M32 56q0-28 28-28t28 28q0 7-28 7t-28-7z' fill='#f7f3ea' stroke='#ded7c6' stroke-width='2'/>`+E(50,42,10,5,'#ffffff'))),
 sukbeef:()=>W(PL(E(60,50,30,17,'#2f8a3e')+DOTS(10,60,50,24,11,'#4cae58',4)+DOTS(6,60,50,20,9,'#6b3418',5.2))),
 chapmix:()=>W(PL(E(60,50,30,17,'#8a4320')+`<g fill='#e7b565' stroke='#b8812f' stroke-width='1.5'><rect x='38' y='42' width='22' height='9' rx='3' transform='rotate(-18 49 46)'/><rect x='58' y='38' width='22' height='9' rx='3' transform='rotate(15 69 42)'/><rect x='44' y='52' width='22' height='9' rx='3' transform='rotate(10 55 56)'/><rect x='64' y='51' width='20' height='9' rx='3' transform='rotate(-12 74 55)'/></g>`)),
 plate:()=>W(PL(E(60,50,22,12,'#cfc7b8')))
};
function pic(m){if(m.photo&&String(m.photo).startsWith("data:image/"))return `<img src="${m.photo}" alt="${esc(m.name)}" style="width:100%;aspect-ratio:4/3;object-fit:cover;display:block">`;return (ART[m.img]||ART.plate)();}
let S={menu:JSON.parse(JSON.stringify(SEED)),orders:[]};
try{const raw=localStorage.getItem(KEY);if(raw){const d=JSON.parse(raw);if(d&&Array.isArray(d.menu))S=d;}}catch(e){}
function save(){try{localStorage.setItem(KEY,JSON.stringify(S));}catch(e){}}
let cart={},tab="Breakfast",admin=false,placed=null,step="cart",buyer={};
const SLOTS=[{t:"Breakfast",s:5,e:11},{t:"Lunch",s:11,e:16},{t:"Supper",s:16,e:21}];
function nowHours(){const p=new Intl.DateTimeFormat("en-GB",{timeZone:"Africa/Nairobi",hour:"numeric",minute:"numeric",hour12:false}).formatToParts(new Date());const h=+p.find(x=>x.type==="hour").value%24,m=+p.find(x=>x.type==="minute").value;return h+m/60;}
function currentSlot(){const h=nowHours();return SLOTS.find(x=>h>=x.s&&h<x.e)||null;}
function fmt(h){return (h%12||12)+" "+(h>=12?"pm":"am");}
const $=id=>document.getElementById(id);
const esc=s=>String(s).replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));
const find=id=>S.menu.find(m=>m.id===id);

function renderTabs(){
  const sl=currentSlot();
  $("tabs").innerHTML=SLOTS.map(x=>`<button ${sl&&sl.t===x.t?'class="on"':"disabled"}>${x.t} &middot; ${fmt(x.s)} &ndash; ${fmt(x.e)}</button>`).join("");
  $("status").textContent=sl?"Now serving "+sl.t.toLowerCase()+". Remaining counts drop as soon as an order is placed. Times are East Africa Time.":"We are closed right now. Breakfast starts at "+fmt(5)+". Times are East Africa Time.";
}
function renderMenu(){
  const sl=currentSlot();
  if(!sl){$("grid").innerHTML='<p class="note">Salawa Cafe is closed right now. Breakfast is served from '+fmt(5)+'.</p>';return;}
  tab=sl.t;
  const items=S.menu.filter(m=>m.type===tab);
  $("grid").innerHTML=items.map(m=>{
    const cls=m.stock<=0?"out":m.stock<=5?"low":"";
    const txt=m.stock<=0?"Sold out":m.stock+" remaining";
    return `<div class="card"><div class="pic">${pic(m)}</div><h3>${esc(m.name)}</h3><div class="price">Ksh ${m.price}</div><div class="rem ${cls}">${txt}</div><button class="p" data-add="${m.id}" ${m.stock<=0?"disabled":""}>Add to cart</button></div>`;
  }).join("")||'<p class="note">No dishes in this meal yet.</p>';
}
function cartCount(){return Object.values(cart).reduce((a,b)=>a+b,0);}
function cartTotal(){return Object.entries(cart).reduce((a,[id,q])=>a+(find(+id)?find(+id).price*q:0),0);}
function renderCart(msg){
  $("cnt").textContent=cartCount();
  const el=$("cartBody");
  if(step==="details"&&!placed&&Object.keys(cart).length){
    el.innerHTML=`<p class="note">Order total: <b>Ksh ${cartTotal()}</b></p><label class="lbl">Your name</label><input id="bName" placeholder="e.g. Jane Wanjiru" value="${esc(buyer.name||"")}"><label class="lbl">M-Pesa phone number</label><input id="bPhone" inputmode="tel" placeholder="07XX XXX XXX" value="${esc(buyer.phone||"")}"><div class="msg">${msg||""}</div><button class="p" style="width:100%" id="payBtn">Pay with M-Pesa</button><button style="width:100%;margin-top:8px" id="backCart">Back to cart</button>`;
    return;
  }
  if(placed){
    el.innerHTML=`<div class="ok"><p>Order placed. Show this token at the counter:</p><b>${placed.token}</b><p>Total: Ksh ${placed.total}</p></div><button class="p" style="margin-top:14px;width:100%" id="newOrder">Order more</button>`;
    return;
  }
  const ids=Object.keys(cart);
  if(!ids.length){el.innerHTML='<div class="empty">Your cart is empty.<br><button class="p" id="browse">Browse the menu</button></div>';return;}
  el.innerHTML=ids.map(id=>{const m=find(+id);return `<div class="row"><div class="pic sm">${pic(m)}</div><div style="flex:1"><b>${esc(m.name)}</b><br><span class="note" style="margin:0">Ksh ${m.price} each</span></div><div class="qty"><button data-dec="${id}">&minus;</button><span>${cart[id]}</span><button data-inc="${id}">+</button></div></div>`;}).join("")
   +`<div class="total"><span>Total</span><span>Ksh ${cartTotal()}</span></div><div class="msg">${msg||""}</div><button class="p" style="width:100%" id="checkout">Checkout</button>`;
}
function openCart(o){$("drawer").classList.toggle("open",o);$("scrim").classList.toggle("on",o);if(o){step="cart";renderCart();}}

function renderAdmin(){
  $("atb").innerHTML=S.menu.map(m=>`<tr><td>${esc(m.name)}</td><td>${m.type}</td><td><input type="number" min="0" value="${m.price}" data-price="${m.id}"></td><td><input type="number" min="0" value="${m.stock}" data-stock="${m.id}"></td><td>${m.photo?'<span class="note" style="margin:0">photo set</span> ':''}<label class="up">Photo<input type="file" accept="image/*" data-photo="${m.id}" hidden></label> <button data-del="${m.id}">Remove</button></td></tr>`).join("");
  const sum=S.orders.reduce((a,o)=>a+o.total,0);
  $("sales").textContent=S.orders.length+" orders, Ksh "+sum+" in sales.";
  $("otb").innerHTML=S.orders.slice().reverse().map(o=>`<tr><td>${o.token}</td><td>${esc((o.name||"-")+" "+(o.phone||""))}</td><td>${esc(o.items)}</td><td>${o.total}</td></tr>`).join("")||'<tr><td colspan="4">No orders yet.</td></tr>';
}

document.addEventListener("click",e=>{
  const b=e.target.closest("button");if(!b)return;
  const d=b.dataset;
  if(d.t){tab=d.t;renderTabs();renderMenu();}
  else if(d.add){const m=find(+d.add);const sl=currentSlot();if(!sl||m.type!==sl.t){renderTabs();renderMenu();return;}const q=(cart[m.id]||0)+1;if(q<=m.stock){cart[m.id]=q;renderCart();openCart(true);}}
  else if(d.inc){const m=find(+d.inc);if(cart[d.inc]<m.stock){cart[d.inc]++;renderCart();}else renderCart("Only "+m.stock+" left of "+esc(m.name)+".");}
  else if(d.dec){cart[d.dec]--;if(cart[d.dec]<=0)delete cart[d.dec];renderCart();}
  else if(d.del){S.menu=S.menu.filter(m=>m.id!==+d.del);delete cart[d.del];save();renderAdmin();renderMenu();renderCart();}
  else if(b.id==="checkout")checkout();
  else if(b.id==="payBtn")startPay();
  else if(b.id==="backCart"){step="cart";renderCart();}
  else if(b.id==="stkSend")stkSend();
  else if(b.id==="stkCancel")closeStk();
  else if(b.id==="pickOk")closePick();
  else if(b.id==="newOrder"){placed=null;renderCart();}
  else if(b.id==="browse")openCart(false);
});
function checkout(){
  const sl=currentSlot();
  const gone=Object.keys(cart).filter(id=>!find(+id)||!sl||find(+id).type!==sl.t);
  if(gone.length){gone.forEach(id=>delete cart[id]);renderCart("Some items were removed because their meal time has ended.");return;}
  const ids=Object.keys(cart);
  for(const id of ids){const m=find(+id);if(!m||m.stock<cart[id]){renderCart("Sorry, "+(m?esc(m.name):"an item")+" no longer has enough stock. Adjust your cart.");return;}}
  step="details";renderCart();
}
function finalize(){
  const sl=currentSlot();
  const ids=Object.keys(cart);
  for(const id of ids){const m=find(+id);if(!m||!sl||m.type!==sl.t||m.stock<cart[id]){closeStk();step="cart";renderCart("Sorry, "+(m?esc(m.name):"an item")+" is no longer available in that quantity. Adjust your cart.");return;}}
  const total=cartTotal();
  const items=ids.map(id=>cart[id]+" x "+find(+id).name).join(", ");
  ids.forEach(id=>{find(+id).stock-=cart[id];});
  const token="SC-"+Math.random().toString(36).slice(2,6).toUpperCase();
  S.orders.push({token,name:buyer.name,phone:buyer.phone,items,total});
  placed={token,total,name:buyer.name};cart={};step="cart";save();
  renderMenu();renderCart();if(admin)renderAdmin();
  showPick();
}
function normPhone(p){let d=String(p).replace(/[\s-]/g,"");if(d.startsWith("+254"))d="0"+d.slice(4);else if(d.startsWith("254"))d="0"+d.slice(3);return /^0[17]\d{8}$/.test(d)?d:null;}
function startPay(){
  const name=$("bName").value.trim(),raw=$("bPhone").value.trim(),ph=normPhone(raw);
  buyer={name,phone:raw};
  if(!name){renderCart("Please enter your name.");return;}
  if(!ph){renderCart("Enter a valid Safaricom number, e.g. 0712 345 678.");return;}
  buyer.phone=ph;
  showStk();
}
function showStk(){
  $("modalBox").innerHTML=`<div class="mp">M-PESA</div><h3 style="margin:8px 0">Pay Ksh ${cartTotal()} to Salawa Cafe</h3><p class="note">A payment request was sent to ${esc(buyer.phone)}. Enter your M-Pesa PIN to confirm.</p><input id="stkPin" type="password" inputmode="numeric" maxlength="4" placeholder="M-Pesa PIN" style="text-align:center;letter-spacing:.4em"><div class="msg" id="stkMsg"></div><div style="display:flex;gap:8px;margin-top:8px"><button style="flex:1" id="stkCancel">Cancel</button><button class="p" style="flex:1" id="stkSend">Send</button></div><p class="note" style="margin-top:10px;font-size:.8rem">Demo only: no real payment is made and the PIN is never stored.</p>`;
  $("modal").classList.add("on");
}
function closeStk(){$("modal").classList.remove("on");}
function stkSend(){
  const v=$("stkPin").value;
  if(!/^\d{4}$/.test(v)){$("stkMsg").textContent="Enter your 4-digit PIN.";return;}
  $("modalBox").innerHTML='<div class="mp">M-PESA</div><p>Payment initiated&hellip; please wait.</p>';
  setTimeout(finalize,1600);
}
function showPick(){
  $("modalBox").innerHTML=`<div class="mp">Payment initiated</div><h3 style="margin:10px 0">You are directed to pick</h3><p class="note">Thank you, ${esc(placed.name)}. Show token <b>${placed.token}</b> at the counter to collect your order (Ksh ${placed.total}).</p><button class="p" style="width:100%" id="pickOk">OK</button>`;
  $("modal").classList.add("on");
}
function closePick(){closeStk();openCart(false);}
$("cartBtn").onclick=()=>openCart(true);
$("closeCart").onclick=()=>openCart(false);
$("scrim").onclick=()=>openCart(false);
$("adminBtn").onclick=()=>$("adminBox").classList.toggle("hide");
$("pinGo").onclick=()=>{
  if($("pin").value==="1234"){admin=true;$("pinStep").classList.add("hide");$("adminBody").classList.remove("hide");$("pin").value="";$("pinMsg").textContent="";renderAdmin();}
  else $("pinMsg").textContent="Wrong PIN.";
};
$("lockBtn").onclick=()=>{admin=false;$("adminBody").classList.add("hide");$("pinStep").classList.remove("hide");$("adminBox").classList.add("hide");};
$("resetBtn").onclick=()=>{S={menu:JSON.parse(JSON.stringify(SEED)),orders:[]};cart={};placed=null;save();renderAdmin();renderMenu();renderCart();};
$("nAdd").onclick=()=>{
  const name=$("nName").value.trim(),price=+$("nPrice").value,stock=+$("nStock").value;
  if(!name||!(price>=0)||!(stock>=0)||$("nPrice").value===""||$("nStock").value==="")return;
  S.menu.push({id:Date.now(),name,type:$("nType").value,price,stock,img:$("nImg").value});
  ["nName","nPrice","nStock"].forEach(i=>$(i).value="");
  save();renderAdmin();renderMenu();
};
function uploadPhoto(inp){
  const f=inp.files[0];if(!f)return;
  const src=find(+inp.dataset.photo);if(!src)return;
  const rd=new FileReader();
  rd.onload=()=>{const im=new Image();im.onload=()=>{
    const w=480,h=360,c=document.createElement("canvas");c.width=w;c.height=h;
    const x=c.getContext("2d");const r=Math.max(w/im.width,h/im.height);const dw=im.width*r,dh=im.height*r;
    x.drawImage(im,(w-dw)/2,(h-dh)/2,dw,dh);
    const url=c.toDataURL("image/jpeg",0.8);
    S.menu.forEach(m=>{if(m.name===src.name)m.photo=url;});
    save();renderAdmin();renderMenu();renderCart();
  };im.src=rd.result;};
  rd.readAsDataURL(f);
}
$("atb").addEventListener("change",e=>{
  const t=e.target;
  if(t.dataset.photo){uploadPhoto(t);return;}
  const v=Math.max(0,+t.value||0);
  if(t.dataset.price){find(+t.dataset.price).price=v;}
  else if(t.dataset.stock){const m=find(+t.dataset.stock);m.stock=v;if(cart[m.id]>v){v>0?cart[m.id]=v:delete cart[m.id];}}
  save();renderMenu();renderCart();
});
renderTabs();renderMenu();renderCart();
let lastSlot=(currentSlot()||{}).t;
setInterval(()=>{const c=(currentSlot()||{}).t;if(c===lastSlot)return;lastSlot=c;Object.keys(cart).forEach(id=>{const m=find(+id);if(!m||m.type!==c)delete cart[id];});renderTabs();renderMenu();renderCart();},30000);
</script>
</body>
</html>
