## Identificador de cadenas
```js
// Definicion de las palabras reservadas, operadores y expresion regular para identificadores y constantes
const reservedWords = ['if', 'else', 'for', 'while', 'return', 'function', 'var', 'let', 'const', 'then'];
const operators = ['+','(', ')', '-', '*', '/', '=', '==', '===', '!=','!==', '<', '>', '<=', '>=', '&&', '||', '++', '--', '"'];
const identifierRegex = /^[a-zA-Z_$][a-zA-Z_$0-9]*$/;
const constantRegex = /^[0-9]+(\.[0-9]+)?$/;

// Función para clasificar cada línea de código
function classifyCode(code) {
    const lines = code.split('\n');
    const classification = [];

    lines.forEach((line, lineIndex) => {
        const tokens = line.trim().split(/\s+/);
        const lineClassification = {
            lineNumber: lineIndex + 1,
            identifiers: [],
            operators: [],
            constants: [],
            reservedWords: []
        };

        tokens.forEach(token => {
            if (reservedWords.includes(token)) {
             lineClassification.reservedWords.push(token);
            } else if (operators.includes(token)) {
                lineClassification.operators.push(token);
            } else if (identifierRegex.test(token)) {
                lineClassification.identifiers.push(token);
            } else if (constantRegex.test(token)) {
                lineClassification.constants.push(token);
            }
        });

        classification.push(lineClassification);
    });

    return classification;
}

// Ejemplo de uso
const code = `If a > t then
Msg " Bienvenidos "`;

// Clasificar el código y mostrar el resultado
const result = classifyCode(code);
console.log(JSON.stringify(result, null, 2));
```

