# 1.- Variables en Java

## 1.1.- Definición y Declaración

Una variable en Java es un espacio de memoria asignado para almacenar datos que pueden modificarse durante la ejecución del programa. Se asocia con un tipo de dato específico que determina el tipo y tamaño de valor que puede contener. La declaración de una variable sigue la sintaxis:

```java
tipo nombreVariable;
```

Ejemplo:

```java
int edad;
String nombre;
```

## 1.2.- Inicialización de Variables

Una variable se inicializa asignando un valor, que se puede realizar en la declaración o posteriormente.

```java
int edad = 30; // Declaración e inicialización
String nombre; // Declaración
nombre = "Juan"; // Inicialización posterior
```

# 2.- Expresiones en Java

## 2.1.- Definición

Una expresión en Java es una combinación de variables, operadores y llamadas a métodos que se evalúa para producir un valor. Puede ser tan simple como una variable individual o más compleja, involucrando múltiples operaciones.

Ejemplo:

```java
int suma = 10 + 5; // Expresión aritmética
boolean esMayorDeEdad = edad >= 18; // Expresión booleana
```

## 2.2.- Tipos de Expresiones

Las expresiones pueden ser aritméticas, lógicas, relacionales, entre otras, y se utilizan en estructuras de control, asignaciones, etc.

# 3.- Tipos de Datos Primitivos y Clases Envolventes

## 3.1.- Tipos Primitivos

Java tiene 8 tipos de datos primitivos, que son tipos básicos y no son objetos:

- `byte`: Entero de 8 bits.
- `short`: Entero de 16 bits.
- `int`: Entero de 32 bits.
- `long`: Entero de 64 bits.
- `float`: Número de punto flotante de 32 bits.
- `double`: Número de punto flotante de 64 bits.
- `char`: Carácter Unicode de 16 bits.
- `boolean`: Valores lógicos `true` o `false`.

Ejemplo:

```java
int numero = 100;
double salario = 2500.30;
char letra = 'A';
boolean esValido = true;
```

## 3.2.- Clases Envolventes

Las clases envolventes o "Wrapper classes" permiten trabajar con tipos primitivos como si fueran objetos. Cada tipo primitivo tiene una clase envolvente correspondiente:

- `Integer` para `int`
- `Long` para `long`
- `Float` para `float`
- `Double` para `double`
- `Character` para `char`
- `Boolean` para `boolean`
- `Byte` para `byte`
- `Short` para `short`

Estas clases proporcionan métodos útiles para manipulaciones como la conversión entre tipos, comparaciones, etc.

Ejemplo:

```java
Integer numeroEntero = new Integer(10); // Forma tradicional
Integer numeroAuto = 20; // Autoboxing

int numPrimitivo = numeroEntero.intValue(); // Unboxing
```

# 4.- Tipos de Datos Primitivos: byte, short y long en Java

## 4.1 byte

### Descripción

El `byte` es un tipo de dato entero de 8 bits con signo. Se utiliza para ahorrar memoria en grandes arrays, siendo particularmente útil en contextos donde la memoria es una preocupación importante.

### Rango

El rango de un `byte` va de -128 a 127.

### Ejemplos de Uso

```java
byte edad = 30;
byte nivel = -5;
```

### Aplicaciones Prácticas

Ideal para el procesamiento de streams de datos y en situaciones donde se manejan datos a nivel de byte.

## 4.2 short

### Descripción

El tipo `short` es un entero de 16 bits con signo. Similar al `byte`, se usa para ahorrar memoria, pero ofrece un rango más amplio que el `byte`.

### Rango

El rango de un `short` es de -32,768 a 32,767.

### Ejemplos de Uso

```java
short temperatura = 120;
short capacidad = -32000;
```

### Aplicaciones Prácticas

Utilizado cuando se necesita más rango que el ofrecido por `byte`, pero menos que un `int`.

## 4.3 long

### Descripción

El `long` es un tipo de dato entero de 64 bits con signo. Se usa cuando los valores exceden el rango de un `int`.

### Rango

El rango de un `long` es de aproximadamente -9.2 quintillones a 9.2 quintillones.

### Ejemplos de Uso

```java
long poblacionMundial = 7800000000L;
long distanciaALasEstrellas = 9460730472580800L;
```

### Aplicaciones Prácticas

Esencial para números extremadamente grandes, como identificadores únicos, cálculos poblacionales o medidas astronómicas.

### Nota sobre Literales

Para literales `long`, se utiliza el sufijo `L` para indicar su tipo.

