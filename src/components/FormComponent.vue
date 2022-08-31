<template>
    <form>
        <div class="form-control">
            <label for="emp-name">ชื่อพนักงาน</label>
            <input type="text" v-model.trim="employee.name">
            <p>{{employee.name}}</p>
        </div>
        <div class="form-control">
            <label for="emp-salary">เงินเดือน</label>
            <input type="number" v-model="employee.salary">
            <p>{{employee.salary}}</p>
        </div>
        <div>
            <button>บันทึกข้อมูล</button>
        </div>
        {{JSON.stringify(employee)}}
    </form>

</template>
<script>
export default {
    name: "FormComponent",
    data() {
        return {
            employee: {
                name: "",
                salary:25000
            }
        }
    }
}
</script>
<style scoped>
    form{
        margin:2rem auto;
        max-width: 40rem;
        border-radius: 12px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.25);
        padding:2rem;
        background: white;
    }
    .form-control{
        margin: 0.5rem 0;
    }
    label{
        font-weight: bold;
    }
    input{
        display:block;
        width: 100%;
        font:inherit;
        margin-top: 0.5rem;
    }
    button{
        font: inherit;
        background: orange;
        color:white;
        cursor:pointer;
        padding: 0.75rem 2rem;
        border-radius: 5px;
    }
</style>