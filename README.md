A partir de la versión 3.8 de Python se añadió un nuevo operador denominado morsa (:= el nombre proviene de su similitud con los ojos y colmillos).

La característica de este operador es que nos permite la asignación de valores a una variable en una expresión, es decir, nos permite asignar el valor y devolverlo en la misma expresión, pudiendo reducir las líneas de código y mejorando legibilidad.

Con algún ejemplo se entiende mejor su uso:

Pongamos que queremos que un usuario introduzca números en una lista a través de un input, y que para dejar de incluirlos tenga que presionar el 0. Podríamos hacerlo así:

lista = []

while True:
    numero = int(input('Añade número: '))
    if numero == 0:
        break
    lista.append(numero)
    
print(lista)
Gracias al operador morsa, podremos reducir el código a lo siguiente:

lista = []

while (numero := int(input('Añade número: '))) != 0:
    lista.append(numero)
    
print(lista)
En ambos casos para las siguientes entradas de datos 4, 3, 6, 2, 9, 0 nos devolverá [4, 3, 6, 2, 9], pero podemos ver que hemos reducido considerablemente el código, ya que podemos asignar el valor del input a la variable numero y comprobar que es distinta de 0 en la misma línea.

Con el operador morsa la asignación a la variable debe estar metida entre paréntesis ya que aunque no dará error, puede no devolver el resultado esperado, por ejemplo el código siguiente:

lista = []

while numero := int(input('Añade número: ')) != 0:
    lista.append(numero)

print(lista)