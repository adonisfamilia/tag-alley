<template>
    <a-plane v-bind:rotation='rotation' v-bind:position='position' color='blue' height='10' width='10'>
        <a-text v-bind:value='header' position='0 0 0' align='center'></a-text>
        <a-image height='3' width='4' position='0 -2 .001'> </a-image>
        <a-circle v-on:click='toggle' zOffset='.001' position='0 -4.2 .001' radius='.5'></a-circle>
        <a-plane v-if='toggled' color='gray' opacity='.65' position='0 -3.2 3.8' height='.75' width='1.5'>
            <a-text value="Welcome\nHello World!" align='center'></a-text>
        </a-plane>
    </a-plane> 
</template>


<script>
export default {
    name: 'Wall',
    props: ['header','font','side','index'],
    data: function(){
    return {
        toggled: false
    }},
    computed: {
        position: function(){
          console.log((this.index+1)*-10)
          if(this.side === 'left'){
                return '-5 5 ' + ((this.index+1)*-10)
            }else{
               return '5 5 ' + ((this.index+1)*-10)
            }
        },
        rotation: function(){
            if(this.side === 'left'){
                return '0 90 0' 
            }else{
               return '0 270 0'
            }
        }
    },
    methods: {
        toggle: function(){
            console.log(this.$data)
            this.$data.toggled = !this.$data.toggled
        }
    }
}
</script>