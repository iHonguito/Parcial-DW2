<template>
    <div id="radio-component" class="radio-component">

    </div>
</template>

<script>
    export default{
        name: 'RadioComponent',
        methods : {
            cargarNombresRadio : async function(){
                let url = 'https://cobuses.com.co/APIV2/model/radio.php?dato=getallgeneros';
                await this.axios.get(url)
                .then(response => {
                    // Manejar la respuesta exitosa
                    const div_radio = document.getElementById('radio-component');
                    let responseRadio = response.data
                    responseRadio.forEach(radio => {
                        const divRadio = document.createElement('div');
                        divRadio.innerHTML = `
                            <p>${radio.nombre}</p>
                        `;
                        div_radio.appendChild(divRadio);
                    })
                })
                .catch(error => {
                    // Manejar el error
                    console.error(error);
                });
            }
        },
        mounted(){
            this.cargarNombresRadio();
        }
    }
</script>

<style>
    .radio-component{
        margin: 10px;
    }

    .radio-component div{
        background-color: #333;
        
        color: white;
    }
    .radio-component div:hover{
        background-color: white;
        color: #333;
    }
    .radio-component div p{
        text-align: center;
        padding: 5px 0px;
        border-radius: 5px;
    }
</style>