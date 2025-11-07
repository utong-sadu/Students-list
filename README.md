# Students-list
Web app
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Student Registration Form</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      padding: 20px;
      min-height: 100vh;
    }

    .container {
      max-width: 1100px;
      margin: 0 auto;
      background: white;
      border-radius: 10px;
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
      padding: 30px;
    }

    h1 {
      color: #333;
      margin-bottom: 10px;
      text-align: center;
    }

    .subtitle {
      text-align: center;
      color: #666;
      margin-bottom: 30px;
      font-size: 14px;
    }

    .form-section {
      margin-bottom: 25px;
      padding-bottom: 20px;
      border-bottom: 2px solid #eee;
    }

    .form-section:last-of-type {
      border-bottom: none;
    }

    .section-title {
      font-size: 16px;
      font-weight: bold;
      color: #667eea;
      margin-bottom: 15px;
      text-transform: uppercase;
    }

    .form-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 15px;
    }

    .form-grid.full {
      grid-template-columns: 1fr;
    }

    .form-group {
      display: flex;
      flex-direction: column;
    }

    label {
      font-weight: 600;
      margin-bottom: 6px;
      color: #333;
      font-size: 13px;
    }

    input,
    select,
    textarea {
      padding: 10px;
      border: 2px solid #ddd;
      border-radius: 5px;
      font-size: 13px;
      font-family: inherit;
      transition: border-color 0.3s;
    }

    input:focus,
    select:focus,
    textarea:focus {
      outline: none;
      border-color: #667eea;
      background-color: #f8f9ff;
    }

    input:disabled {
      background-color: #f5f5f5;
      color: #666;
      cursor: not-allowed;
    }

    textarea {
      resize: vertical;
      min-height: 80px;
    }

    .button-group {
      display: flex;
      gap: 10px;
      justify-content: center;
      margin-top: 30px;
      flex-wrap: wrap;
    }

    button {
      padding: 12px 30px;
      font-size: 14px;
      font-weight: bold;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s;
    }

    .btn-submit {
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
      flex: 1;
      min-width: 150px;
    }

    .btn-submit:hover {
      transform: translateY(-2px);
      box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
    }

    .btn-submit:disabled {
      opacity: 0.6;
      cursor: not-allowed;
    }

    .btn-reset {
      background: #f0f0f0;
      color: #333;
      flex: 1;
      min-width: 150px;
    }

    .btn-reset:hover {
      background: #e0e0e0;
    }

    .status {
      margin-top: 20px;
      padding: 15px;
      border-radius: 5px;
      text-align: center;
      display: none;
    }

    .status.success {
      background: #d4edda;
      color: #155724;
      border: 1px solid #c3e6cb;
      display: block;
    }

    .status.error {
      background: #f8d7da;
      color: #721c24;
      border: 1px solid #f5c6cb;
      display: block;
    }

    .sheet-section {
      margin-top: 40px;
      border-top: 3px solid #667eea;
      padding-top: 30px;
    }

    .sheet-title {
      font-size: 18px;
      font-weight: bold;
      color: #333;
      margin-bottom: 15px;
    }

    .sheet-container {
      overflow-x: auto;
      border: 2px solid #ddd;
      border-radius: 5px;
      max-height: 400px;
      overflow-y: auto;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      background: white;
    }

    th {
      background: #667eea;
      color: white;
      padding: 12px;
      text-align: left;
      font-weight: 600;
      font-size: 12px;
      position: sticky;
      top: 0;
    }

    td {
      padding: 10px 12px;
      border-bottom: 1px solid #eee;
      font-size: 12px;
    }

    tr:hover {
      background: #f9f9f9;
    }

    tr:last-child td {
      border-bottom: none;
    }

    .loading {
      text-align: center;
      padding: 20px;
      color: #667eea;
    }

    .no-data {
      text-align: center;
      padding: 20px;
      color: #999;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>📋 ការចុះឈ្មោះសិស្ស / Student Registration</h1>
    <h1>	សាលាបឋមសិក្សា រោគ	</h1>
    <p class="subtitle">Student Information Form</p>

    <form id="studentForm">
      <!-- Personal Information -->
      <div class="form-section">
        <div class="section-title">👤 Personal Information</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Entry Number (ល.រ) - Auto</label>
            <input type="number" id="etc" name="etc" disabled>
          </div>
          <div class="form-group">
            <label>First Name *</label>
            <input type="text" id="firstName" name="firstName" required>
          </div>
          <div class="form-group">
            <label>Last Name *</label>
            <input type="text" id="lastName" name="lastName" required>
          </div>
          <div class="form-group">
            <label>Gender *</label>
            <select id="gender" name="gender" required>
              <option value="">Select...</option>
              <option value="ស្រី">ស្រី (Female)</option>
              <option value="ប្រុស">ប្រុស (Male)</option>
            </select>
          </div>
          <div class="form-group">
            <label>Date of Birth *</label>
            <input type="date" id="dob" name="dob" required>
          </div>
          <div class="form-group">
            <label>Age - Auto</label>
            <input type="number" id="age" name="age" disabled>
          </div>
          <div class="form-group full">
            <label>Birth Certificate Number *</label>
            <input type="text" id="birthCert" name="birthCert" required>
          </div>
        </div>
      </div>

      <!-- Academic Information -->
      <div class="form-section">
        <div class="section-title">📚 Academic Information</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Grade *</label>
            <select id="Grade" name="Grade" required>
            	<option value="">Select...</option>
           		  <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
                <option value="5">5</option>
                <option value="6">6</option>
                <option value="មត្តេយ្យ">មត្តេយ្យ</option>
             <select>
        	</div>
          <div class="form-group">
            <label>Level *</label>
            <select id="level" name="level" required>
              <option value="">Select...</option>
              <option value="A">A</option>
              <option value="B">B</option>
              <option value="C">C</option>
              <option value="កម្រិតខ្ពស់">កម្រិតខ្ពស់</option>
              <option value="កម្រិតមធ្យម">កម្រិតមធ្យម</option>
              <option value="កម្រិតទាប">កម្រិតទាប</option>
            </select>
          </div>
          <div class="form-group">
            <label>Class Teacher Name *</label>
            <input type="text" id="teacher" name="teacher" required>
          </div>
          <div class="form-group">
            <label>Date of Registration *</label>
            <input type="date" id="regDate" name="regDate" required>
          </div>
        </div>
      </div>

      <!-- Family Information -->
      <div class="form-section">
        <div class="section-title">👨‍👩‍👧 Family Information</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Father's Name</label>
            <input type="text" id="fatherName" name="fatherName">
          </div>
          <div class="form-group">
            <label>Father's Occupation</label>
            <input type="text" id="fatherOcc" name="fatherOcc">
          </div>
          <div class="form-group">
            <label>Mother's Name</label>
            <input type="text" id="motherName" name="motherName">
          </div>
          <div class="form-group">
            <label>Mother's Occupation</label>
            <input type="text" id="motherOcc" name="motherOcc">
          </div>
        </div>
      </div>

      <!-- Status Information -->
      <div class="form-section">
        <div class="section-title">✅ Status Information</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Disability</label>
            <select id="disability" name="disability">
              <option value="No">No</option>
              <option value="Yes">Yes</option>
            </select>
          </div>
          <div class="form-group">
            <label>Vulnerable Children</label>
            <select id="vulnerable" name="vulnerable">
              <option value="No">No</option>
              <option value="Yes">Yes</option>
            </select>
          </div>
          <div class="form-group">
            <label>Foster Children</label>
            <select id="foster" name="foster">
              <option value="No">No</option>
              <option value="Yes">Yes</option>
            </select>
          </div>
          <div class="form-group">
            <label>Poor</label>
            <select id="Poor" name="Poor">
            	<option value="">Select...</option>
            	<option value="ក្រ​១">ក្រ​១</option>
                <option value="ក្រ​២">ក្រ​២</option>
                <option value="បណ្ណហានីភ័យ">បណ្ណហានីភ័យ</option>
                <option value="ផ្សេងៗ">ផ្សេងៗ</option>
            </select>
          </div>
          <div class="form-group full">
            <label>Poverty Card Number</label>
            <input type="text" id="povertyCard" name="povertyCard">
          </div>
        </div>
      </div>

      <!-- Location Information -->
      <div class="form-section">
        <div class="section-title">📍 Location Information</div>
        <div class="form-grid">
          <div class="form-group">
            <label>Province *</label>
             <select id="Province" name="Province" required>
            	<option value="">Select...</option>
            	<option Value="បន្ទាយមានជ័យ">បន្ទាយមានជ័យ</option>
                <option Value="បា់ត់ដំបង">បា់ត់ដំបង</option>
                <option Value="សៀមរាប">សៀមរាប</option>
                <option Value="ឧត្តរមានជ័យ">ឧត្តរមានជ័យ</option>
                <option Value="ពោធិសាត់">ពោធិសាត់</option>
                <option Value="ប៉ៃលិន">ប៉ៃលិន</option>
         	</select>
          </div>
          <div class="form-group">
            <label>District *</label>
            <input type="text" id="district" name="district" required>
          </div>
          <div class="form-group">
            <label>Commune *</label>
            <input type="text" id="commune" name="commune" required>
          </div>
          <div class="form-group">
            <label>Village *</label>
            <input type="text" id="village" name="village" required>
          </div>
        </div>
      </div>

      <!-- Buttons -->
      <div class="button-group">
        <button type="submit" class="btn-submit">💾 Save Data</button>
        <button type="reset" class="btn-reset">Clear Form</button>
      </div>

      <div id="status" class="status"></div>
    </form>

    <!-- Sheet Display Section -->
    <div class="sheet-section">
      <div class="sheet-title">📊 Student Records</div>
      <div class="sheet-container">
        <div id="sheetContent" class="loading">Loading data...</div>
      </div>
    </div>
  </div>

  <script>
    // Initialize
    let studentData = [];

    // Load data from localStorage
    function loadData() {
      const stored = localStorage.getItem('studentDatabase');
      if (stored) {
        studentData = JSON.parse(stored);
      }
      updateEntryNumber();
      renderTable();
    }

    // Save data to localStorage
    function saveData() {
      localStorage.setItem('studentDatabase', JSON.stringify(studentData));
    }

    // Update entry number
    function updateEntryNumber() {
      const nextEtc = studentData.length + 1;
      document.getElementById('etc').value = nextEtc;
    }

    // Auto-calculate age from DOB
    document.getElementById('dob').addEventListener('change', function () {
      const dob = new Date(this.value);
      const today = new Date();
      let age = today.getFullYear() - dob.getFullYear();
      const month = today.getMonth() - dob.getMonth();
      if (month < 0 || (month === 0 && today.getDate() < dob.getDate())) {
        age--;
      }
      document.getElementById('age').value = age >= 0 ? age : '';
    });

    // Set today's date as default
    document.getElementById('regDate').valueAsDate = new Date();

    // Form submission
    document.getElementById('studentForm').addEventListener('submit', function (e) {
      e.preventDefault();
      const statusDiv = document.getElementById('status');
      const submitBtn = document.querySelector('.btn-submit');

      // Collect form data
      const formData = {
        etc: document.getElementById('etc').value,
        lastName: document.getElementById('lastName').value,
        firstName: document.getElementById('firstName').value,
        gender: document.getElementById('gender').value,
        dob: document.getElementById('dob').value,
        age: document.getElementById('age').value,
        birthCert: document.getElementById('birthCert').value,
        regDate: document.getElementById('regDate').value,
        grade: document.getElementById('grade').value,
        level: document.getElementById('level').value,
        disability: document.getElementById('disability').value,
        poor: document.getElementById('poor').value,
        povertyCard: document.getElementById('povertyCard').value,
        vulnerable: document.getElementById('vulnerable').value,
        foster: document.getElementById('foster').value,
        province: document.getElementById('province').value,
        district: document.getElementById('district').value,
        commune: document.getElementById('commune').value,
        village: document.getElementById('village').value,
        fatherName: document.getElementById('fatherName').value,
        fatherOcc: document.getElementById('fatherOcc').value,
        motherName: document.getElementById('motherName').value,
        motherOcc: document.getElementById('motherOcc').value,
        teacher: document.getElementById('teacher').value,
        confirmation: 'updated',
        editInfo: 'ok',
        timestamp: new Date().toLocaleString()
      };

      // Add to database
      studentData.push(formData);
      saveData();

      // Show success
      statusDiv.className = 'status success';
      statusDiv.textContent = '✅ Success! Data saved locally';
      
      // Reset form
      document.getElementById('studentForm').reset();
      document.getElementById('regDate').valueAsDate = new Date();
      
      // Refresh display
      loadData();
      renderTable();

      // Hide message after 3 seconds
      setTimeout(() => {
        statusDiv.className = 'status';
      }, 3000);
    });

    // Render table
    function renderTable() {
      const container = document.getElementById('sheetContent');

      if (studentData.length === 0) {
        container.innerHTML = '<div class="no-data">No student records yet</div>';
        return;
      }

      let html = '<table>';
      
      // Headers
      html += '<tr>';
      const headers = [
        'ល.រ', 'Last Name', 'First Name', 'Gender', 'DOB', 'Age', 
        'Birth Cert', 'Reg Date', 'Grade', 'Level', 'Disability', 'Poor', 
        'Poverty Card', 'Vulnerable', 'Foster', 'Province', 'District', 
        'Commune', 'Village', "Father's Name", "Father's Occ", "Mother's Name", 
        "Mother's Occ", 'Teacher', 'Confirmation', 'Edit Info', 'Timestamp'
      ];
      headers.forEach(h => html += '<th>' + h + '</th>');
      html += '</tr>';

      // Data rows
      studentData.forEach((row, idx) => {
        html += '<tr>';
        html += '<td>' + row.etc + '</td>';
        html += '<td>' + row.lastName + '</td>';
        html += '<td>' + row.firstName + '</td>';
        html += '<td>' + row.gender + '</td>';
        html += '<td>' + row.dob + '</td>';
        html += '<td>' + row.age + '</td>';
        html += '<td>' + row.birthCert + '</td>';
        html += '<td>' + row.regDate + '</td>';
        html += '<td>' + row.grade + '</td>';
        html += '<td>' + row.level + '</td>';
        html += '<td>' + row.disability + '</td>';
        html += '<td>' + row.poor + '</td>';
        html += '<td>' + row.povertyCard + '</td>';
        html += '<td>' + row.vulnerable + '</td>';
        html += '<td>' + row.foster + '</td>';
        html += '<td>' + row.province + '</td>';
        html += '<td>' + row.district + '</td>';
        html += '<td>' + row.commune + '</td>';
        html += '<td>' + row.village + '</td>';
        html += '<td>' + row.fatherName + '</td>';
        html += '<td>' + row.fatherOcc + '</td>';
        html += '<td>' + row.motherName + '</td>';
        html += '<td>' + row.motherOcc + '</td>';
        html += '<td>' + row.teacher + '</td>';
        html += '<td>' + row.confirmation + '</td>';
        html += '<td>' + row.editInfo + '</td>';
        html += '<td>' + row.timestamp + '</td>';
        html += '</tr>';
      });

      html += '</table>';
      container.innerHTML = html;
    }

    // Load on page init
    window.addEventListener('load', loadData);
  </script>
</body>
</html>
