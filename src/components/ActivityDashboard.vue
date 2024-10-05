<template>
    <div class="dashboard-container">
      <!-- Dark green pill background -->
      <div class="pill-background">
        <!-- Header with Create, Download, Edit buttons -->
        <button class="pill-btn create-btn">
          <i class="fas fa-plus"></i> Create
        </button>
        <button class="pill-btn download-btn">
          <i class="fas fa-download"></i> Download
        </button>
        <button class="pill-btn edit-btn">
          <i class="fas fa-edit"></i> Edit
        </button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ActivityDashboard",
  };
  </script>
  
  <style scoped>
  /* Dashboard container */
  .dashboard-container {
    display: flex;
    align-content: center;


  }
  
  /* Dark green pill background that holds the buttons */
  .pill-background {
    background-color: #005f30; /* Dark green */
    padding: 15px;
    border-radius: 50px; /* Creates the pill shape */
    display: flex;
    gap: 30px; /* Space between buttons */
    align-items: center;
    vertical-align: top;
    margin-bottom: 20px;
  }
  
  /* Pill button styles */
  .pill-btn {
    background-color: #b6e39b; /* Light green */
    color: #005f30; /* Dark green text */
    padding: 12px 30px;
    border-radius: 50px; /* Creates the pill shape */
    border: none;
    font-size: 16px;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 10px; /* Gap between icon and text */
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  .pill-btn:hover {
    background-color: #003b1f; /* Darker green on hover */
  }
  
  .pill-btn i {
    font-size: 18px; /* Icon size */
  }
  
  /* Adjust button styles individually if needed */
  .create-btn,
  .download-btn,
  .edit-btn {
    background-color: #b6e39b;
    color: #005f30;
  }
  </style>
  