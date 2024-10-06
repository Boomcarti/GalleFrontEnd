<template>
  <div class="status-containers">
    <div class="status-box" id="visitor-signin-box" @click="togglePopup('visitors')">
      <div class="status-header">
        <span class="status-title">Visitor Sign-in</span>
        <img src="@/assets/visitor-icon.webp" class="status-icon" alt="Visitor Icon">
      </div>
      <div class="status-content">
        <span class="status-number">27</span>
        <p class="status-description">People in currently</p>
      </div>
    </div>

    <!-- Popup for Visitors List -->
    <div v-if="showPopup === 'visitors'" class="popup-background" @click.self="closePopup">
      <div class="popup-body">
        <h3>Visitor List</h3>
        <ul>
          <li v-for="(visitor, index) in visitors" :key="index">
            <p><strong>Name:</strong> {{ visitor.name }}</p>
            <p><strong>Email:</strong> {{ visitor.email }}</p>
            <p><strong>Contact:</strong> {{ visitor.contact }}</p>
            <p><strong>Sign-in Time:</strong> {{ visitor.signInTime }}</p>
            <button class="button-material" @click="requestReception(visitor)">Request to Reception</button>
            <hr class="popup-separator">
          </li>
        </ul>
      </div>
    </div>

    <!-- Maintenance Requests Box -->
    <div class="status-box" id="maintenance-requests-box" @click="togglePopup('maintenance')">
      <div class="status-header">
        <span class="status-title">Outstanding Maintenance Requests</span>
        <img src="@/assets/maintenance-icon.webp" class="status-icon" alt="Maintenance Icon">
      </div>
      <div class="status-content">
        <span class="status-number">5</span>
        <p class="status-description">Washing Machine, +3 more</p>
      </div>
    </div>

    <!-- Maintenance Requests Details Popup -->
    <div v-if="showPopup === 'maintenance'" class="popup-background" @click.self="closePopup">
      <div class="popup-body">
        <h3>Maintenance Requests</h3>
        <ul>
          <li v-for="(issue, index) in maintenanceIssues" :key="index" :class="issue.status.toLowerCase()">
            <p><strong>Issue:</strong> {{ issue.issue }}</p>
            <p><strong>Appliance:</strong> {{ issue.appliance }}</p>
            <p><strong>Status:</strong> {{ issue.status }}</p>
            <p><strong>Reported On:</strong> {{ issue.reportedOn }}</p>
            <hr class="popup-separator">
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StatusContainers',
  data() {
    return {
      showPopup: null,
visitors: [
    { name: 'John Doe', email: 'john@example.com', contact: '1234567890', signInTime: '10:00 AM' },
    { name: 'Jane Smith', email: 'jane@example.com', contact: '0987654321', signInTime: '10:30 AM' },
    { name: 'Alice Johnson', email: 'alice.johnson@example.com', contact: '2345678901', signInTime: '11:00 AM' },
    { name: 'Bob Williams', email: 'bob.williams@example.com', contact: '3456789012', signInTime: '11:15 AM' },
    { name: 'Charlie Brown', email: 'charlie.brown@example.com', contact: '4567890123', signInTime: '11:30 AM' },
    { name: 'David Clark', email: 'david.clark@example.com', contact: '5678901234', signInTime: '11:45 AM' },
    { name: 'Ella Martinez', email: 'ella.martinez@example.com', contact: '6789012345', signInTime: '12:00 PM' },
    { name: 'Frank Thomas', email: 'frank.thomas@example.com', contact: '7890123456', signInTime: '12:15 PM' },
    { name: 'Grace Lee', email: 'grace.lee@example.com', contact: '8901234567', signInTime: '12:30 PM' },
    { name: 'Henry Scott', email: 'henry.scott@example.com', contact: '9012345678', signInTime: '12:45 PM' },
    { name: 'Irene Black', email: 'irene.black@example.com', contact: '0123456789', signInTime: '1:00 PM' },
    { name: 'Jack White', email: 'jack.white@example.com', contact: '1234567809', signInTime: '1:15 PM' },
    { name: 'Katy Green', email: 'katy.green@example.com', contact: '2345678012', signInTime: '1:30 PM' },
    { name: 'Liam Harris', email: 'liam.harris@example.com', contact: '3456780123', signInTime: '1:45 PM' },
    { name: 'Mia King', email: 'mia.king@example.com', contact: '4567801234', signInTime: '2:00 PM' },
    { name: 'Noah Lewis', email: 'noah.lewis@example.com', contact: '5678012345', signInTime: '2:15 PM' },
    { name: 'Olivia Young', email: 'olivia.young@example.com', contact: '6780123456', signInTime: '2:30 PM' },
    { name: 'Paul Robinson', email: 'paul.robinson@example.com', contact: '7890123467', signInTime: '2:45 PM' },
    { name: 'Quincy Evans', email: 'quincy.evans@example.com', contact: '8901234678', signInTime: '3:00 PM' },
    { name: 'Rachel Taylor', email: 'rachel.taylor@example.com', contact: '9012346789', signInTime: '3:15 PM' }
]
,
      maintenanceIssues: [
        { issue: 'Leaking pipe', appliance: 'Washing Machine', status: 'Active', reportedOn: 'Oct 1, 2024' },
        { issue: 'Broken door', appliance: 'Dryer', status: 'Inactive', reportedOn: 'Sept 28, 2024' },
        { issue: 'Burnt motor', appliance: 'Washing Machine', status: 'Out of Order', reportedOn: 'Sept 25, 2024' },
        { issue: 'Power failure', appliance: 'Dishwasher', status: 'Active', reportedOn: 'Oct 2, 2024' },
        { issue: 'Clogged filter', appliance: 'Dryer', status: 'Inactive', reportedOn: 'Sept 29, 2024' }
        // Add more maintenance issues...
      ]
    };
  },
  methods: {
    togglePopup(type) {
      this.showPopup = this.showPopup === type ? null : type;
    },
    closePopup() {
      this.showPopup = null;
    }
  }
};
</script>

