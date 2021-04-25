<template>
    <header class="text-center bg-red-400 text-white p-4 mb-10"> 
        <div class="text-3xl md:text-5xl font-bold mb-3">
            <img src="../assets/virus.png" alt="" class="inline">
            <!-- <i class="fa fa-viruses"></i> -->
            {{ title }}
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            title: 'Covid Tracker',
        }
    }
}
</script>