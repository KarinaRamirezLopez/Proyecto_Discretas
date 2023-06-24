Ejercicio 2 "Sherlock  And  Divisors" 

Descripción del problema:
Watson le da un número entero n a Sherlock y le pregunta: ¿Cuál es el número de divisores de n que son divisibles por 2?.

Formate de entrada:
La primera línea contiene T, el número de casos de prueba. A esto le siguen T líneas, cada una de las cuales contiene un número entero N .

Formato de salida:
Para cada caso de prueba, imprima la respuesta requerida en una línea.

Salución del problema:
Se añade una función que lo que hace es tomar el numero "n", que en este ejemplo es 2, donde nos va a dejar ingresar dos enteros, donde la función que definimos va a verficar a traves de un bucle con tres condiciones si nuestros numeros enteros tienen divisores de 2, en el ejemplo que nos da la plataforma se nos dice que tenemos dos enteros 8 y 9, donde 9 tiene 3 divisores, en donde ninguno de ellos es divisible entre dos, y en el caso de 8 tenemos 4 divisores en donde solo 3 de ellos son divisibles entre 2, de tal manera que la salida que nos dara en nuestro archivo seran 0 y 3, esto porque 9 no tiene divisores que se dividan entre 2, y 3 por que 8 tiene 4 divisores en donde solo tres se pueden dividir entre dos.

Instrucciones de ejecución:
1. Compilar programa con "gcc sherlock.c"
2. Para revisar el resultado revisar el archivo generado en el directorio "OUTPUT_PATH"

Nombrado de variables:
Las nuevas variables agregadas en la función son:

int n
int count
int sqrtN
int x
int y

Explicación del codigo:

int divisors(int n) {
    int count = 0;              // Variable para contar la cantidad de divisores pares
    int sqrtN = sqrt(n);        // Calcula la raíz cuadrada de n para reducir el rango 
                                // del bucle for

    for (int x = 1; x <= sqrtN; x++) {
        if (n % x == 0) {       // Comprueba si x es un divisor de n
            if (x % 2 == 0) {   // Comprueba si x es par
                count++;        // Incrementa el contador de divisores pares
            }

            int y = n / x;                  // Calcula el otro divisor, e
            if (y != x && y % 2 == 0) {     // Incrementa el contador si y es diferente 
                count++;                    // de x y es par
            }
        }
    }

    return count;               // Devuelve la cantidad de divisores pares
}
