### Conexión en la protoboard:

1. **Alimentación:**
    
    - Coloca la batería o fuente de alimentación en la protoboard.
    - Conecta el terminal positivo de la batería al bus positivo de la protoboard y el negativo al bus negativo.
2. **Circuito Integrado 7447:**
    
    - Inserta el CI 7447 en la protoboard, asegurándote de que cada pin esté en diferentes filas de la protoboard.
    - Conecta los pines de alimentación:
        - Pin 16 del 7447 a la línea positiva de la protoboard.
        - Pin 8 del 7447 a la línea negativa de la protoboard.
3. **Display de 7 segmentos:**
    
    - Coloca el display en la protoboard de manera que cada uno de los pines esté en una fila diferente.
    - conecta el pin 15(f) del 7447 al pin9(f) del display ánodo
    - conecta el pin 14(g) del 7447 al pin10(g) del display ánodo
    - conecta el pin 13(a)  del 7447 al pin7(a) del display ánodo
    - conecta el pin 12(b)del 7447 al pin8(b) del display ánodo
    - conecta el pin 11(c) del 7447 al pin4(c) del display ánodo
    - conecta el pin 10(d) del 7447 al pin2(d) del display ánodo
    - conecta el pin 9(e) del 7447  al pin1(e) del display ánodo
    - conecta el pin8(com) del display ánodo a una resistencia 4.6k al positivo de la protoboard
    - conecta el pin3(com) del display ánodo a una resistencia 4.6k al positivo de la protoboard
4. **Conexión del switch:**
    - Conecta una terminal de cada botón a la línea positiva de la protoboard(en mi caso use el 1, 3, 5, 7).
    - La otra terminal de cada botón va a las resistencias de 1kΩ que se conectarán a negativo y entre ellos conecta a los pines A, B, C y D del 7447.
    - boton1 se conecta al pin7(A) del 7447 
    - boton3 se conecta al pin1(B) del 7447
    - boton5 se conecta al pin2(C) del 7447
    - boton7 se conecta al pin6(D) del 7447
5. **Conexión de señales de control:**
    - Conecta los pines restantes del CI 7447  
        - El pin 3 (LT) , el pin 4(BI/RBO) y El pin 5 (RBI) se conectan a la línea positiva de la protoboard.
![[Pasted image 20240830135120.png]]
![[Pasted image 20240830135135.png|600]]


