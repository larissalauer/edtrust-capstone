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
      padding: 2rem;
    }
    h1 {
      margin-bottom: 1rem;
    }
  </style>
</head>
<body>

  <h1>📊 College Scorecard Data Snapshot</h1>
  <div id="table"></div>

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


