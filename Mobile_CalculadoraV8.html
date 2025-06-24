<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Árbol de Exactitud de Glucosa</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      background-color: #269FD9;
    }
    .node {
      position: absolute;
      width: 56px;
      height: 56px;
      border-radius: 9999px;
      background-color: white;
      border: 2px solid #003366;
      color: #003366;
      font-weight: bold;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 12px;
      text-align: center;
      padding: 4px;
    }
    .node.low {
      background-color: #ef4444;
      border-color: #991b1b;
      color: white;
    }
    .node.high {
      background-color: #fde047;
      border-color: #facc15;
      color: #78350f;
    }
    .label {
      position: absolute;
      font-size: 11px;
      color: #003366;
      background: rgba(255, 255, 255, 0.8);
      padding: 1px 3px;
      border-radius: 4px;
      white-space: nowrap;
    }
    .svg-line {
      stroke: #003366;
      stroke-width: 1.5;
    }
    @media (max-width: 640px) {
      .node {
        width: 48px;
        height: 48px;
        font-size: 10px;
      }
      .label {
        font-size: 10px;
      }
    }
  </style>
</head>
<body class="text-[#003366] px-4 py-6 font-sans">
  <h1 class="text-2xl sm:text-3xl font-bold text-center mb-4 sm:mb-6">Árbol de Exactitud de Glucosa</h1>

  <div class="max-w-md mx-auto mb-4 sm:mb-6">
    <label class="block mb-2 font-semibold text-base sm:text-lg">Introduce el valor de glucosa (mg/dL):</label>
    <input id="glucoseInput" type="number" placeholder="Ejemplo: 90"
           class="w-full p-2 border rounded-lg text-base sm:text-lg" />
    <button onclick="drawTree()"
            class="mt-4 w-full bg-[#4D205C] text-white py-2 rounded-lg hover:bg-[#003366]">
      Calcular y Dibujar Árbol
    </button>
  </div>

  <div id="treeCanvas" class="w-full h-[480px] sm:h-[500px] relative">
    <svg id="treeSVG" class="absolute w-full h-full"></svg>
    <div id="treeNodes" class="absolute w-full h-full"></div>
  </div>

  <footer class="mt-8 sm:mt-10 text-xs sm:text-sm text-center text-white">
    💡 Abre este archivo haciendo doble clic. Funciona 100% en el navegador.
  </footer>

  <script>
    function roundUp(n) {
      return Math.ceil(n);
    }

    function getNodeClass(value) {
      if (value < 70) return "node low";
      if (value > 180) return "node high";
      return "node";
    }

    function createNode(x, y, value, labelText = "") {
      const node = document.createElement("div");
      node.className = getNodeClass(value);
      node.style.left = `calc(${x}% - 28px)`;
      node.style.top = `calc(${y}% - 28px)`;
      node.textContent = value + ' mg/dL';
      document.getElementById("treeNodes").appendChild(node);

      if (labelText) {
        const label = document.createElement("div");
        label.className = "label";
        label.style.left = `calc(${x}% - 30px)`;
        label.style.top = `calc(${y}% - 48px)`;
        label.textContent = labelText;
        document.getElementById("treeNodes").appendChild(label);
      }
    }

    function createLine(x1, y1, x2, y2) {
      const svg = document.getElementById("treeSVG");
      const line = document.createElementNS("http://www.w3.org/2000/svg", "line");
      line.setAttribute("x1", `${x1}%`);
      line.setAttribute("y1", `${y1}%`);
      line.setAttribute("x2", `${x2}%`);
      line.setAttribute("y2", `${y2}%`);
      line.setAttribute("class", "svg-line");
      svg.appendChild(line);
    }

    function clearTree() {
      document.getElementById("treeNodes").innerHTML = "";
      document.getElementById("treeSVG").innerHTML = "";
    }

    function drawTree() {
      clearTree();
      const input = parseFloat(document.getElementById("glucoseInput").value);
      if (isNaN(input) || input <= 0) {
        alert("Introduce un valor válido.");
        return;
      }

      const fixedPercents = [0.053, 0.10, 0.15];
      const fixedDiffs = input < 100 ? [5.3, 10, 15] : fixedPercents.map(p => input * p);

      const levels = [
        [roundUp(input - fixedDiffs[0]), roundUp(input + fixedDiffs[0])],
        [roundUp(input - fixedDiffs[1]), roundUp(input + fixedDiffs[1])],
        [roundUp(input - fixedDiffs[2]), roundUp(input + fixedDiffs[2])]
      ];

      const labels = input < 100 ? ["5.3 mg/dL", "10 mg/dL", "15 mg/dL"] : ["5.3%", "10%", "15%"];

      const positions = {
        root: [20, 50],
        l1: [40, 35], r1: [40, 65],
        l2: [60, 25], r2: [60, 75],
        l3: [80, 15], r3: [80, 85]
      };

      createNode(...positions.root, input);
      createLine(...positions.root, ...positions.l1);
      createLine(...positions.root, ...positions.r1);
      createLine(...positions.l1, ...positions.l2);
      createLine(...positions.r1, ...positions.r2);
      createLine(...positions.l2, ...positions.l3);
      createLine(...positions.r2, ...positions.r3);

      createNode(...positions.l1, levels[0][0], `- ${labels[0]}`);
      createNode(...positions.r1, levels[0][1], `+ ${labels[0]}`);
      createNode(...positions.l2, levels[1][0], `- ${labels[1]}`);
      createNode(...positions.r2, levels[1][1], `+ ${labels[1]}`);
      createNode(...positions.l3, levels[2][0], `- ${labels[2]}`);
      createNode(...positions.r3, levels[2][1], `+ ${labels[2]}`);
    }

    document.getElementById("glucoseInput").addEventListener("keypress", function(e) {
      if (e.key === "Enter") drawTree();
    });
  </script>
</body>
</html>
