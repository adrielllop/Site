<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Consulta de Preços - Panificadora Pacheco</title>
  <style>
    body { font-family: Arial, sans-serif; background:#f5f5f5; margin:0; padding:20px; }
    .container { max-width:900px; margin:0 auto; }
    .card { background:#fff; padding:20px; border-radius:10px; box-shadow:0 2px 5px rgba(0,0,0,0.1); margin-bottom:20px; }
    input, select { padding:8px; border-radius:5px; border:1px solid #ccc; }
    button { padding:8px 12px; border:none; background:#2563eb; color:#fff; border-radius:5px; cursor:pointer; }
    button.red { background:#d11; }
    ul { list-style:none; padding:0; }
    li { border-bottom:1px solid #ddd; padding:10px 0; display:flex; justify-content:space-between; }
    .admin-box { margin-top:10px; }
  </style>
</head>
<body>
<div class="container">
  <h1>Panificadora Pacheco – Rio Verde (GO)</h1>
  <p>Consulta de preços</p>

  <div class="card">
    <input id="search" placeholder="Buscar produto..."> 
    <select id="category"></select>
    <select id="sort">
      <option value="nome">Ordenar por nome</option>
      <option value="preco">Ordenar por preço</option>
    </select>

    <div id="admin-login">
      <input type="password" id="admin-pass" placeholder="Senha admin">
      <button onclick="enterAdmin()">Entrar</button>
    </div>
  </div>

  <div class="card">
    <h3>Produtos</h3>
    <ul id="product-list"></ul>
  </div>

  <div id="admin-panel" class="card" style="display:none;">
    <h3>Painel Admin</h3>
    <form id="form-product">
      <input type="hidden" id="prod-id">
      <div><input id="prod-name" placeholder="Nome" style="width:100%; margin-top:5px;"></div>
      <div><input id="prod-cat" placeholder="Categoria" style="width:100%; margin-top:5px;"></div>
      <div><input id="prod-price" placeholder="Preço" style="width:100%; margin-top:5px;"></div>
      <div><input id="prod-unit" placeholder="Unidade" style="width:100%; margin-top:5px;"></div>
      <button style="margin-top:10px;" type="submit">Salvar</button>
    </form>
  </div>
</div>

<script>
const ADMIN_PASSWORD = "Pacheco0708";
const LS_KEY = "pacheco_products_v1";

function nowISO(){ return new Date().toISOString(); }

function sample(){ return [
  {id:"1", name:"Pão Francês (kg)", category:"Pães", price:18.5, unit:"kg", lastUpdated:nowISO()},
  {id:"2", name:"Pão de Forma", category:"Pães", price:7.0, unit:"un", lastUpdated:nowISO()},
  {id:"3", name:"Coxinha", category:"Salgados", price:3.5, unit:"un", lastUpdated:nowISO()}
];}

function load(){ let r=localStorage.getItem(LS_KEY); if(!r){localStorage.setItem(LS_KEY,JSON.stringify(sample()));return sample();} return JSON.parse(r); }
function save(p){ localStorage.setItem(LS_KEY, JSON.stringify(p)); }

let products = load();
let admin = false;

const listEl = document.getElementById('product-list');
const categoryEl = document.getElementById('category');

function refresh(){
  let q = document.getElementById('search').value.toLowerCase();
  let cat = categoryEl.value;
  let sort = document.getElementById('sort').value;

  let out = products.filter(p=>p.name.toLowerCase().includes(q));
  if(cat !== 'Todos') out = out.filter(p=>p.category===cat);
  if(sort==='preco') out.sort((a,b)=>a.price-b.price);
  if(sort==='nome') out.sort((a,b)=>a.name.localeCompare(b.name));

  listEl.innerHTML = '';
  out.forEach(p=>{
    let li = document.createElement('li');
    li.innerHTML = `<div><b>${p.name}</b><br><small>${p.category} — ${new Date(p.lastUpdated).toLocaleString()}</small></div>
                    <div><b>R$ ${p.price.toFixed(2)}</b> / ${p.unit}
                    ${admin ? `<br><button onclick="edit('${p.id}')">Editar</button> <button class='red' onclick="del('${p.id}')">Del</button>`:''}</div>`;
    listEl.appendChild(li);
  });
}

function loadCategories(){
  let cats = ['Todos', ...new Set(products.map(p=>p.category))];
  categoryEl.innerHTML = cats.map(c=>`<option>${c}</option>`).join('');
}

function enterAdmin(){
  let pass = document.getElementById('admin-pass').value;
  if(pass === ADMIN_PASSWORD){
    admin = true;
    document.getElementById('admin-panel').style.display = '';
    document.getElementById('admin-login').style.display = 'none';
    refresh();
  } else alert('Senha incorreta');
}

function edit(id){
  let p = products.find(x=>x.id===id);
  document.getElementById('prod-id').value = p.id;
  document.getElementById('prod-name').value = p.name;
  document.getElementById('prod-cat').value = p.category;
  document.getElementById('prod-price').value = p.price;
  document.getElementById('prod-unit').value = p.unit;
}

function del(id){
  if(confirm('Remover?')){
    products = products.filter(p=>p.id!==id);
    save(products);
    loadCategories();
    refresh();
  }
}

document.getElementById('form-product').onsubmit = function(e){
  e.preventDefault();
  let id = document.getElementById('prod-id').value || Math.random().toString(36).slice(2,9);
  let name = document.getElementById('prod-name').value;
  let category = document.getElementById('prod-cat').value;
  let price = parseFloat(document.getElementById('prod-price').value.replace(',','.'));
  let unit = document.getElementById('prod-unit').value;

  const p = { id, name, category, price, unit, lastUpdated: nowISO() };
  let exists = products.find(x=>x.id===id);
  if(exists) products = products.map(x=>x.id===id?p:x);
  else products.unshift(p);

  save(products);
  loadCategories();
  refresh();
  e.target.reset();
};

// Inicialização
loadCategories();
refresh();
</script>

</body>
</html>
