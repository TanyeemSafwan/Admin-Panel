<script setup lang="ts">
const tableData = [
  {
    name: 'John Doe',
    id: 1,
    email: 'johndoe@example.com',
    phoneNumber: '+1234567890',
    dateAdded: '2024-10-25',
    status: 'Active',
    specialty: 'Cardiologist',
  },
  {
    name: 'Jane Smith',
    id: 2,
    email: 'janesmith@example.com',
    phoneNumber: '+0987654321',
    dateAdded: '2024-10-24',
    status: 'Inactive',
    specialty: 'Dermatologist',
  },
  {
    name: 'Alice Johnson',
    id: 3,
    email: 'alicejohnson@example.com',
    phoneNumber: '+1122334455',
    dateAdded: '2024-10-23',
    status: 'Active',
    specialty: 'Pediatrician',
  },
  {
    name: 'Bob Brown',
    id: 4,
    email: 'bobbrown@example.com',
    phoneNumber: '+5566778899',
    dateAdded: '2024-10-22',
    status: 'Inactive',
    specialty: 'Orthopedic Surgeon',
  },
  {
    name: 'Charlie Davis',
    id: 5,
    email: 'charliedavis@example.com',
    phoneNumber: '+6677889900',
    dateAdded: '2024-10-21',
    status: 'Active',
    specialty: 'Neurologist',
  },
]
</script>

<template>
  <div class="header">
    <div>
      <h1>List of Doctors</h1>
      <p class="subheading">365 doctors available</p>
    </div>

    <div class="add-doctor-button">
      <button
        style="
          background-color: var(--primary-green);
          color: var(--white);
          padding: 10px 20px;
          border: none;
          border-radius: 5px;
        "
      >
        <font-awesome-icon
          :icon="['fas', 'user-plus']"
          style="padding-right: 10px"
        />
        Add new doctor
      </button>
    </div>
  </div>

  <div>
    <table cellspacing="0" cellpadding="7">
      <tr
        style="
          background: var(--background-gray);
          color: var(--text-gray);
          text-align: left;
        "
      >
        <th>Name</th>
        <th>ID</th>
        <th>Email</th>
        <th>Phone Number</th>
        <th>Date Added</th>
        <th>Status</th>
      </tr>
      <tr v-for="table in tableData" :key="table.id">
        <td>
          <div style="display: flex; gap: 25px">
            <div style="padding-top: 10px">
              <font-awesome-icon :icon="['fas', 'user-doctor']" />
            </div>
            <div>
              <div>{{ table.name }}</div>
              <div style="color: var(--text-gray)">{{ table.specialty }}</div>
            </div>
          </div>
        </td>
        <td>{{ table.id }}</td>
        <td>{{ table.email }}</td>
        <td>{{ table.phoneNumber }}</td>
        <td>{{ table.dateAdded }}</td>
        <td>{{ table.status }}</td>
      </tr>
    </table>
  </div>
</template>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
}

.add-doctor-button {
  align-content: center;
}

.subheading {
  color: var(--text-gray);
}

td,
th {
  padding-right: 30px;
}
</style>
