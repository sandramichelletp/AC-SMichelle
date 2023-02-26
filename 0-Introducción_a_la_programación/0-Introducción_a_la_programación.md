# ¿Qué es un programa?

En este curso, emplearemos la palabra **programa** para referirnos a un _programa computacional_, el cual podemos definir de forma general como un _conjunto de instrucciones que una computadora puede ejecutar o, en su defecto, interpretar_.

**Pregunta** Considera los siguientes enunciados.
1. ''Calcula cuántos átomos hay en el universo.'' 
1. ''Dime cuáles números enteros son mayores que uno y menores que cien.''
1. ''Enumera todos los enteros positivos de menor a mayor.''
1. ''Divide uno entre cero.''

¿Cuál(es) enunciado(s) califica(n) como un programa y cuál(es) no, de acuerdo a la definición general anterior?

A la tarea de crear programas computacionales que cumplan una función específica se le conoce como **programación**.

## Paradigmas de la programación

Existen muchas formas distintas de pensar la programación, que colectivamente se conocen como los **paradigmas de la programación**. Estos pueden tener diferentes enfoques que resulten ventajosos (o desventajosos) para distintos usos, y no necesariamente se excluyen entre sí. Algunos ejemplos de paradigmas son:
* imperativo,
* declarativo,
* dinámico,
* concurrente,
* programación cuántica.

En este curso, nos enfocaremos en el paradigma **imperativo**.

**Nota** Existen algunos paradigmas que pueden implementarse como variaciones más específicas de otros ya existentes, por lo que se les considera también como _subparadigmas_. Por ejemplo, el paradigma de la **programación orientada a objetos** (OOP, por sus siglas en inglés) usualmente se considera como un subparadigma del paradigma imperativo, mientras que el paradigma de la programación funcional se considera un subparadigma del paradigma declarativo. Al final de este curso veremos una breve introducción a la programación orientada a objetos, puesto que es uno de los paradigmas más ampliamente utilizados actualmente. 

### Paradigma imperativo de la programación

Dentro del **paradigma imperativo de la programación**, definiremos a un programa como una _**serie** de instrucciones que una computadora puede ejecutar o, en su defecto, interpretar_.

Observemos que en nuestra nueva definición de _programa_ -dentro del paradigma imperativo- hablamos de una _serie_ de instrucciones en vez de un _conjunto_, como en la definición general que habíamos dado previamente. Esto es porque el paradigma **imperativo** de la programación se basa en dar **órdenes estrictas** a la computadora y que ésta las siga al pie de la letra; sin embargo, para lograrlo, no basta con dar instrucciones, sino que éstas deben tener una secuencia clara. Es decir, en el paradigma imperativo le decimos a la computadora _qué_ hacer y _cómo_ hacerlo, **removiendo toda ambigüedad** en el proceso.

En este sentido, el enunciado 2 visto anteriormente no puede ser considerado como un programa, pues hay muchísimas maneras de ''decir cuáles números enteros son mayores que uno y menores que cien'', y el enunciado _no_ remueve esta ambigüedad especificando de qué forma debería hacerse. En cambio, los enunciados 3 y 4 sí son considerados programas, pues el 3 pide enumerar varios elementos pero especifica en qué orden hacerlo, y el 4 se reduce a una sola instrucción, por lo que no existe más que un orden posible en ese caso. Intentemos ahora ejecutar los enunciados 3 y 4 en las dos celdas siguientes, dando clic en algún lugar de la celda y presionando la combinación de teclas `Ctrl+Enter` por cada celda.


```julia
Enumera todos los números positivos de menor a mayor.
```


```julia
Divide uno entre cero.
```

Observemos que en ninguno de los dos casos anteriores obtenemos el resultado que buscamos. Esto se debe a que la computadora no puede interpretar estos enunciados de la forma en que los escribimos; por ende, estrictamente hablando, los enunciados 3 y 4 _tampoco_ contarían como programas (en el paradigma imperativo).

## Código y pseudocódigo

Para hacer más clara esta distinción, nos referiremos a un programa que puede ser ejecutado o al menos interpretado por una computadora, de acuerdo a la última definición que vimos, como un **código**. En cambio, a una serie de instrucciones que _podría_ ser ejecutada/interpretada por una computadora si se transformara en código pero que, _en su forma actual, sólo puede ser interpretada por seres humanos_ se le conoce como **pseudocódigo**.

Por ejemplo, una forma de transformar el enunciado 4 a código es la siguiente:


```julia
1/0  # Divide uno entre cero.
```

En cambio, si cambiamos el enunciado 2 a "Dime cuáles números enteros son mayores que uno y menores que cien, ordenándolos de menor a mayor." obtenemos un programa que se puede implementar en código como sigue:


```julia
#Imprime la frase "Los números enteros mayores que uno y menores que cien, ordenados de menor a mayor, son:" y crea una línea nueva.
println("Los números enteros mayores que uno y menores que cien, ordenados de menor a mayor, son: ")

for i in -100:100           #Para una variable 'i' que va de -100 a 100,
    if (i > 1) & (i < 100)  #si la variable es mayor que uno y menor que cien,
        println(i)          #imprime su valor y crea una línea nueva.
    end
end
```

Sin embargo, para poder **transformar pseudocódigo en código** necesitamos un **lenguaje de programación**, el cual tiene una **sintáxis** y una **semántica** propia. Más aún, para poder saber si la computadora puede ejecutar o al menos interpretar lo que le escribimos, debemos aprender a leer **mensajes de error**. Por ello, ¡estos son los temas que discutiremos en el siguiente _notebook_!

**Nota** En el código pasado le ordenamos a la computadora considerar números enteros sólo entre -100 y 100. Esto es porque, dado que el conjunto $\mathbb{Z}$ es infinito, considerar a _todos_ los números enteros le tomaría a la computadora una cantidad infinita de tiempo y de memoria.

#### Ejercicio

Completa la siguiente tabla y argumenta tus respuestas debajo. (Nota: Recuerda que debes hacer doble clic en esta celda para editarla, y que en este curso siempre asumiremos que estamos trabajando dentro del paradigma imperativo de la programación.)

|Enunciado|1|2|3|4|
|-|-|-|-|-|
|¿Es código?|No|No|No|No|
|¿Es pseudocódigo?|No|Sí|No|Sí|

Definimos como código al lenguaje de programación dotado de instrucciones estrictamente claras y concisas, es decir, removiendo toda ambiguedad en el lenguaje. Por su parte, éste requiere de cierta sintáxis y semántica propia. Conocemos como pseudocódigo a la serie de instrucciones que se le dan a una computadora pero que antes de que las pueda interpretar necesita de un lenguaje de programación, ya que por lo mientras, solo podrá ser interpretada por humanos dentro del paradigma imperativo. Basándonos en ello, el primer enunciado no lo podemos considerar como código puesto que la computadora no tiene noción de su entorno y por tanto no sabe interpretarlo. Por su parte, el segundo enunciado tampoco lo podemos considerar como código ya que hay diversas formas de imprimir el resultado. El tercer enunciado incluye a todos los números positivos es decir infinitos números, por tanto la computadora no podría acabar mientras que el cuarto enunciado es pseudocódigo pero no código, puesto que se puede pasar a código pero en la forma en la que está escrita solo la pueden interpretar humanos, requiere de lenguaje de programación tal como 1/0.

## Recursos complementarios
* Página de Wikipedia sobre [paradigmas de la programación](https://en.wikipedia.org/wiki/Programming_paradigm).
