<template>
  <v-container class="fill-height">
    <v-responsive class="align-center text-center fill-height">
      <div class="text-body-2 font-weight-light mb-n1">Write Word</div>
    </v-responsive>
  </v-container>
</template>

<script setup>

  const word = 'Reviver';

  testIsPolindromo(word);

  function testIsPolindromo(word) {

      var result = true;
      
      const chars = word.length;
      for(var i=0;i<chars;i++){
        if(!charIsEqualInPosition(word, word[i], i)){
          result = false;
        }
      }

      const message = result ? 'It\'s OK' : 'Failed!';
      console.log(message);

  }

  function charIsEqualInPosition(word, char, position){

    char    = char.toLowerCase();
    word  = word.toLowerCase();

    // invert string
    var newWord = '';
    const chars = word.length;
    
    for(var i=(chars-1);i>=0;i--){
      newWord += word[i];
    }

    return (newWord[position]==char);

  }

</script>

<style scoped>
  .input{
    margin-top: 10px;
    border: 1px solid #ddd;
  }
</style>