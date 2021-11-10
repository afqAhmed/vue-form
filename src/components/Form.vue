<template>
  <div class="flex flex-col items-center mt-16">
    <div>
      <h1 class="text-4xl mb-4">Form Details</h1>
    </div>
    <div class="w-1/3 bg-gray-300 rounded-xl">
      <form @submit.prevent="submitForm" class="p-8">
        <div class="flex py-4">
          <label class="label">Email</label>
          <input v-model="email" class="input" type="email" required />
        </div>
        <div class="flex py-4">
          <label class="label">Password</label>
          <input v-model="password" class="input" type="password" required />
        </div>
        <div class="flex py-4">
          <label class="label">Role</label>
          <select v-model="role" class="input">
            <option value="designer">Web Designer</option>
            <option value="developer">Web Developer</option>
          </select>
        </div>
        <div class="flex py-4">
          <label class="label">Skills</label>
          <input v-model="tempSkill" class="input" type="text" @keyup.enter="addSkill" required />
        </div>
        <div class="flex py-4 items-center">
          <input v-model="terms" type="checkbox" required />
          <label class="ml-2">Accept terms and conditions</label>
        </div>
        <div class="flex justify-center mt-8">
          <button class="bg-blue-600 px-6 py-3 uppercase text-white rounded-3xl shadow-xl hover:shadow-lg">Create Account</button>
        </div>
      </form>
    </div>
    <!-- <div class="w-1/3 py-4">
      <p v-if="email" class="p-4">Email: {{ email }}</p>
      <p v-if="password" class="p-4">Password: {{ password }}</p>
      <p v-if="role" class="p-4">Role: {{ role }}</p>
      <p v-if="terms" class="p-4">Terms: {{ terms }}</p>
      <ul class="py-4">
        <li v-for="skill in skills" :key="skill" class="py-0.5 inline-block  mx-1">
          <a class="cursor-pointer px-2 py-1 rounded-lg bg-gray-300" @click="removeSkill(skill)">{{ skill }}</a></li>
      </ul>
    </div> -->
  </div>
</template>

<script>
export default {
  name: 'Form',
  data() {
    return {
      email: '',
      password: '',
      role: '',
      terms: false,
      tempSkill: '',
      skills: [],
      passError: ''
    }
  },
  methods: {
    addSkill(e) {
      if (e.key === 'Enter' && this.tempSkill) {
        if (!this.skills.includes(this.tempSkill.toLowerCase())) {
          this.skills.push(this.tempSkill)
        }
        this.tempSkill = ''
      }
    },
    removeSkill(skill) {
      this.skills =this.skills.filter(item => skill !== item)
    }
  },
}
</script>
