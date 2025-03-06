Proyecto Amigo Secreto
Este proyecto es una aplicación que permite realizar el sorteo de amigos secretos entre un grupo de participantes.Debes agragar el nombre de tus amigos para realizar el sorteo.
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amigo Secreto</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            background: #f4f4f4;
            margin: 5px;
            padding: 10px;
            border-radius: 5px;
        }
        button {
            margin-top: 10px;
            padding: 10px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Amigo Secreto</h1>
    <input type="text" id="nombre" placeholder="Ingrese un nombre">
    <button onclick="agregarNombre()">Adicionar</button>
    <ul id="lista"></ul>
    <button onclick="sortearAmigo()">Sortear Amigo</button>
    <h2 id="resultado"></h2>

    <script>
        let nombres = [];

        function agregarNombre() {
            let input = document.getElementById("nombre");
            let nombre = input.value.trim();
            if (nombre === "") {
                alert("Por favor, ingrese un nombre válido.");
                return;
            }
            nombres.push(nombre);
            input.value = "";
            actualizarLista();
        }

        function actualizarLista() {
            let lista = document.getElementById("lista");
            lista.innerHTML = "";
            nombres.forEach(nombre => {
                let li = document.createElement("li");
                li.textContent = nombre;
                lista.appendChild(li);
            });
        }

        function sortearAmigo() {
            if (nombres.length === 0) {
                alert("La lista está vacía. Agregue nombres antes de sortear.");
                return;
            }
            let indice = Math.floor(Math.random() * nombres.length);
            document.getElementById("resultado").textContent = "Amigo secreto: " + nombres[indice];
        }
    </script>
</body>
</html>
