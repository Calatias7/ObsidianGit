```js
function countCharacters(phrase){
    const characterCount ={};
    for (let i=0;i< phrase.length; i++){
        const character = phrase[i];
        if (characterCount[character]){
            characterCount[character]++;
        }else{
            characterCount[character]=1;
        }
    }
    return characterCount;
}
  
const phrase = "La vida es como un lápiz que seguro se acabará. Pero dejará la hermosa escritura de la vida";

const result = countCharacters(phrase);  
console.log("caracteres contados:");
for (const character in result){
    console.log(`${character}=${result[character]}`);
}
```