<template>
    <div class="status-boxes">
      <div class="box" id="visitor-signin">
        <div class="box-header">
          <span class="title">Visitor Sign-in</span>
          <img src="@/assets/visitor-icon.webp" class="icon" alt="Visitor Icon">
        </div>
        <div class="box-content">
          <span class="number">27</span>
          <p class="description">People in currently</p>
        </div>
      </div>
      <div class="box" id="maintenance-requests">
        <div class="box-header">
          <span class="title">Outstanding Maintenance Requests</span>
          <img src="@/assets/maintenance-icon.webp" class="icon" alt="Maintenance Icon">
        </div>
        <div class="box-content">
          <span class="number">5</span>
          <p class="description">Washing Machine, +3 more</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'StatusBoxes',
  };
  </script>
  
  <style scoped>
  /* Main container for both boxes */
  .status-boxes {
    display: flex;
    justify-content: space-around; /* Adjust spacing between boxes */
    gap: 40px; /* Increase gap for better separation */
    margin-top: 40px; /* Top margin for better positioning */
  }
  
  /* Common styling for both boxes */
  .box {
    width: 220px; /* Increased width to match design */
    height: 200px; /* Increased height for better balance */
    border-radius: 16px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    color: #000;
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.1); /* Slightly stronger shadow for better contrast */
    background-color: #fff; /* Ensure background is white */
    transition: transform 0.3s ease; /* Add hover effect */
  }
  
  .box:hover {
    transform: translateY(-5px); /* Subtle hover effect */
  }
  
  /* Box 1: Visitor Sign-in */
  #visitor-signin {
    background: linear-gradient(135deg, #a1c4fd, #c2e9fb);
  }
  
  /* Box 2: Outstanding Maintenance Requests */
  #maintenance-requests {
    background: linear-gradient(135deg, #fbc2eb, #a6c1ee);
  }
  
  /* Header styling for both boxes */
  .box-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-weight: bold;
  }
  
  .title {
    font-size: 18px;
  }
  
  /* Icon styling */
  .icon {
    width: 35px; /* Increased icon size for better visibility */
    height: 35px;
    object-fit: contain;
  }
  
  /* Content styling for both boxes */
  .box-content {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
  }
  
  .number {
    font-size: 42px; /* Increased font size for numbers */
    font-weight: bold;
  }
  
  .description {
    font-size: 14px;
    color: gray;
    margin-top: 5px;
  }
  </style>
  