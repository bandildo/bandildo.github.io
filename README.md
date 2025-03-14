<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Visitor Counter</title>
</head>
<body>
  <h1>Visitor Counter</h1>
  <p id="counter">Loading...</p>

  <script>
    async function updateVisitorCount() {
      await fetch('https://tertulianus-proto.onrender.com/update-counter', {
        method: 'POST'
      });

      const response = await fetch('https://YOUR_RENDER_APP_URL/get-counter');
      const data = await response.json();
      document.getElementById('counter').textContent = data.count;
    }

    updateVisitorCount();
  </script>
</body>
</html>
