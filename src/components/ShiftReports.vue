<template>
    <div class="shift-reports-card">
      <div class="header">
        <div>
          <h2 class="title">Subwarden Shift Reports</h2>
          <p class="subtitle">This gives an account of the shift reports sent</p>
        </div>
        <div class="profile-icons">
          <img src="../assets/profile-image.jpg" class="profile-image" alt="Profile 1">
          <img src="../assets/profile-image.jpg" class="profile-image" alt="Profile 2">
          <img src="../assets/profile-image.jpg" class="profile-image" alt="Profile 3">
          <span class="profile-add">+1</span>
        </div>
      </div>
      <div class="chart-container">
        <div class="day-column">
          <div class="line active"></div>
          <div class="day">S</div>
        </div>
        <div class="day-column">
          <div class="line inactive"></div>
          <div class="day">M</div>
        </div>
        <div class="day-column">
          <div class="line active-today"></div>
          <div class="day">T</div>
        </div>
        <div class="day-column">
          <div class="line"></div>
          <div class="day">W</div>
        </div>
        <div class="day-column">
          <div class="line"></div>
          <div class="day">T</div>
        </div>
        <div class="day-column">
          <div class="line"></div>
          <div class="day">F</div>
        </div>
        <div class="day-column">
          <div class="line"></div>
          <div class="day">S</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ShiftReports',
  };
  </script>
  
  <style scoped>
  /* Main card styling */
  .shift-reports-card {
    width: 550px;
    height: 250px;
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    background-color: #f9f9f9;
    font-family: 'Roboto', sans-serif;
    margin-left: 60px;
  }
  
  /* Header styling */
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
  
  .title {
    font-size: 18px;
    font-weight: 500;
    color: #4B3F3F;
    margin: 0;
  }
  
  .subtitle {
    font-size: 12px;
    color: #888;
    margin: 0;
  }
  
  /* Profile icons */
  .profile-icons {
    display: flex;
    align-items: center;
  }
  
  .profile-image {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    margin-left: -10px;
  }
  
  .profile-add {
    background-color: #ccc;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 14px;
    margin-left: -10px;
  }
  
  /* Chart container and columns */
  .chart-container {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
  }
  
  .day-column {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .line {
    width: 2px;
    height: 80px;
    background-color: #ddd;
    border-radius: 10px;
  }
  
  .active {
    background-color: #4CAF50;
  }
  
  .inactive {
    background-color: #FFCDD2;
  }
  
  .active-today {
    background-color: #1E88E5;
  }
  
  .day {
    margin-top: 10px;
    font-size: 14px;
    color: #666;
  }
  
  .day.active {
    font-weight: bold;
  }
  </style>
  