<style scoped>
/* Main container for both boxes */
.status-containers {
  display: flex;
  justify-content: space-around;
  gap: 40px;
  margin-top: 40px;
}

/* Popup overlay and content */
.popup-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5); 
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup-body {
  background-color: #e0f7ff;
  padding: 20px;
  border-radius: 10px;
  width: 350px;
  max-height: 400px;
  overflow-y: auto;
}

.popup-body h3 {
  margin-bottom: 10px;
}

.popup-body ul {
  list-style: none;
  padding: 0;
}

.popup-body li {
  margin-bottom: 20px;
}

/* Horizontal rule (separator) between entries */
.popup-separator {
  border: 0;
  height: 1px;
  background: #ccc;
  margin-top: 10px;
  margin-bottom: 10px;
}

/* Maintenance Issue Status Color Coding */
.active {
  background-color: #4caf50; /* Green for active */
  color: white;
  padding: 10px;
  border-radius: 8px;
}

.inactive {
  background-color: #ffc107; /* Yellow for inactive */
  color: white;
  padding: 10px;
  border-radius: 8px;
}

.outoforder {
  background-color: #f44336; /* Red for out of order */
  color: white;
  padding: 10px;
  border-radius: 8px;
}

/* Styling for boxes */
.status-box {
  width: 220px;
  height: 200px;
  border-radius: 16px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: #000;
  box-shadow: 0 4px 14px rgba(0, 0, 0, 0.1);
  background-color: #fff;
  transition: transform 0.3s ease;
}

.status-box:hover {
  transform: translateY(-5px);
}

#visitor-signin-box {
  background: linear-gradient(135deg, #a1c4fd, #c2e9fb);
}

#maintenance-requests-box {
  background: linear-gradient(135deg, #fbc2eb, #a6c1ee);
}

.status-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-weight: bold;
}

.status-title {
  font-size: 18px;
}

.status-icon {
  width: 35px;
  height: 35px;
  object-fit: contain;
}

.status-content {
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.status-number {
  font-size: 42px;
  font-weight: bold;
}

.status-description {
  font-size: 14px;
  color: gray;
  margin-top: 5px;
}

/* Material Design Button */
.button-material {
  display: inline-block;
  padding: 10px 16px;
  border-radius: 24px;
  background-color: #2196f3;
  color: white;
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  border: none;
  box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.16);
  cursor: pointer;
  outline: none;
  transition: background-color 0.3s, box-shadow 0.3s;
  position: relative;
  overflow: hidden;
}

.button-material::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.4);
  opacity: 0;
  transform: translate(-50%, -50%) scale(0);
  transition: transform 0.3s, opacity 0.3s;
}

.button-material:active::after {
  transform: translate(-50%, -50%) scale(2);
  opacity: 1;
}

.button-material:hover {
  background-color: #1976d2;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
}

.button-material:focus {
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.3);
}
</style>
