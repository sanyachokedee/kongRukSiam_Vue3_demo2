<template>
    <li>       
            <img src="https://cdn-icons-png.flaticon.com/512/3177/3177440.png" alt=""> 
            <hr/>
            <slot name="card-header"></slot>
            <slot name="card-button"></slot>
            <slot name="card-content"></slot>
    </li>
       
        
</template>
<script>

export default {
    name: "Card",
}
</script>
<style scoped>
    li{
    margin:1rem 0;
    font-size: 1.5rem;
    font-weight: bold;
    background: purple;
    padding: 0.5rem;
    color: white;
    border-radius: 25px;
}
img{
    width: 100px;
    height: 100px;
}
</style>