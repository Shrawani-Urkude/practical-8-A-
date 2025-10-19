# practical-8-A-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>College Registration Form</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #eef2f3;
      padding: 20px;
    }
    h2 {
      color: #2c3e50;
      text-align: center;
    }
    form {
      background: white;
      width: 400px;
      margin: 0 auto;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }
    label {
      display: block;
      margin-top: 10px;
      font-weight: bold;
    }
    input, select, button {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      background-color: #0078D7;
      color: white;
      font-size: 16px;
      cursor: pointer;
      margin-top: 15px;
    }
    button:hover {
      background-color: #005fa3;
    }
    #output {
      background: white;
      width: 400px;
      margin: 20px auto;
      padding: 15px;
      border-radius: 8px;
      box-shadow: 0 0 8px rgba(0,0,0,0.2);
      white-space: pre-line;
    }
    .warning {
      color: red;
      font-size: 14px;
      margin-top: 5px;
    }
  </style>
</head>
<body>

  <h2>College Registration Form</h2>

  <form id="collegeForm">
    <label for="name">Full Name:</label>
    <input type="text" id="name" placeholder="Enter your full name">
    <div id="warnName" class="warning"></div>

    <label for="age">Age:</label>
    <input type="number" id="age" placeholder="Enter your age">
    <div id="warnAge" class="warning"></div>

    <label for="gender">Gender:</label>
    <select id="gender">
      <option value="">--Select Gender--</option>
      <option value="Female">Female</option>
      <option value="Male">Male</option>
      <option value="Other">Other</option>
    </select>
    <div id="warnGender" class="warning"></div>

    <label for="course">Course:</label>
    <select id="course">
      <option value="">--Select Course--</option>
      <option value="B.Tech">B.Tech</option>
      <option value="B.Sc">B.Sc</option>
      <option value="B.Com">B.Com</option>
      <option value="BA">BA</option>
      <option value="MCA">MCA</option>
    </select>
    <div id="warnCourse" class="warning"></div>

    <button type="button" onclick="registerStudent()">Submit</button>
  </form>

  <div id="output"></div>

  <script>
    function registerStudent() {
      // Clear previous warnings
      document.getElementById("warnName").innerText = "";
      document.getElementById("warnAge").innerText = "";
      document.getElementById("warnGender").innerText = "";
      document.getElementById("warnCourse").innerText = "";
      document.getElementById("output").innerText = "";

      // Get input values
      let name = document.getElementById("name").value.trim();
      let age = document.getElementById("age").value.trim();
      let gender = document.getElementById("gender").value;
      let course = document.getElementById("course").value;
      let valid = true;

      // Validation with warnings
      if (name === "") {
        document.getElementById("warnName").innerText = "⚠ Please enter your full name.";
        valid = false;
      }
      if (age === "" || age <= 0) {
        document.getElementById("warnAge").innerText = "⚠ Please enter a valid age.";
        valid = false;
      } else if (age < 18) {
        document.getElementById("warnAge").innerText = "⚠ You must be 18 or older to register for college.";
        valid = false;
      }
      if (gender === "") {
        document.getElementById("warnGender").innerText = "⚠ Please select your gender.";
        valid = false;
      }
      if (course === "") {
        document.getElementById("warnCourse").innerText = "⚠ Please select your course.";
        valid = false;
      }

      // Stop if validation fails
      if (!valid) return;

      let result = `🎓 College Registration Successful!\n\n`;
      result += `Name: ${name}\nAge: ${age}\nGender: ${gender}\nCourse: ${course}\n\n`;

      // Demonstrate For Loop
      result += "📘 For Loop (Counting 1 to 5):\n";
      for (let i = 1; i <= 5; i++) {
        result += "Count: " + i + "\n";
      }

      // Demonstrate While Loop
      result += "\n📗 While Loop (Printing course name letters):\n";
      let i = 0;
      while (i < course.length) {
        result += course.charAt(i) + "\n";
        i++;
      }

      document.getElementById("output").innerText = result;
    }
  </script>

</body>
</html>
