<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Welcome to My Project</title>
  <style>
    body {
      font-family: "Segoe UI", sans-serif;
      margin: 0;
      padding: 2rem;
      background-color: #f9f9f9;
      color: #333;
    }

  </style>
</head>
<body>

  <h1>🚀 Welcome to My Project</h1>
  <p>A modern open-source tool for doing awesome things with ease.</p>

  <nav>
    <h2>📑 Table of Contents</h2>
    <ul>
      <li><a href="#overview">Overview</a></li>
      <li><a href="#table 1">Overview</a></li>
    </ul>
  </nav>

  <section id="overview">
    <h2>🔍 Overview</h2>
    <p>This project helps you do XYZ using modern web tools. It's lightweight, flexible, and easy to set up.</p>
  </section>

<section id="Table 1">
    <h2>🔍 Table</h2>
    <p> <!-- Grid.js JS -->
  <script src="https://unpkg.com/gridjs/dist/gridjs.umd.js"></script>

  <script>
    new gridjs.Grid({
      columns: ["Name", "Project", "Status"],
      data: [
        ["Alice", "Genome Analysis", "✅ Complete"],
        ["Bob", "ML Model", "🚧 In Progress"],
        ["Charlie", "Data Cleaning", "❌ Not Started"]
      ],
      search: true,
      sort: true,
      pagination: {
        limit: 5
      }
    }).render(document.getElementById("wrapper"));
  </script></p>
  </section>

  <footer>
    Made by Larissa Lauer, Michelle Chen, and Sebastian Kane
  </footer>

</body>
</html>

