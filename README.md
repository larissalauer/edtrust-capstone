<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>College Scorecard Preview</title>
  <link href="https://unpkg.com/gridjs/dist/theme/mermaid.min.css" rel="stylesheet" />
  <script src="https://unpkg.com/gridjs/dist/gridjs.umd.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/papaparse@5.4.1/papaparse.min.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      display: flex;
    }
    /* Sidebar styles */
    .sidebar {
      width: 250px;
      background-color: #f4f4f4;
      padding: 1rem;
      border-right: 1px solid #ccc;
      height: 100vh;
      box-sizing: border-box;
      position: fixed;
      left: 0;
      top: 0;
      overflow-y: auto;
      transition: transform 0.3s ease;
    }
    .sidebar.hidden {
      transform: translateX(-100%);
    }
    .sidebar h2 {
      font-size: 1.2rem;
      margin-top: 0;
    }
    .sidebar ul {
      list-style: none;
      padding: 0;
    }
    .sidebar li {
      margin: 0.5rem 0;
    }
    .sidebar a {
      text-decoration: none;
      color: #007BFF;
    }
    .sidebar a:hover {
      text-decoration: underline;
    }
    /* Main content */
    .content {
      margin-left: 250px;
      padding: 2rem;
      width: 100%;
      transition: margin-left 0.3s ease;
    }
    .content.full {
      margin-left: 0;
    }
    /* Toggle button */
    .toggle-btn {
      position: fixed;
      top: 1rem;
      left: 1rem;
      background-color: #007BFF;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      cursor: pointer;
      z-index: 1000;
    }
    h1 {
      margin-bottom: 1rem;
    }
  </style>
</head>
<body>

<button class="toggle-btn" onclick="toggleSidebar()">☰ Menu</button>

  <div class="sidebar" id="sidebar">
    <h2>📑 Table of Contents</h2>
    <ul>
      <li><a href="#scorecard">College Scorecard Data Snapshot</a></li>
    </ul>
  </div>
  
<div class="content" id="content">
    <h1 id="scorecard">📊 College Scorecard Data Snapshot</h1>
    <div id="table"></div>
  </div>

  <script>
    function toggleSidebar() {
      const sidebar = document.getElementById("sidebar");
      const content = document.getElementById("content");
      sidebar.classList.toggle("hidden");
      content.classList.toggle("full");
    }

  <script>
    Papa.parse("pep_roi.csv", {
      download: true,
      header: true,
      complete: function(results) {
        const headers = results.meta.fields;
        const rows = results.data.map(row => headers.map(h => row[h]));

        new gridjs.Grid({
          columns: headers,
          data: rows,
          search: true,
          pagination: { limit: 10 },
          sort: true,
          fixedHeader: true,
          height: '500px'
        }).render(document.getElementById("table"));
      }
    });
  </script>

</body>
</html>


