<template>
    <div class="activity-timeline">
      <!-- Header -->
      <div class="header">
        <div class="header-left">
          <h3>My Activity</h3>
          <p>What is waiting for you today</p>
        </div>
        <div class="header-right">
          <button class="add-task-btn">
            <span class="plus-icon">+</span> Add task
          </button>
          <button class="calendar-btn">
            <i class="calendar-icon">📅</i>
          </button>
        </div>
      </div>
  
      <!-- Timeline -->
      <div class="timeline-container">
        <div class="time-labels">
          <div v-for="hour in hours" :key="hour" class="time-label">{{ hour }}</div>
        </div>
  
        <div class="tasks">
          <!-- Project Onboarding Task -->
          <div class="task task-onboarding">
            <span class="task-title">Project Onboarding</span>
            <div class="avatars">
              <img class="avatar" src="../assets/profile-image.jpg" alt="Avatar 1" />
              <img class="avatar" src="../assets/profile-image.jpg" alt="Avatar 2" />
              <img class="avatar" src="../assets/profile-image.jpg" alt="Avatar 3" />
              <span class="extra-count">+1</span>
            </div>
            <span class="task-time">MS Teams Meeting</span>
          </div>
  
          <!-- Design Research Task -->
          <div class="task task-design-research">
            <span class="task-title">Design Research</span>
            <img class="avatar" src="../assets/profile-image.jpg" alt="Avatar 4" />
            <span class="task-time">MS Teams Meeting</span>
          </div>
  
          <!-- Lunch Break -->
          <div class="task task-lunch-break">
            <span class="task-title">Lunch Break</span>
          </div>
  
          <!-- Current Time Line -->
          <div class="current-time-line"></div>
          <div class="current-time">15:00</div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ActivityTimeline",
    data() {
      return {
        hours: ['07:00', '08:00', '09:00', '10:00', '11:00', '12:00', '13:00', '14:00', '15:00', '16:00', '17:00'],
      };
    },
  };
  </script>
  
  <style scoped>
  /* Container Styling */
  .activity-timeline {
    background-color: #f6f8fb;
    border-radius: 20px;
    padding: 20px;
    font-family: 'Poppins', sans-serif;
    margin-top: 30px;
  }
  
  /* Header Styling */
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
  
  .header-left h3 {
    font-weight: 600;
    font-size: 24px;
  }
  
  .header-left p {
    color: #8a8a8a;
    margin: 5px 0;
  }
  
  .header-right button {
    border: none;
    border-radius: 25px;
    padding: 10px 20px;
    margin-left: 10px;
    cursor: pointer;
    font-size: 16px;
  }
  
  .add-task-btn {
    background-color: #333;
    color: white;
    display: flex;
    align-items: center;
  }
  
  .add-task-btn .plus-icon {
    font-size: 20px;
    margin-right: 8px;
  }
  
  .calendar-btn {
    background-color: #fff;
    color: #333;
  }
  
  .calendar-btn .calendar-icon {
    font-size: 20px;
  }
  
  /* Timeline Section */
  .timeline-container {
    display: flex;
    position: relative;
  }
  
  .time-labels {
    width: 10%;
  }
  
  .time-label {
    color: #8a8a8a;
    font-size: 14px;
    margin-bottom: 20px;
  }
  
  .tasks {
    width: 90%;
    position: relative;
  }
  
  .task {
    border-radius: 10px;
    padding: 15px;
    margin-bottom: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 14px;
  }
  
  .task-title {
    font-weight: bold;
  }
  
  .avatars {
    display: flex;
    align-items: center;
  }
  
  .avatar {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    margin-right: 5px;
  }
  
  .extra-count {
    background-color: #333;
    color: white;
    padding: 5px;
    border-radius: 50%;
  }
  
  .task-time {
    color: #8a8a8a;
  }
  
  .task-onboarding {
    background-color: #ccffcc;
  }
  
  .task-design-research {
    background-color: #d9d9d9;
  }
  
  .task-lunch-break {
    background-color: #dabfff;
  }
  
  /* Current Time Indicator */
  .current-time-line {
    position: absolute;
    top: 0;
    left: 60%;
    height: 100%;
    width: 1px;
    background-color: #000;
  }
  
  .current-time {
    position: absolute;
    top: 0;
    left: 60%;
    background-color: #fff;
    padding: 5px;
    border-radius: 5px;
  }
  </style>
  