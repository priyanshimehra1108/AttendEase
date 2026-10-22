<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Attendease | Student Portal</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f1f5fb;
      color: #1b2d50;
    }
    header {
      background: #172b50;
      color: white;
      padding: 22px;
      text-align: center;
    }
    nav {
      background: white;
      padding: 14px;
      text-align: center;
      box-shadow: 0 2px 8px #0001;
    }
    nav a {
      color: #245ed7;
      margin: 8px;
      text-decoration: none;
      font-weight: bold;
    }
    main { max-width: 1000px; margin: 25px auto; padding: 15px; }
    .welcome, .card {
      background: white;
      border-radius: 14px;
      padding: 22px;
      margin-bottom: 18px;
      box-shadow: 0 3px 14px #0000000b;
    }
    .stats {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 14px;
    }
    .stat {
      background: #f8faff;
      border: 1px solid #e1e9f6;
      padding: 18px;
      border-radius: 10px;
    }
    .stat h2 { color: #2868e8; }
    input, textarea, button {
      display: block;
      width: 100%;
      padding: 12px;
      margin: 10px 0;
      border: 1px solid #d3ddec;
      border-radius: 7px;
      font: inherit;
    }
    button {
      background: #2868e8;
      color: white;
      border: 0;
      font-weight: bold;
      cursor: pointer;
    }
    footer { text-align: center; padding: 25px; color: #6b7890; }
  </style>
</head>
<body>
  <header>
    <h1>🎓 Attendease</h1>
    <p>Student Attendance and Query Management System</p>
  </header>

  <nav>
    <a href="#dashboard">Dashboard</a>
    <a href="#attendance">Attendance</a>
    <a href="#queries">Queries</a>
  </nav>

  <main>
    <section class="welcome" id="dashboard">
      <h2>Welcome to Attendease!</h2>
      <p>Manage attendance and communicate with your teachers.</p>
    </section>

    <section class="stats">
      <div class="stat">
        <p>Total Classes</p>
        <h2 id="total">12</h2>
      </div>
      <div class="stat">
        <p>Present</p>
        <h2 id="present">9</h2>
      </div>
      <div class="stat">
        <p>Absent</p>
        <h2 id="absent">3</h2>
      </div>
      <div class="stat">
        <p>Attendance</p>
        <h2 id="percent">75%</h2>
      </div>
    </section>

    <section class="card" id="attendance">
      <h2>My Attendance</h2>
      <p>Database Management System — Present</p>
      <p>Data Structures — Present</p>
      <p>Operating Systems — Absent</p>
      <p><small>Sample data for the PBL demonstration.</small></p>
    </section>

    <section class="card" id="queries">
      <h2>Submit a Query</h2>
      <form id="queryForm">
        <label for="subject">Subject</label>
        <input id="subject" required placeholder="Enter query subject">
        <label for="message">Message</label>
        <textarea id="message" required placeholder="Write your query"></textarea>
        <button type="submit">Submit Query</button>
      </form>
      <div id="result"></div>
    </section>
  </main>

  <footer>Attendease PBL | Built without AI</footer>

  <script>
    document.getElementById("queryForm").addEventListener("submit", function(e) {
      e.preventDefault();
      const subject = document.getElementById("subject").value;
      const message = document.getElementById("message").value;
      const item = document.createElement("div");
      const heading = document.createElement("h3");
      const body = document.createElement("p");
      heading.textContent = subject;
      body.textContent = message;
      item.append(heading, body);
      document.getElementById("result").prepend(item);
      this.reset();
      alert("Your query has been submitted!");
    });
  </script>
</body>
</html>
