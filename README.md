<html>
<head>
  <title>Editable School Timetable</title>
  <style>
    table, th, td {
      border: 2px solid black;
      border-collapse: collapse;
      padding: 10px;
      text-align: center;
    }
    th {
      background-color: #3c3c2c;
      color: white;
    }
    td, th {
      cursor: pointer;
    }
    #controls {
      display: none;
      margin: 10px 0;
    }
    select {
      margin-right: 10px;
    }
  </style>
</head>
<body><center>
<h3>Click this button to - <button onclick="toggleEdit()">Edit from here</button></h3>

<div id="controls">
  <label>Choose action: </label>
  <select id="actionSelect">
    <option value="period">Change Period</option>
    <option value="color">Change Color</option>
    <option value="teacher">Change Teacher</option>
  </select>

  <select id="periodSelect">
    <option value="CHEMISTRY">CHEMISTRY</option>
    <option value="PHYSICS">PHYSICS</option>
    <option value="COMPUTER">COMPUTER</option>
    <option value="ENGLISH">ENGLISH</option>
    <option value="URDU">URDU</option>
    <option value="ISLAMIYAT">ISLAMIYAT</option>
    <option value="FREE-PERIOD">FREE-PERIOD</option>
    <option value="TEST">TEST</option>
  </select>

  <input type="color" id="colorPicker">
  <input type="text" id="teacherInput" placeholder="Enter new teacher">
</div>
<h1>TIME TABLE</h1>
<h3>9TH B FGPS R A BAZAR RWP</h3>
<table>
  </tr>
    <th>TEACHERS NAME</th>
    <th>MONDAY</th>
    <th>TUESDAY</th>
    <th>WEDNESDAY</th>
    <th>THURSDAY</th>
    <th>FRIDAY</th>
  </tr>
  <tr id="teacherRow">
    <th onclick="editCell(this)">Sir Ahad Rana</th>
    <td onclick="editCell(this)">CHEMISTRY</td>
    <td onclick="editCell(this)">PHYSICS</td>
    <td onclick="editCell(this)">COMPUTER</td>
    <td onclick="editCell(this)">ENGLISH</td>
    <td onclick="editCell(this)">FREE-PERIOD</td>
  </tr>
  <tr id="teacherRow">
     <th onclick="editCell(this)">Sir Sajjad</th>
    <td onclick="editCell(this)">TEST</td>
    <td onclick="editCell(this)">COMPUTER</td>
    <td onclick="editCell(this)">URDU</td>
    <td onclick="editCell(this)">ISLAMIYAT</td>
    <td onclick="editCell(this)">FREE-PERIOD</td>
  </tr>
  <tr id="teacherRow">
    <th onclick="editCell(this)">Sir Jamshed</th>
    <td onclick="editCell(this)">COMPUTER</td>
    <td onclick="editCell(this)">ENGLISH</td>
    <td onclick="editCell(this)">CHEMISTRY</td>
    <td onclick="editCell(this)">PHYSICS</td>
    <td onclick="editCell(this)">ENGLISH</td>
  </tr>
  <tr id="teacherRow">
     <th onclick="editCell(this)">Sir Qaiser</th>
    <td onclick="editCell(this)">URDU</td>
    <td onclick="editCell(this)">FREE-PERIOD</td>
    <td onclick="editCell(this)">TEST</td>
    <td onclick="editCell(this)">COMPUTER</td>
    <td onclick="editCell(this)">ENGLISH</td>
  </tr>
  <tr id="teacherRow">
   <th onclick="editCell(this)">Sir zaffar</th>
    <td onclick="editCell(this)">TEST</td>
    <td onclick="editCell(this)">PHYSICS</td>
    <td onclick="editCell(this)">CHEMISTRY</td>
    <td onclick="editCell(this)">COMPUTER</td>
    <td onclick="editCell(this)">ENGLISH</td>
  </tr>
</table>

<h2>MADE BY RAHEEL AHMED</h2>
<p>THIS IS THE TIME TABLE OF FGPS R.A BAZAR SCHOOL SYSTEM</p>

<script>
  let editMode = false;

  function toggleEdit() {
    editMode = !editMode;
    document.getElementById("controls").style.display = editMode ? "block" : "none";
  }

  function editCell(cell) {
    if (!editMode) return;

    const action = document.getElementById("actionSelect").value;

    if (action === "period") {
      const newPeriod = document.getElementById("periodSelect").value;
      cell.innerText = newPeriod;
    } else if (action === "color") {
      const newColor = document.getElementById("colorPicker").value;
      cell.style.backgroundColor = newColor;
    } else if (action === "teacher" && cell.parentElement.id === "teacherRow") {
      const newTeacher = document.getElementById("teacherInput").value;
      if (newTeacher.trim() !== "") {
        cell.innerText = newTeacher;
      }
    }
  }
</script>

</center> </body>
</html>
