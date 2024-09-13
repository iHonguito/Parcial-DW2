<template>
    <div class="div-imagenes" id="div-imagenes">

    </div>
</template>

<script>
export default {
    name: 'ImagenesComponent',
    methods: {
        cargarImagenes: async function () {
            let url = 'https://cobuses.com.co/APIV2/model/radio.php?dato=getallemisoras';

            await this.axios.get(url)
                .then(response => {
                    // Manejar la respuesta exitosa
                    let ImagesResponse = response.data;
                    const div_imagenes = document.getElementById('div-imagenes');
                    ImagesResponse.forEach(image => {
                        const div_imagen = document.createElement("div");
                        console.log(image.image)
                        div_imagen.innerHTML = `
                            <img src="${image.imagen}"/>
                        `
                        div_imagenes.appendChild(div_imagen)
                    });
                })
                .catch(error => {
                    // Manejar el error
                    console.error(error);
                });
        }
    },
    mounted() {
        this.cargarImagenes();
    }
}
</script>

<style>
.div-imagenes {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 10px;
}
</style>