<template>
  <div class="home-page-container">
    <div class="home-page">
      <NavBar />
      <SearchBar />
    </div>
    <div class="content-container" style="display: flex; flex-direction: row; width: 100%;">
      <div style="display: flex; flex-direction: column; flex: 1;margin-top: 40px;margin-right: 50px">
        <ShiftReports/>
        <StatusBoxes/>
      </div>
      <div style="display: flex; flex-direction: column; flex: 1;margin-top: 40px;margin-: 50px">
        <ActivityDashboard/>
        <div style="display: flex; flex-direction: row; justify-content: center;">
          <PositionShift/>
          <LaundryRooms/>
        </div>
        <ActivityTimeline/>
      </div>
    </div>
  </div>
</template>

<script>
  import NavBar from './NavBar.vue';
  import SearchBar from './SearchBar.vue';
  import ActivityDashboard from './ActivityDashboard.vue';
  import PositionShift from './PositionShift.vue';
  import LaundryRooms from './LaundryRooms.vue';
  import ShiftReports from './ShiftReports.vue';
  import StatusBoxes from './StatusBoxes.vue';
  import ActivityTimeline from './ActivityTimeline.vue';

  export default {
    name: 'HomePage',
    components: {
      NavBar,
      SearchBar,
      ActivityDashboard,
      PositionShift,
      LaundryRooms,
      ShiftReports,
      StatusBoxes,
      ActivityTimeline
    },
  };
</script>

<style scoped>
.home-page-container {
  padding: 20px; /* Padding for the entire page */
  box-sizing: border-box; /* Ensure padding is included in the element's total width/height */
}

.home-page {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f8f9fa;
  border-radius: 20px;
}

NavBar {
  flex-grow: 1;
}

SearchBar {
  margin-left: 10px;
}

.content-container {
  padding: 0 40px; /* Padding for the sides of the content */
  width: 100%;
  box-sizing: border-box; /* Ensure padding is included in the element's total width */
}
</style>
