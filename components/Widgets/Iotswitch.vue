<template>
<card>
    <div slot="header">
        <h5 class="card-title"> {{ config.selectedDevice.name }} - {{ config.variableFullName }}</h5>
    </div>
    <i class="fa " :class="[config.icon, getIconColorClass()]" aria-hidden="true" style="font-size: 30px;"></i>
    <base-switch @click="value = !value; sendValue()" :value="value" type="primary" on-text="ON" off-text="OFF" class="pull-right"></base-switch>
</card>

</template>


<script>
    export default {
        name: 'iotswitch',
        props: ['config'],
        
        data() {
            return {
                value: true,
                sending: false
            };
        },
        watch: {
            config: {
                immediate: true,
                deep: true,
                handler() {

                }
            }
        },

        mounted() {



        },
        beforeDestroy() {

        },
        methods: {

            getIconColorClass() {
                //para apagar el icono 
                if (!this.value){
                    return "text-dark";
                }

                if (this.config.class == "success") {
                    return "text-success";
                }
                if (this.config.class == "primary") {
                    return "text-primary";
                }
                if (this.config.class == "warning") {
                    return "text-warning";
                }
                if (this.config.class == "danger") {
                    return "text-danger";
                }
            },


            sendValue(){

                this.sending = true;
                setTimeout(() => {
                this.sending = false;
                }, 500);

                var aux = (!this.value)?this.config.messageOn:this.config.messageOff; 
                                
                const toSend = {
                    topic: this.config.userId + '/' + this.config.selectedDevice.dId + '/' + this.config.variable + '/actdata',
                    msg: {                 
                        value: aux
                    }
                };

               // console.log(toSend);
                $nuxt.$emit('mqtt-sender', toSend);

            }


        }
    };
</script>
<style></style>