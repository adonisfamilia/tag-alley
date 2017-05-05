<template>
    <a-plane v-bind:rotation='rotation' v-bind:position='position' height='10' width='10' src='#brick'>
        <a-text  v-bind:value='header' position='0 0 0' align='center'></a-text>
        <a-image height='3' width='4' position='0 -2 .001' v-bind:src='img'> </a-image>
        <a-circle color='#F4D03F' v-on:click='toggle' zOffset='.001' position='0 -4.4 .001' radius='.5'>
            <a-text align='center' v-bind:value='textSelect' color='#5D8CAE'></a-text>
        </a-circle>
        <a-plane v-if='toggled' color='gray' opacity='.85' position='1 -3 3.6' height='.75' width='1.5'>
            <a-text height='1' width='1' v-bind:value='blurb' align='center'></a-text>
        </a-plane>
    </a-plane> 
</template>


<script>
export default {
    name: 'Wall',
    props: ['header','font','side','index','img', 'blurb'],
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
        },
        textSelect: function(){
            if(this.$data.toggled)
                return 'Less'
            return 'More'
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