<template>
    <div class="navbar">
      <div class="nav-item" :class="{ active: activeTab === 'Home' }" @click="navigate('Home')">
        <i class="fas fa-home"></i>
        <span>Home</span>
      </div>
      <div class="nav-item" :class="{ active: activeTab === 'Calendar' }" @click="navigate('Calendar')">
        <i class="fas fa-calendar-alt"></i>
        <span>Calendar</span>
      </div>
      <div class="nav-item" :class="{ active: activeTab === 'Schedule' }" @click="navigate('Schedule')">
        <i class="fas fa-clock"></i>
        <span>Schedule</span>
      </div>
      <div class="nav-item" :class="{ active: activeTab === 'Resources' }" @click="navigate('Resources')">
        <i class="fas fa-folder-open"></i>
        <span>Resources</span>
      </div>
      <div class="nav-item" :class="{ active: activeTab === 'Log' }" @click="navigate('Log')">
        <i class="fas fa-file-alt"></i>
        <span>Log</span>
      </div>
      <div class="nav-item" :class="{ active: activeTab === 'Settings' }" @click="navigate('Settings')">
        <i class="fas fa-cog"></i>
        <span>Settings</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        activeTab: 'Home',
      };
    },
    methods: {
      navigate(tab) {
        this.activeTab = tab;
        console.log(`Navigating to: ${tab}`);
      }
    }
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap'); /* Import the font */
  
  .navbar {
    display: flex;
    justify-content: space-evenly;
    padding: 10px 20px;
    background-color: #f8f9fa;
    border-radius: 20px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    margin-right: 20px;
  }
  
  .nav-item {
    display: flex;
    align-items: center;
    font-size: 14px;
    cursor: pointer;
    padding: 10px;
    margin: 0 40px;
    color: #000;
    transition: color 0.2s ease;
    font-family: 'Poppins', sans-serif; /* Apply the font */
  }
  
  .nav-item i {
    font-size: 20px;
    margin-right: 8px;
  }
  
  .nav-item.active {
    color: #ff6f00;
  }
  
  .nav-item.active i {
    color: #ff6f00;
  }
  
  .nav-item:hover {
    color: #ff6f00;
  }
  </style>
  