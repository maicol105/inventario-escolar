<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="utf-8"/>
<title>Login | Inventario Estudiantil</title>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      margin: 0;
      padding: 0;
    }

    .login-container {
      max-width: 400px;
      margin: 100px auto;
      background: white;
      padding: 30px;
      border-radius: 8px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      text-align: center;
    }

    .login-container h2 {
      margin-bottom: 20px;
      color: #020202
    }

    input {
      width: 100%;
      padding: 12px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }

    button {
      width: 100%;
      padding: 12px;
      background-color: #22292c;
      color: white;
      border: none;
      border-radius: 4px;
      font-size: 16px;
      cursor: pointer;
    }

    #inventario {
      display: none;
    }

    header {
      background-color: #5076bd;
      color: white;
      display: flex;
      align-items: center;
      padding: 10px 20px;
    }

    .header-image {
      width: 120px;
      height: 120px;
      object-fit: contain;
      margin-right: 60px;
      border-radius: 60px;
      padding: 5px;
    }

    .header-title {
      flex: 1;
      text-align: center;
      font-size: 28px;
      font-weight: bold;
    }

    .table-container {
      max-width: 1000px;
      margin: 30px auto;
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }

    table {
      width: 100%;
      border-collapse: collapse;
    }

    th, td {
      padding: 12px;
      text-align: left;
      border-bottom: 1px solid #ddd;
    }

    th {
      background-color: #5076bd;
      color: white;
    }

    .item-img {
      width: 80px;
      height: 60px;
      object-fit: contain;
      border-radius: 6px;
      box-shadow: 0 1px 4px rgba(0,0,0,0.2);
    }

    footer {
      text-align: center;
      padding: 10px;
      background: #5076bd;
      color: white;
      position: fixed;
      width: 100%;
      bottom: 0;
    }

    #logoutBtn {
      background-color: crimson;
      margin-top: 20px;
      width: auto;
      padding: 10px 20px;
    }
  </style>
</head>
<body>
<!-- Login -->
<div class="login-container" id="login">
<h2>Iniciar Sesión</h2>
<input id="usuario" placeholder="Usuario" required="" type="text"/>
<input id="clave" placeholder="Contraseña" required="" type="password"/>
<button onclick="validarLogin()">Entrar</button>
</div>
<!-- Inventario visible para ambos -->
<div id="inventario">
<header>
<img alt="Logo" class="header-image" src="imagen 4-Photoroom.png"/>
<div class="header-title">Inventario Estudiantil</div>
</header>
<div class="table-container">
<h2>Tabla de Inventario</h2>
<table>
<tr>
<th>ID</th>
<th>Imagen</th>
<th>Nombre del Artículo</th>
<th>Categoría</th>
<th>Cantidad</th>
<th>Estado</th>
</tr>
<tr>
<td>1</td>
<td><img alt="Computadora portátil" class="item-img" src="Desktop_computer_clipart_-_Yellow_theme.svg.png"/></td>
<td>Computadora portátil</td>
<td>Electrónica</td>
<td>15</td>
<td>Bueno</td>
</tr>
<tr>
<td>2</td>
<td><img alt="Proyector Epson" class="item-img" src="images.jpg"/></td>
<td>Proyector Epson</td>
<td>Electrónica</td>
<td>5</td>
<td>Regular</td>
</tr>
<tr>
<td>3</td>
<td><img alt="Libros de Matemáticas" class="item-img" src="download.jpg"/></td>
<td>Libros de Matemáticas</td>
<td>Biblioteca</td>
<td>40</td>
<td>Bueno</td>
</tr>
<tr>
<td>4</td>
<td><img alt="Sillas escolares" class="item-img" src="imagen 2.jpg"/></td>
<td>Sillas escolares</td>
<td>Mobiliario</td>
<td>100</td>
<td>Bueno</td>
</tr>
</table>
</div>
<div style="text-align:center;">
<button id="logoutBtn" onclick="cerrarSesion()">Salir</button>
</div>
<footer>
    © 2025 Inventario Escolar
  </footer>
</div>
<script>
  function validarLogin() {
    const usuario = document.getElementById('usuario').value.toLowerCase();
    const clave = document.getElementById('clave').value;

    if ((usuario === 'admin' && clave === '1234') || (usuario === 'profesor' && clave === 'abcd')) {
      document.getElementById('login').style.display = 'none';
      document.getElementById('inventario').style.display = 'block';

      // Mostrar solo el botón de salida para profesores
      if (usuario === 'profesor') {
        alert("Has iniciado sesión como Profesor (solo consulta).");
      } else {
        alert("Bienvenido, Administrador.");
      }
    } else {
      alert('Usuario o contraseña incorrectos');
    }
  }

  function cerrarSesion() {
    location.reload();
  }
</script>
</body>
</html>
