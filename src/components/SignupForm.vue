<template>
    <form @submit.prevent="handleSubmit">
        <label>Email</label>
        <input type="email" required v-model="email">
        <label>Password</label>
        <input type="password" required v-model="password">
        <label>Role :</label>
        <select v-model="role">
            <option value="webdev">Web Developer</option>
            <option value="webdes">Web Designer</option>
            <option value="mobdev">Mobile Developer</option>
        </select>

        <div class="terms">
            <input type="checkbox" v-model="terms" required>
            <label>Accept terms and condition</label>
        </div>

        <div class="names">
            <input type="checkbox" v-model="names" value="sarah">
            <label for="Accept terms and condition">Sarah</label>
            <input type="checkbox" v-model="names" value="yoshi">
            <label for="Accept terms and condition">Yoshi</label>
            <input type="checkbox" v-model="names" value="sandra">
            <label for="Accept terms and condition">Sandra</label>
        </div>

        <label>Skills</label>
        <input type="text" v-model="tempSkill" @keydown.enter.prevent="addSkill">
        <div v-for="skill in skills" :key="skill">
            <p @click="deleteSkill(skill)">
                {{ skill }}
            </p>
        </div>

        <div class="submit">
            <button>Create Account</button>
        </div>

    </form>
    <p>Email : {{ email }}</p>
    <p>Role : {{ role }}</p>
    <p>Names : {{ names }}</p>
    <p>Skills : {{ skills }}</p>
</template>

<script>

export default {
    name: 'SignupForm',
    data() {
        return {
            email: '',
            password: '',
            role: '',
            terms: false,
            names: [],
            tempSkill: '',
            skills: []
        }
    },
    methods: {
        addSkill(e) {
            if (e.key === 'Enter' && this.tempSkill) {
                if (!this.skills.includes(this.tempSkill)) {
                    this.skills.push(this.tempSkill)
                }
                this.tempSkill = ''
            }
            // console.log(e)
        },
        deleteSkill(skill) {
            this.skills = this.skills.filter((item) => {
                return skill !== item
            })
        },
        handleSubmit() {
            console.log()
        }
    }
}
</script>

<style></style>