<template>
  <div class="laundry-card" @click="toggleLaundryGrid">
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
    
    <!-- Display grid of laundry machines when the card is clicked -->
    <div v-if="showLaundryGrid" class="laundry-grid">
      <div 
        v-for="(machine, index) in machines" 
        :key="index" 
        class="machine" 
        :class="{ free: machine.status === 'Free', busy: machine.status === 'Busy', outOfOrder: machine.status === 'Out of Order' }"
      >
        <p>{{ machine.name }}</p>
        <p>{{ machine.status }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LaundryRooms',
  data() {
    return {
      showLaundryGrid: false,
      machines: [
        { name: 'Machine 1', status: 'Free' },
        { name: 'Machine 2', status: 'Busy' },
        { name: 'Machine 3', status: 'Free' },
        { name: 'Machine 4', status: 'Busy' },
        { name: 'Machine 5', status: 'Out of Order' },
        { name: 'Machine 6', status: 'Busy' },
        { name: 'Machine 7', status: 'Free' },
        { name: 'Machine 8', status: 'Busy' },
      ],
    };
  },
  methods: {
    toggleLaundryGrid() {
      this.showLaundryGrid = !this.showLaundryGrid;
    },
  },
};
</script>

<style scoped>
.laundry-card {
  margin-left: 150px;
  width: 250px;
  padding: 15px;
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  background-color: #f9f9f9;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  cursor: pointer;
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

/* Laundry machine grid */
.laundry-grid {
  margin-top: 15px;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
  width: 100%;
}

.machine {
  padding: 10px;
  border-radius: 8px;
  text-align: center;
  color: white;
  font-weight: bold;
}


.machine.free {
  background-color: #4caf50; 
}

.machine.busy {
  background-color: #f44336;
}

.machine.outOfOrder {
  background-color: #9e9e9e; 
}
</style>
