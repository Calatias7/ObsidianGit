```js
function parseAsig(input) {
    let index = 0;
    let tokens = input.match(/[a-zA-Z]|[0-9]+|=|[\+\-\*\/\(\)]/g); // Tokenización ajustada
    
    let errorFound = false;
    let errorMessage = "";
    
    function currentToken() {
        return tokens[index];
    }

  

    function nextToken() {
        index++;
    }

  

    // Regla de producción <sent_asig> ::= <var> = <expresion>

    function sentAsig() {
        if (errorFound) return false;
        if (varToken()) {
            nextToken();
            if (currentToken() === "=") {
                nextToken();
                if (expresion()) {
                    return true;
                } else {

                    showError("Error: No se cumple la regla <expresion> en <sent_asig>");

                    return false;
                }
            } else {

                showError("Error: Se esperaba '=' en la producción <sent_asig>");

                return false;
            }
        } else {

            showError("Error: Se esperaba una variable en minúsculas (a-z) en la producción <sent_asig>");
            return false;
        }

    }
    // Regla de producción <expresion> ::= <expresion> + <termino> | <expresion> - <termino> | <termino>

    function expresion() {
        if (errorFound) return false;
        if (termino()) {
            while (currentToken() === "+" || currentToken() === "-" || currentToken() === "*" || currentToken() === "/") {
                let operator = currentToken();
                nextToken();
                if (currentToken() === "+" || currentToken() === "-" || currentToken() === "*" || currentToken() === "/") {
                    showError(`Error: No se permiten múltiples operadores seguidos ('${operator}${currentToken()}')`);
                    return false;
                }

                if (!termino()) {
                    showError(`Error: Se esperaba un término después del operador '${operator}' en <expresion>`);
                    return false;
                }
            }
            return true;
        }
    }
    // Regla de producción <termino> ::= <termino> * <factor> | <termino> / <factor> | <factor>

    function termino() {
        if (errorFound) return false;
        if (factor()) {
            while (currentToken() === "*" || currentToken() === "/") {
                let operator = currentToken();
                nextToken();
                if (!factor()) {
                    showError(`Error: Se esperaba un factor después del operador '${operator}' en <termino>`);
                    return false;
                }
            }
            return true;
        }
    }
    // Regla de producción <factor> ::= ( <expresion> ) | <var> | <num>

    function factor() {
        if (errorFound) return false;
        if (currentToken() === "(") {
            nextToken();
            if (!expresion()) {
                showError("Error: Se esperaba una expresión dentro de los paréntesis en <factor>");
                return false;
            }
            if (currentToken() !== ")") {
                showError("Error: Se esperaba ')' en la producción <factor>");
                return false;
            }
            nextToken();
            return true
        } else if (varToken() || numToken()) {
            nextToken();
            return true;
        }
    }
    // Regla de producción <var> ::= a | b | c | ... | z (solo minúsculas)

    function varToken() {
        if (/^[A-Z]$/.test(currentToken())) {
            showError("Error: No se permiten letras mayúsculas según la gramática");
            return false;
        }
        return /^[a-z]$/.test(currentToken());
    }
    // Regla de producción <num> ::= 0 | 1 | ... | 9 (sin permitir negativos)
    function numToken() {
        if (/^-/.test(currentToken())) { // Detecta números negativos
            showError("Error: No se permiten números negativos según la gramática");
            return false;
        }
        return /^[0-9]+$/.test(currentToken());
    }
    // Manejo del mensaje de error
    function showError(message) {
        if (!errorFound) {
            errorMessage = message;
            errorFound = true;
        }
    }

  

    // Análisis inicial
    if (sentAsig() && index === tokens.length && !errorFound) {
        console.log("La cadena es válida según la gramática.");
    } else {
        if (errorFound) {
            console.log(errorMessage);
        } else {
            console.log("Error: La cadena no es válida según la gramática.");
        }
    }
}
// Ejemplo de uso:

parseAsig("A = 14 / 1");
```