```java
long ejemploLong = 123456789L;
```

# Tema 5: Casting Primitivo en Java

## 5.1 Definición de Casting Primitivo

El casting primitivo en Java se refiere a la conversión de un tipo de dato primitivo a otro. Esto es necesario cuando se quiere asignar un valor de un tipo a una variable de otro tipo. El casting puede ser implícito o explícito.

## 5.2 Tipos de Casting Primitivo

### 5.2.1 Casting Implícito (Widening Casting)

El casting implícito ocurre cuando se asigna un valor de un tipo de dato más pequeño a un tipo de dato más grande. Java realiza esta conversión automáticamente, ya que no hay riesgo de pérdida de información.

#### Ejemplo de Casting Implícito

```java
int miInt = 100;
double miDouble = miInt;  // Aquí se realiza un casting implícito de int a double
```

### 5.2.2 Casting Explícito (Narrowing Casting)

El casting explícito es necesario cuando se asigna un valor de un tipo de dato más grande a un tipo de dato más pequeño. Esto se debe hacer manualmente y con cuidado, ya que puede conllevar a la pérdida de información.

#### Ejemplo de Casting Explícito

```java
double miDouble = 9.78;
int miInt = (int) miDouble;  // Casting explícito de double a int
```

## 5.3 Precauciones en el Casting Primitivo

### 5.3.1 Pérdida de Información

Al realizar casting explícito (narrowing), es importante ser consciente de la posible pérdida de información, especialmente cuando se convierte de un tipo con mayor capacidad a uno con menor capacidad (por ejemplo, de `double` a `int`).

### 5.3.2 Precisión Numérica

En el caso de números decimales convertidos a enteros, se pierde la parte fraccionaria del número, lo que puede afectar la precisión del valor resultante.

### 5.3.3 Rango de Valores

Es crucial considerar el rango de valores que puede manejar el tipo de destino. Por ejemplo, al convertir un `long` grande a `int`, si el valor de `long` está fuera del rango del `int`, el resultado será una conversión incorrecta.

# Tema 6: Tipos Primitivos Float y Double en Java

## 6.1 Float

### Descripción

El tipo `float` es un tipo de dato primitivo en Java que se utiliza para almacenar números de punto flotante (números con decimales) con precisión simple. Utiliza 32 bits de almacenamiento.

### Rango y Precisión

- Rango aproximado: 3.4e−038 a 3.4e+038.
- Precisión: hasta 7 dígitos decimales.

### Ejemplo de Uso

```java
float tasaDeInteres = 6.75f;
float temperatura = 36.6f;
```

### Uso del Sufijo 'f'

Es necesario usar el sufijo `f` o `F` al asignar un literal de punto flotante a una variable `float`, ya que los literales decimales son tratados como `double` por defecto en Java.

```java
float pi = 3.14f; // Uso correcto del sufijo 'f'
```

### Aplicaciones

`float` es útil en contextos donde se requiere una gran cantidad de operaciones matemáticas pero no se necesita una precisión extremadamente alta, como en gráficos por computadora o ciertas aplicaciones científicas.

## 6.2 Double

### Descripción

El tipo `double` es un tipo de dato primitivo utilizado para números de punto flotante con precisión doble. Utiliza 64 bits de almacenamiento, lo que permite una mayor precisión y rango que `float`.

### Rango y Precisión

- Rango aproximado: 1.7e−308 a 1.7e+308.
- Precisión: hasta 15 dígitos decimales.

### Ejemplo de Uso

```java
double salario = 123456.789;
double distancia = 98765.4321;
```

### Aplicaciones

`double` es el tipo de punto flotante predeterminado en Java y es ampliamente utilizado en cálculos matemáticos precisos, finanzas, ciencias, y donde la precisión es crucial.

## 6.3 Consideraciones de Uso

### 6.3.1 Precisión

- `double` es más preciso que `float` y es generalmente la mejor opción si no hay restricciones de memoria o rendimiento.
- En cálculos científicos y matemáticos de alta precisión, se prefiere `double`.

### 6.3.2 Rendimiento

- El uso de `float` puede ser más eficiente en términos de memoria cuando se manejan grandes arrays de números.
- Sin embargo, en la mayoría de los procesadores modernos, los cálculos con `double` pueden ser tan rápidos como con `float`.

### 6.3.3 Elección entre Float y Double

- Prefiera `double` para la mayoría de los cálculos para evitar problemas de precisión.
- Utilice `float` cuando necesite ahorrar memoria y la precisión no sea la principal preocupación.
