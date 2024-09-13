<template>
    <div>
        <NavBarComponent></NavBarComponent>
        <div class="principal-content">
            <div class="div1">
                <ImagenesComponent></ImagenesComponent>
            </div>
            <div class="div2">
                <RadioComponent></RadioComponent>
            </div>
        </div>
        <FooterComponent></FooterComponent>
    </div>
</template>

<script>
import NavBarComponent from '../components/NavBarComponent.vue'
import ImagenesComponent from '../components/ImagenesComponent.vue'
import RadioComponent from '../components/RadioComponent.vue'
import FooterComponent from '../components/FooterComponent.vue'

export default {
    name: 'PrincipalPage',
    components: {
        NavBarComponent,
        ImagenesComponent,
        RadioComponent,
        FooterComponent
    }
}
</script>

<style scoped>
.principal-content {
    display: flex;
    justify-content: space-between;
    margin: 10px;
}

.div1 {
    flex: 4;
}

.div2 {
    flex: 3;
}
</style>