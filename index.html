<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Facturación Inteligente</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            color: #333;
        }
        header {
            background-color: #005f99;
            color: white;
            padding: 20px;
            text-align: center;
        }
        h1 {
            margin: 0;
        }
        main {
            padding: 20px;
            display: none;
        }
        form {
            margin: 20px 0;
        }
        textarea, input, button {
            margin: 5px 0;
            padding: 10px;
            width: 100%;
            max-width: 400px;
        }
        button {
            background-color: #ff6600;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #cc5200;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            font-size: 12px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 5px;
            text-align: center;
        }
        th {
            background-color: #005f99;
            color: white;
        }
        tbody tr:nth-child(odd) {
            background-color: #f9f9f9;
        }
        tbody tr:hover {
            background-color: #f1f1f1;
        }
        .delete-btn {
            background-color: red;
            color: white;
            border: none;
            padding: 5px;
            cursor: pointer;
        }
        .factura-count {
            font-weight: bold;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>Sistema de Facturación Inteligente</h1>
    </header>
    <div id="login-section">
        <h2>Acceso al Sistema</h2>
        <form id="login-form">
            <input type="password" id="password" placeholder="Contraseña" required>
            <button type="submit">Ingresar</button>
        </form>
        <p id="login-error" style="color: red; display: none;">Contraseña incorrecta</p>
    </div>
    <main>
        <section>
            <h2>Cargar Facturas</h2>
            <form id="upload-form">
                <input type="file" id="file-upload" accept=".xml">
                <button type="submit">Subir Factura XML</button>
            </form>
            <textarea id="text-input" rows="10" placeholder="Pega aquí las facturas en texto"></textarea>
            <button id="process-text">Procesar Texto</button>
            <div>
                <input type="text" id="search-bar" placeholder="Buscar por cliente, factura, etc.">
                <span class="factura-count" id="factura-count">Facturas leídas: 0</span>
            </div>
            <table>
                <thead>
                    <tr>
                        <th>Factura</th>
                        <th>Fecha</th>
                        <th>Cliente</th>
                        <th>RUC</th>
                        <th>Descripción</th>
                        <th>Monto</th>
                        <th>Eliminar</th>
                    </tr>
                </thead>
                <tbody id="invoice-table">
                    <!-- Datos serán añadidos dinámicamente -->
                </tbody>
            </table>
        </section>
    </main>
    <footer>
        <p>Sistema de Facturación Inteligente - 2024</p>
    </footer>
    <script>
        const PASSWORD = "mcm352";
        let invoices = JSON.parse(localStorage.getItem("invoices")) || [];

        document.getElementById("login-form").addEventListener("submit", (e) => {
            e.preventDefault();
            const password = document.getElementById("password").value;
            if (password === PASSWORD) {
                document.getElementById("login-section").style.display = "none";
                document.querySelector("main").style.display = "block";
                updateFacturaCount();
            } else {
                document.getElementById("login-error").style.display = "block";
            }
        });

        document.getElementById("process-text").addEventListener("click", () => {
            const text = document.getElementById("text-input").value.trim();
            if (!text) {
                alert("Por favor, pega el texto de las facturas.");
                return;
            }

            const rows = text.split(/\n/).map(line => line.trim()).filter(line => line);
            rows.forEach(row => {
                const columns = row.split(/\s+/); // Ajustar según la estructura exacta
                if (columns.length >= 5) {
                    invoices.push({
                        factura: columns[0],
                        fecha: columns[1],
                        cliente: columns[2],
                        ruc: columns[3],
                        descripcion: columns.slice(4, -1).join(" "), // Combina descripción si es texto largo
                        monto: columns[columns.length - 1]
                    });
                }
            });

            invoices.sort((a, b) => new Date(b.fecha) - new Date(a.fecha)); // Ordenar de más reciente a más antiguo
            localStorage.setItem("invoices", JSON.stringify(invoices));
            populateTable();
            updateFacturaCount();
        });

        document.getElementById("upload-form").addEventListener("submit", async (e) => {
            e.preventDefault();
            alert("Procesamiento de XML aún no implementado para texto masivo. Usa el campo de texto.");
        });

        function populateTable() {
            const tbody = document.getElementById("invoice-table");
            tbody.innerHTML = "";

            invoices.forEach((invoice, index) => {
                const row = document.createElement("tr");
                row.innerHTML = `
                    <td>${invoice.factura}</td>
                    <td>${invoice.fecha}</td>
                    <td>${invoice.cliente}</td>
                    <td>${invoice.ruc}</td>
                    <td>${invoice.descripcion}</td>
                    <td>${invoice.monto}</td>
                `;
                const deleteBtn = document.createElement("button");
                deleteBtn.textContent = "Eliminar";
                deleteBtn.classList.add("delete-btn");
                deleteBtn.addEventListener("click", () => {
                    invoices.splice(index, 1);
                    localStorage.setItem("invoices", JSON.stringify(invoices));
                    populateTable();
                    updateFacturaCount();
                });
                const deleteCell = document.createElement("td");
                deleteCell.appendChild(deleteBtn);
                row.appendChild(deleteCell);
                tbody.appendChild(row);
            });
        }

        function updateFacturaCount() {
            document.getElementById("factura-count").textContent = `Facturas leídas: ${invoices.length}`;
        }

        document.addEventListener("DOMContentLoaded", () => {
            populateTable();
            updateFacturaCount();
        });

        document.getElementById("search-bar").addEventListener("input", (e) => {
            const query = e.target.value.toLowerCase();
            const rows = document.querySelectorAll("#invoice-table tr");

            rows.forEach((row) => {
                const matches = Array.from(row.cells).some((cell) =>
                    cell.textContent.toLowerCase().includes(query)
                );
                row.style.display = matches ? "" : "none";
            });
        });
    </script>
</body>
</html>
