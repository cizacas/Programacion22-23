# UNIDAD 4.  ESTRUCTURAS DE ALMACENAMIENTO ESTÁTICAS. ARRAYS

## ÍNDICE

## INTRODUCCIÓN

Hasta ahora conocemos los tipos de datos simples. Con ellos no podemos gestionar muchos datos a la vez.
**Pregunta**:
¿Cómo tendríamos que hacer ahora si queremos almacenar la nota de 30 alumnos de clase?
- En la mayoría de los lenguajes se pueden agrupar variables del mismo tipo en una misma estructura conocida como **array**.
- **Los arrays** son una **colección de datos del mismo tipo** al que se le pone un nombre (por ejemplo notas). Para acceder a un dato individual de la colección hay que utilizar su posición. La posición es un número entero, normalmente se le llama **índice**
- por ejemplo notas[4] es el nombre que recibe el quinto elemento de la sucesión de notas.
- Hay que tener en cuenta que en los arrays el primer elemento tiene como índice el número cero.
- En Java los arrays son **OBJETOS**.

si tenemos el siguiente ejemplo 
![array de notas](img/arraynotas.png)
¿Cómo accederemos al valor 4?
¿Qué obtendremos si hacemos nota[8]?

## ARRAYS UNIDIMENSIONALES

### Declaración
Para declarar un array en Java podremos hacerlo del siguiente modo:
```java
	tipo[] nombre;
```
Ejemplo
```java
	 double[] notas;
```
Esta declaración indica para qué servirá el array, pero no reserva espacio en la RAM al no saberse todavía el tamaño del mismo. 

Tras la declaración del array, se tiene que inicializar. Eso lo realiza el **operador new**, que es el que realmente crea el array indicando un tamaño.
Cuando se usa new es cuando se reserva el espacio necesario en memoria. Un array sin inicializar no se puede utilizar en el código.
```java
	double[] notas; //Declaración
	notas =  new double[30]; //Se crea el array con 30 valores de tipo double
```
También se puede hacer ambas operaciones en la misma instrucción: 
```java
	double[] notas = new double[30];
```
### Asignación
Los valores del array se asignan utilizando el índice del mismo entre corchetes:
```java
notas[18]=4.45;
```
También se pueden asignar valores al array en la propia declaración: 
```java
double[] notas = {3.0, 5.2, 8, 0.5} //Esto creará un array de 4 elementos
```
Preguntas:
¿Cuánto valdrá notas[1]?
¿Y notas[4]?

Se pueden declarar arrays a cualquier tipo de datos (enteros, booleanos, doubles, ... e incluso objetos como se verá más adelante).

La ventaja de usar arrays es que gracias a un simple bucle for se puede recorrer fácilmente todos los elementos de un array.

### Longitud

Los arrays poseen un método que permite determinar cuánto mide un array; es decir, de cuántos elementos consta. Se trata de length. 
```java
int a[]=new int [17]; 
System.out.println(a.length); //Escribe: 17 
```
Gracias a este método el bucle de recorrido de un array (para cualquier tipo de array) sería: 
```java
	for (int i = 0; i < x.length; i++) 
	{ 
		//x[i] tendrá el valor de cada posición del array
	}
```
Ejemplo: Realizar un programa en Java que cree un array de 10 notas y calcule la nota media de ellas.
```java
double[] notas = {5, 4.3, 2.7, 6, 7.9, 9.8, 4.9, 7.5, 8.4, 3};
double suma=0; 
for (int i=0;i<notas.length;i++){ 
        suma+=notas[i]; 
    }
double media=suma/notas.length; 
System.out.println("La media de las notas es " + media);
```

