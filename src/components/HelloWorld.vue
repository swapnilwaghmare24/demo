<template>
  <div id="app">
  
  <ul>
    <li v-for="item in items" :key="item">
      {{ item }}
    </li>
  </ul>
  <h3>Type here:</h3>
  <textarea v-model="message" class="message" rows="5" maxlength="72"/>
  <br>
  <p class="booktext">{{ message }} </p>
  <input v-model="checkedNames" type="checkbox" id="john" value="John"/>
  <label for="john"> John</label>
  
  <input v-model="checkedNames" type="checkbox" id="paul" value="Paul"/>
  <label for="paul"> Paul</label>
  
  <input v-model="checkedNames" type="checkbox" id="george" value="George"/>
  <label for="george"> George</label>
  
  <input v-model="checkedNames" type="checkbox" id="ringo" value="Ringo"/>
  <label for="ringo"> Ringo</label>
  <br>
  <span>Checked names: {{ checkedNames }}</span>

  <span v-for="option in options" :key="option">
    <input v-model="checkedNames" :id="option.value" :value="option.value" type="checkbox">
    <label for="option.value">  {{option.value}}</label>
  </span>

  <br>
  <span>Checked names: {{ checkedNames }}</span>
  <br>
  <br>
  <h3>What is your favorite kind of taco?</h3>
  <textarea v-model="tacos"></textarea>
  <br>
  <button v-show="tacos" type="submit">Let us know!</button>
  <br>
  <br>
   <h3>Do you like tacos?</h3>

    <input v-model="tacos" value="yes" type="radio" id="yes" />
    <label for="yes"> yes</label><br />

    <input v-model="tacos" value="no" type="radio" id="no" />
    <label for="no"> no</label><br />

    <p v-if="tacos === 'yes'" class="thumbs">👍</p>
    <p v-else-if="tacos === 'no'">you're a monster</p>

    <br>
 <h3>What is your favorite kind of taco?</h3>
  <p><input v-model="tacos1" /></p>
  <p v-once>{{ tacos1 }}</p>
  <span v-pre>This is good if I need to show the mustache view of {{ tacos1 }}</span>
  <pre>{{ $data }}</pre>
<br>

  <button class="inc" @click="counter > 0 ? counter -= 1 : 0">-</button>
      <span class="quant-text">Quantity: {{ counter }}</span>
      <button class="inc" @click.once="counter += 1">+</button>
   
    <button class="submit" @click.="">Submit</button>
  <br>
    <h3>What is your favorite kind of taco?</h3>
  <p v-html="tacos2"></p>

  <h3>What is your favorite kind of taco?</h3>
  <p v-text="tacos1"></p>
  <p>{{ tacos1 }}</p>
  <p><input v-model="tacos1" /></p>
</div>


</template>

<script>


export default {
  name:'App',
  data() {
    return {
    items: [
        'thingie',
        'another thingie',
        'lots of stuff',
        'yadda yadda'
      ],
      message: 'This is a good place to type things.',
      checkedNames: [],
       options: [
        { value: 'John' },
        { value: 'Paul' },
        { value: 'George' },
        { value: 'Ringo' }
      ],
      tacos: '',
       tacos1: 'I like Al Pastor tacos',
       counter: 0,
      tacos2: `I like <a href="http://www.epicurious.com/recipes/food/views/tacos-al-pastor-242132" target="_blank">Al Pastor</a> tacos`

    }
  }
}

</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
