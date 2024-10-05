<template>
    <div class="laundry-card">
      <div class="header">
        <span class="title">Laundry Rooms</span>
        <div class="status-text">
          <p><span class="bold-number">5</span> active</p>
          <p><span class="bold-number">3</span> inactive</p>
          <p><span class="bold-number">1</span> out of order</p>
        </div>
      </div>
      <div class="image-container">
        <img class="status-image" src="@/assets/laundry.webp" alt="Laundry Rooms">
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'LaundryRooms',
  };
  </script>
  
  <style scoped>
  .laundry-card {
    margin-left: 80px;
    width: 250px;
    padding: 15px;
    border-radius: 12px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    background-color: #f9f9f9;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }
  
  .header {
    text-align: left;
    width: 100%;
  }
  
  .title {
    font-weight: 500;
    font-size: 18px;
    color: #000;
  }
  
  .status-text {
    margin-top: 5px;
  }
  
  .status-text p {
    margin: 2px 0;
    font-size: 14px;
    color: gray;
  }
  
  .bold-number {
    font-weight: 600;
    color: #000;
  }
  
  .image-container {
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .status-image {
    width: 100px;
    height: 100px;
    border-radius: 10px;
  }
  </style>
  