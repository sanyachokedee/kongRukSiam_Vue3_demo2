<template>
    <li>
        <h1>ชื่อ {{name}}</h1>
        <button @click="showDescription(id)">ดูรายละเอียด</button>&nbsp;
        <button @click="D=deleteEmployee(id)">ลบข้อมูล</button>
        <div v-show="isVisible">
            <p>เงินเดือน {{salary}} บาท , ตำแหน่งงาน : {{department}}</p>
        </div>     

    </li>
</template>
<script>
export default {
    name: "Person",
    data() {
        return {
            message: "ข้อมูลพนักงาน"
        }
    },
    props: {
        id: { 
            type:Number
        },
        name: {
            type: String,
            require:true
        },
        salary: {
            type: Number,
            default: 100
            
        },
        department: {
            type: String,
            required:true
        },
        isVisible: {
            type:Boolean
        }
    },
    methods: {
        showDescription(id) {  
            // console.log("show1 : " + id)
            this.$emit("show",id)
        },
        deleteEmployee(id) {
            console.log("delete :" + id)
            this.$emit("deleteEmployee_pr",id)
        }
    }
}
</script>
<style scoped>
li{
    margin:1rem 0;
    font-size: 1.5rem;
    font-weight: bold;
    background: #8ddba4;
    padding: 0.5rem;
    color: #1f1f1f;
    border-radius: 25px;
}
button{
    font: inherit;
    cursor:pointer;
    border: 1px solid #ff0077;
    background:#ff0077; 
    color: white;
    padding: 0.05rem 1rem;
    box-shadow: 1px 1px 2px rgba(0,0,0,0.26);

}
</style>