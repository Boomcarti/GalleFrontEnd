<template>
  <div class="dashboard-container">
    <!-- Dark green pill background -->
    <div class="pill-background">
      <!-- Header with Create, Download, Edit buttons -->
      <button class="pill-btn create-btn" @click="openModal">
        <i class="fas fa-plus"></i> Create
      </button>
      <button class="pill-btn download-btn">
        <i class="fas fa-download"></i> Download
      </button>
      <button class="pill-btn edit-btn">
        <i class="fas fa-edit"></i> Edit
      </button>
    </div>

    <!-- Modal for creating a shift assignment -->
    <div v-if="isModalOpen" class="modal-overlay" @click.self="closeModal">
      <div class="modal-content">
        <h3>Create Shift Assignment</h3>
        <form @submit.prevent="submitShift">
          <!-- Shift name input -->
          <div class="form-group">
            <label for="shiftName">Shift Name</label>
            <input type="text" id="shiftName" v-model="shiftName" placeholder="Enter shift name" required />
          </div>

          <!-- Start Time input -->
          <div class="form-group">
            <label for="startTime">Start Time</label>
            <input type="time" id="startTime" v-model="startTime" required />
          </div>

          <!-- End Time input -->
          <div class="form-group">
            <label for="endTime">End Time</label>
            <input type="time" id="endTime" v-model="endTime" required />
          </div>

          <!-- Staff select input -->
          <div class="form-group">
            <label for="staff">Assign to Staff</label>
            <select id="staff" v-model="assignedStaff" required>
              <option value="">Select Staff Member</option>
              <option v-for="staff in staffList" :key="staff.id" :value="staff.name">{{ staff.name }}</option>
            </select>
          </div>

          <!-- Submit button -->
          <div class="form-group">
            <button type="submit" class="btn-submit">Create Shift</button>
            <button type="button" class="btn-cancel" @click="closeModal">Cancel</button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ActivityDashboard",
  data() {
    return {
      isModalOpen: false,
      shiftName: "",
      startTime: "",
      endTime: "",
      assignedStaff: "",
      staffList: [
        { id: 1, name: "Aubrey Ntini" },
        { id: 2, name: "Jane Doe" },
        { id: 3, name: "John Smith" }
      ],
    };
  },
  methods: {
    openModal() {
      this.isModalOpen = true;
    },
    closeModal() {
      this.isModalOpen = false;
      this.resetForm();
    },
    submitShift() {
      // Logic for submitting the shift assignment
      const newShift = {
        shiftName: this.shiftName,
        startTime: this.startTime,
        endTime: this.endTime,
        assignedStaff: this.assignedStaff
      };
      console.log("New Shift Created:", newShift);
      this.closeModal();
    },
    resetForm() {
      this.shiftName = "";
      this.startTime = "";
      this.endTime = "";
      this.assignedStaff = "";
    }
  }
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

/* Modal styles */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  width: 400px;
  max-height: 80%;
  overflow-y: auto;
}

.modal-content h3 {
  margin-bottom: 15px;
  color: #005f30;
}

/* Form group styles */
.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  margin-bottom: 5px;
  color: #333;
}

.form-group input,
.form-group select {
  width: 100%;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

/* Button styles */
.btn-submit {
  background-color: #4caf50;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  margin-right: 10px;
}

.btn-cancel {
  background-color: #f44336;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.btn-submit:hover {
  background-color: #45a049;
}

.btn-cancel:hover {
  background-color: #d32f2f;
}
</style>
