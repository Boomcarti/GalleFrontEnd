<template>
    <div class="card">
      <div class="header">
        <span class="title">SFDA</span>
        <div class="shift-time">
          <span>Shift Time :</span> 14:00hrs to 16:00hrs
        </div>
      </div>
      <div class="content">
        <img class="profile-image" src="@/assets/profile-image.jpg" alt="Profile Photo">
        <span class="name">Aubrey Ntini</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'PositionShift',
  };
  </script>
  
  <style scoped>
  /* Applying the Roboto font */
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap');
  
  .card {
    font-family: 'Roboto', sans-serif; /* Font applied to the entire card */
    width: 200px;
    padding: 10px;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    background-color: #f9f9f9;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  
  .header {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-bottom: 10px;
  }
  
  .title {
    font-weight: 500; /* Medium weight for title */
    font-size: 16px;
  }
  
  .shift-time {
    font-size: 12px;
    color: gray;
  }
  
  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .profile-image {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    border: 2px solid #ddd;
  }
  
  .name {
    margin-top: 10px;
    font-size: 14px;
    font-weight: 500;
  }
  </style>
  