<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Nuestro Instagram Privado</title>
  <style>
    body { font-family: system-ui, sans-serif; padding: 20px; max-width: 800px; margin: auto; background:#fafafa; }
    h1 { text-align: center; }
    #top { display:flex; gap:10px; justify-content:center; margin-bottom:20px; flex-wrap:wrap; }
    button, input[type="file"] {
      padding: 8px 12px;
      border-radius: 8px;
      border: 1px solid #ddd;
      background:white;
      cursor:pointer;
    }
    button { background:#0095f6; color:white; border:none; }
    button:hover { background:#0077c8; }
    #gallery { display:flex; flex-wrap:wrap; gap:10px; justify-content:center; }
    .card { background:white; border:1px solid #ddd; border-radius:12px; padding:8px; }
    .card img { width:200px; height:200px; object-fit:cover; border-radius:10px; display:block; }
  </style>
</head>
<body>

<h1>Nuestro Instagram Privado</h1>

<div id="top">
  <input type="file" id="fileInput" accept="image/*">
  <button onclick="upload()">Subir foto</button>
</div>

<h2>Galería</h2>
<div id="gallery"></div>

<script>
const username = "TU_USUARIO";
const repo = "TU_REPO";
const branch = "main";

// Pide el token una vez y lo guarda en el navegador
let token = localStorage.getItem("github_token");
if (!token) {
  token = prompt("Introduce tu token de GitHub (PAT)");
  if (token) localStorage.setItem("github_token", token);
}

async function upload() {
  const file = document.getElementById("fileInput").files[0];
  if (!file) return alert("Selecciona una imagen");

  if (!token) return alert("No hay token configurado");

  const reader = new FileReader();
  reader.onloadend = async () => {
    const content = reader.result.split(",")[1];
    const filename = `images/${Date.now()}-${file.name}`;

    const res = await fetch(`https://api.github.com/repos/${username}/${repo}/contents/${filename}`, {
      method: "PUT",
      headers: {
        "Authorization": `token ${token}`,
        "Content-Type": "application/json"
      },
      body: JSON.stringify({
        message: "Nueva foto",
        content: content,
        branch: branch
      })
    });

    if (!res.ok) {
      console.error(await res.text());
      alert("Error subiendo la foto. Revisa el token o los permisos.");
      return;
    }

    loadGallery();
  };

  reader.readAsDataURL(file);
}

async function loadGallery() {
  try {
    const res = await fetch(`https://api.github.com/repos/${username}/${repo}/contents/images`);
    if (!res.ok) return; // si aún no existe la carpeta, no pasa nada
    const files = await res.json();

    const gallery = document.getElementById("gallery");
    gallery.innerHTML = "";

    files
      .filter(f => f.type === "file")
      .sort((a,b) => a.name.localeCompare(b.name))
      .reverse()
      .forEach(f => {
        const card = document.createElement("div");
        card.className = "card";
        const img = document.createElement("img");
        img.src = f.download_url;
        card.appendChild(img);
        gallery.appendChild(card);
      });
  } catch (e) {
    console.error(e);
  }
}

loadGallery();
</script>

</body>
</html>
