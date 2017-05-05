<template>
  <a-scene id="app">
    <a-assets> 
      <img id='sky' src='src/assets/daylight.png'></img>
      
      <img id="wildstyle" src="src/assets/wildstyle.png" crossorigin="anonymous"/>
      <img id='brick' src="src/assets/crt-brick.jpg"/>
      <img id='concrete' src="src/assets/concrete.jpg"/>

      <img id='blockandthrow' src="src/assets/BlockbusterGlow.jpg"/>
      <img id='wildandtag' src="src/assets/wildandtag.jpg"/>
      <img id='heavenandpiece' src="src/assets/heavenpiece.jpg"/>
      <img id='stencilandslap' src="src/assets/stencilslap.jpg"/>

       <img id='dondi' src="src/assets/dondi.jpg"/>
      <img id='cornbread' src="src/assets/cornbread.jpg"/>
      <img id='trains' src="src/assets/trains.jpg"/>


    <img id='first_pol' src="src/assets/first_pol.PNG" />
    <img id='second_pol' src="src/assets/second_pol.jpg" />
    <img id='third_pol' src="src/assets/third_pol.PNG" />
    <img id='lenon' src="src/assets/lenon.jpg" />

     <img id='ses' src="src/assets/ses.png"/>

      <!--<img id="marsnevenekskdemo" src="https://ucarecdn.com/1b676bc8-54fe-458d-910a-3ddee53d9a4c/" crossorigin="anonymous"/>-->
    </a-assets>

    <a-camera>
      <a-cursor></a-cursor>
    </a-camera>

    <a-sky src='#sky'></a-sky>
    <a-plane height='80' width='10' src='#concrete' rotation='-90 0 0' repeat='5 40' position='0 0 -35'></a-plane>
    <a-plane height='10' width='10' src='#brick' rotation='0 90 0' position='-5 5 0'></a-plane>
     <a-plane height='10' width='10' src='#brick' rotation='0 -90 0' position='5 5 0'></a-plane>
     <a-plane height='10' width='10' src='#brick' rotation='0 180 0' position='0 5 5'></a-plane>
     <a-plane height='10' width='10' src='#brick'  position='0 5 -65'></a-plane>
    
     

    <wall v-for='(tag, index) in tags' v-bind:header='tag.header' v-bind:blurb='tag.blurb' v-bind:img='tag.img' v-bind:index='index' side='right'></wall>
    <wall v-for='(tag, index) in tagleft' v-bind:header='tag.header' v-bind:blurb='tag.blurb' v-bind:img='tag.img' v-bind:index='index' side='left'></wall>
  </a-scene>
</template>

<script>
import Wall from './components/Wall.vue'
import gStyles from './components/Styles.vue'

export default {
  name: 'app',
  data () {
    return {
      tags: [
            {header: '', side: 'right', img: '#blockandthrow',
              blurb: '1) Blockbuster: This is a large throw-up in blocky letters. They are used to cover a large area in a small amount of time. They’re often painted with rollers which make them easier and faster to do.\n2) Throw up: This is a more complicated version of a tag. It has two or more colors and typically uses bubble-style lettering.'},
            {header: '', side: 'right', img: '#heavenandpiece',
            blurb: '3) Heaven: A heaven is a tag in an extremely difficult/dangerous place to get to. These gain a lot of attention and respect from other artists.\n4) Piece:   A piece is something that takes longer to paint. A piece in an obvious place will gain the artist respect from other artists because standing in an obvious place painting on walls where graffiti is illegal is a great risk.'},
             {header: '', side: 'right', img: '#stencilandslap',
             blurb: "5) A stencil is a quick and precise way to put up detailed pieces. They are an easy way to make something repeatable.\n6) Slap (or sticker)  A sticker is like a smaller version of a poster and easy to execute. It’s common for people to put their tags on postage labels and plaster them around a city on signs or poles. They’re quickly executed which makes them common."},
            {header: '', side: 'right', img: '#wildandtag',
               blurb: "7) Wildstyle is an elaborate version of a throw up which is usually difficult to read. It consists of curves, spikes, arrows, etc.\n8) A tag is considered the simplest style. It includes an artist's name and symbol"},
            {header: '', side: 'right', img: '#lenon',
              blurb: 'Politics has long been a part of modern graffiti culture. The illegal nature of graffiti is a political statement in itself - an act of protest against the establishment and its norms, and unquestioning respect for property rights over human rights.'},
            {header: '', side: 'right', img: '#ses',
            blurb: 'Example digital piece our team created for this display'}
      ],
      tagleft: [
            {header: '', side: 'right', img: '#cornbread',
            blurb:"Graffiti originated in the late 60s in Philadelphia with a high school student named Cornbreadwho began using the art form as a way to gain attention from the community. Urban graffiti isalso accredited to New York City around the same time period. In the late 1960s, Taki 183, usedhis profession as a messenger as a guide through spreading his art throughout subway trains.By writing his name on every track that he went to he gained a notoriety that many othersbecame inspired by and wanted to mimic through by the same idea."},
            {header: '', side: 'right', img: '#trains',
            blurb: "The word “graffiti” comes from the Italian word graffiato meaning “scratched.”A big effort that was emphasized by artists was the intention of getting their names around asmuch as possible but once that was achieved, they would start to outdo each other in terms ofstyle. Spray cans were utilized as a way of doing the art more efficiently and more easilyavoiding getting caught by someone. They allowed for graffiti to evolve from small tags on theinsides of trains to huge murals on many different subway cars."},
            {header: '', side: 'right', img: '#dondi',
            blurb: "1970s “style wars”: older artists began taking on younger ones to help them with large pieces.Writing crews started to come around, who would collaborate and share their future ideastogether and then figure out how to emulate them."},
            {header: '', side: 'right', img: '#first_pol',
              blurb: 'Politics has long been a part of modern graffiti culture. The illegal nature of graffiti is a political statement in itself - an act of protest against the establishment and its norms, and unquestioning respect for property rights over human rights.'},
            {header: '', side: 'right', img: '#second_pol',
            blurb: 'Powerful entities such as corporations or otherwise the elite upper class have number of ways they can exert political influence and propagate their views - either directly through bribing officials or indirectly through sponsoring and broadcasting their opinions through TV, radio, and billboards, etc. This is why graffiti is an incredibly powerful political tool in Hip Hop culture for the silenced minority, who otherwise don’t have the means to reach the public - it is literal “writing on the wall” expressing dissent of these communities.'},
            {header: '', side: 'right', img: '#third_pol', 
            blurb: 'Political graffiti and street art can be a complex mural or a simple written statement. For example, “Sous les pavés, la plage,” (1968, bottom) which translates to “under the paving stones, the beach,” is graffiti from the French protesters that reflected the freedom that could be found under the constrictions of French society, which the protesters were attempting to overthrow.'}  
      ]
      }
  },
  components: {
    'wall': Wall,
    'gstyles': gStyles
  }
}
</script>

<style>

</style>
