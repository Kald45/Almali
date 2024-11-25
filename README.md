<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>School Management System</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; }
    nav { background-color: #007BFF; padding: 10px; color: white; }
    nav ul { list-style: none; display: flex; gap: 20px; }
    nav ul li { cursor: pointer; }
    section { margin-top: 20px; }
    table { width: 100%; border-collapse: collapse; margin-top: 10px; }
    table, th, td { border: 1px solid black; text-align: left; padding: 8px; }
    button { margin-top: 10px; padding: 10px 20px; background-color: #007BFF; color: white; border: none; cursor: pointer; }
    button:hover { background-color: #0056b3; }
  </style>
</head>
<body>
  <nav>
    <ul>
      <li onclick="showSection('dashboard')">Dashboard</li>
      <li onclick="showSection('students')">Students</li>
      <li onclick="showSection('fees')">Fees</li>
      <li onclick="showSection('reports')">Reports</li>
    </ul>
  </nav>

  <section id="dashboard">
    <h2>Admin Dashboard</h2>
    <p>Welcome to the school management system</p>
  </section>

  <section id="students" style="display: none;">
    <h2>Students Management</h2>
    <button onclick="addStudent()">Add New Student</button>
    <table>
      <thead>
        <tr>
          <th>Student ID</th>
          <th>Name</th>
          <th>Class</th>
          <th>Attendance</th>
        </tr>
      </thead>
      <tbody id="studentsTable">
        <tr>
          <td>123</td>
          <td>John Doe</td>
          <td>10</td>
          <td>Present</td>
        </tr>
      </tbody>
    </table>
  </section>

  <section id="fees" style="display: none;">
    <h2>Fees Management</h2>
    <button onclick="generateFeesReport()">Generate Fees Report</button>
    <table>
      <thead>
        <tr>
          <th>Student ID</th>
          <th>Name</th>
          <th>Total Fees</th>
          <th>Paid</th>
          <th>Remaining</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>123</td>
          <td>John Doe</td>
          <td>$500</td>
          <td>$400</td>
          <td>$100</td>
        </tr>
      </tbody>
    </table>
  </section>

  <section id="reports" style="display: none;">
    <h2>Generate Reports</h2>
    <button onclick="exportReport('PDF')">Export as PDF</button>
    <button onclick="exportReport('Excel')">Export as Excel</button>
  </section>

  <script>
    function showSection(sectionId) {
      const sections = document.querySelectorAll('section');
      sections.forEach(section => {
        section.style.display = section.id === sectionId ? 'block' : 'none';
      });
    }

    function addStudent() {
      const table = document.getElementById('studentsTable');
      const row = document.createElement('tr');
      row.innerHTML = `
        <td>124</td>
        <td>Jane Smith</td>
        <td>11</td>
        <td>Present</td>
      `;
      table.appendChild(row);
    }

    function generateFeesReport() {
      alert('Fees report generated successfully!');
    }

    function exportReport(type) {
      alert(`Exporting report as ${type}`);
    }
  </script>
</body>
</html>
