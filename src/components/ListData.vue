<template>
    <ul>       
            <Person v-for="item  in employees" :key="item.id" :name="item.name" :id="item.id" :salary="item.salary"
                :department="item.department" :isVisible="item.isVisible" @show="toggleVisible"
                @deleteEmployee_pr = "removeEmployee"
            />
        </ul>

</template>
<script>

import Person from './Person.vue'

export default {
    name: "ListData",
    components: {
        Person,
 
    },

    data() {
        return {
            employees: [
                { id: 1, name: "ก้อง", salary: 40000, department: "programer", isVisible: false },
                { id: 2, name: "ก้อง", salary: 32000, department: "ฝ่ายการตลาด", isVisible: false },
                { id: 3, name: "แก้ม", salary: 35000, department: "Graphics", isVisible: false },
                { id: 4, name: "โจโจ้", salary: 3000, department: "ฝ่ายขาย", isVisible: false },
                { id: 5, name: "สมปอง", salary: 25000, department: "ฝ่ายบริหาร" },
                { id: 6, name: "สมศักดิ์", isVisible: false },
            ]
        }
    },
    methods: {
        toggleVisible(id) {
            // console.log("Child Id: " + id)
            this.employees = this.employees.map((item) => {
                if (item.id === id) {
                    return {...item,isVisible:!item.isVisible}
                }
                return item
            })
        },
        removeEmployee(id) {
            // console.log("ListData_pr :" + id)
            this.employees = this.employees.filter(item => {
                return item.id !== id
            })
        }
    }



}
</script>
<style scoped>
ul {
    list-style: none;
    margin: 0;
    padding: 0;

}
</style>