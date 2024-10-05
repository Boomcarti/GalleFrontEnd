<template>
    <div class="search-bar">
      <!-- Search Input -->
      <div class="search-input">
        <i class="fas fa-search"></i>
        <input type="text" placeholder="Search here..." />
      </div>
      
      <!-- Notification Icon -->
      <div class="notification">
        <i class="fas fa-bell"></i>
        <span class="notification-badge"></span>
      </div>
      
      <!-- Profile Image -->
      <div class="profile">
        <img src="@/assets/profile-image.jpg" alt="Profile" />
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'SearchBar',
  };
  </script>
  
  <style scoped>
  .search-bar {
    display: flex;
    align-items: center;
    background-color: #f8f9fa;
    padding: 10px;
    border-radius: 50px;
    box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
    width: 400px;
    justify-content: space-between;
  }
  
  .search-input {
    display: flex;
    align-items: center;
    background-color: #e6eaee;
    padding: 10px 15px;
    border-radius: 50px;
    flex-grow: 1;
    margin-right: 15px;
  }
  
  .search-input i {
    font-size: 18px;
    color: #999;
    margin-right: 10px;
  }
  
  .search-input input {
    border: none;
    background: none;
    outline: none;
    width: 100%;
    font-size: 16px;
    color: #666;
  }
  
  .notification {
    position: relative;
    margin-right: 15px;
  }
  
  .notification i {
    font-size: 20px;
    color: #666;
  }
  
  .notification-badge {
    position: absolute;
    top: -3px;
    right: -3px;
    width: 8px;
    height: 8px;
    background-color: red;
    border-radius: 50%;
  }
  
  .profile img {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    object-fit: cover;
  }
  </style>
  