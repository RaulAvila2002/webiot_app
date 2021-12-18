<template>
<card>
    Slader bar
</card>   
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default {
   // props: ['config'],
    data() {
        return {
            config: {
                userId: 'userid',
                selectedDevice: {
                    name: "Home",
                    dId: "8888",
                    templateName: "Power Sensor",
                    templateId: "erterte5563546345",
                    serverRule: false
                },
                variableFullName: "Meter",
                icon: "fa-sun",
                column: 'col-6',
                widget: 'slader',
                class: 'danger',
                variable: "unniquestring",

            },
        }
    }
}


// /userId/dId/unniquestring/sdata      disp -> plataforma
// /userId/ + /    +      /sdata        disp -> plataforma
// /userId/ + /    +      /actdata      plataforma ->  disp

</script>

<script>

</script>