# Curso Base de Ruby

* [Proyecto de Ruby](#proyecto-de-ruby)
* [Combados básicos](#combados-básicos)
* [Variables](#variables)
* [Prints Code](#prints-code)
* [Comentarios](#comentarios)
* [Single Quotes vs Double Quotes](#single-quotes-vs-double-quotes)
* [Operadores Aritméticos](#operadores-aritméticos)
* [Operadores Comparativos](#operadores-comparativos)
* [Operadores Lógicos](#operadores-lógicos)
* [Operador Splat](#operador-splat)
* [Condicionales](#condicionales)
* [Case](#case)
* [Array](#array)
* [Operaciones con Array](#operaciones-con-array)
* [Rangos](#rangos)
* [Iterardores](#iterardores)
    * [For and Each](#for-and-each)
    * [While and Until](#while-and-until)
    * [Time](#time)   
    * [Upto](#upto)   
    * [Downto](#downto)   
* [Matriz](#matriz)
* [Cadenas](#cadenas)
* [Hashes](#hashes)
* [Simbolos](#simbolos)
* [I/O](#io)
* [Clases](#clases)
    * [Clases.constructor](#clasesconstructor)

* [Métodos](#métodos)
    * [Definir un Método](#definir-un-método)
    * [String.class](#stringclass)
    * [String.upcase](#stringupcase)
    * [String.downcase](#stringdowncase)
    * [String.capitalize](#stringcapitalize)    
    * [String.length](#stringlength)
    * [String.reverse](#stringreverse)
    * [String.to_i](#stringto_i)
    * [String.to_f](#stringto_f)
    * [String.to_a](#stringto_a)
    * [String.eql](#stringeql)
    * [String.equal](#stringequal)
    * [String.gsub](#stringgsub)
    * [String.split](#stringsplit)
    




## Proyecto de Ruby

## Combados básicos
*   **`ruby app-name`:** Permite la ejecución de un archivo .rb


## Variables
Para ruby no hay necesidad de declarar una variable basta con nombrarla y asignarle un valor y el interprete deduce que tipo de variable es
```rb
nombre = "Fernando" #string
edad = 23 #integer
precio = 20.5 #float
is_strange = true #boolear
```
Las variables en ruby se escribo con la modalidad `snake_case`, es decir "palabras en letras minúsculas separadas por guión bajo"
```rb
first_name
second_name
last_name
full_name
```

## Prints Code
Para imprimir por consola se puede usar el comando `puts` o `print`, la diferencia de una con la otra se basa en que print no genera un salto de linea al imprimir a diferencia de puts
```rb
print "Fernando" 
print "Antúnez" 
# El resultante FernandoAntúnez
puts "Fernando" 
puts "Antúnez" 
# El resultante Fernando \nAntúnez \n
```


## Comentarios
Para comentar en el código existen 2 manera

*   **`#`:**  comentarios de una sola línea
*   **`=begin   +    =end`:** comentarios de varias líneas. 

## Operadores Aritméticos
En ruby podemos usar operadores aritméticos para evaluar expresiones matemáticas. Los operadores aritméticos de Ruby más comunes son suma (+), resta (-), división (/), multiplicación (*), exponenciación (**) y módulo (%).

```rb
puts 1+3 # Suma: output 4 
puts 1-2 # Resta: output -1 
puts 9/3 # Division: output 3 
puts 2*3 # Multiplicación: output 6 
puts 2**3 # Exponenciación: output 8 
puts 16%9 # Modulo: output 7 
```

Es importante saber que el tipo de dato de inserción guarda mucha relación con el tipo de dato de salida
```rb
puts 10 / 3 # Dara 3 ya que se usan valores enteros
puts 10.0 / 3.0 # Dara 3.33333333 ya que se usan valores tipo float
```

En ruby los número no son primitivos sino por su parte son considerados objetos permitiendo ejecutar métodos sin necesidad de incluir en otro tipo de datos
```rb
puts 10.to_f # Transforma a tipo float, daría 10.0
puts 12.2312.to_i # Transforma a tipo int, daría 12.2
puts -10.abs # Retorna el valor absoluto, daría 10
```

## Single Quotes vs Double Quotes
La diferencia principal entre usar comillas simples `''` y comillas dobles `""` al momento de usar en Ruby, radica que con comillas simples no se puede usar interpolación (disponer de una expresión dentro del String para que el interprete de Ruby la procese para obtener el String definitivo.) de los elementos

```rb
nombre = "juan"
edad = 24
puts "#{nombre} tiene #{edad} años" # juan tiene 24 años
puts '#{nombre} tiene #{edad} años' # #{nombre} tiene #{edad} años
```

## Operadores Comparativos
Existen diversos tipos de operadores para comparar
```rb
a>b # Evalua 'a' mayor que 'b'
a<b # Evalua 'a' menor que 'b'
a>=b # Evalua 'a' mayor igual que 'b'
a<=b # Evalua 'a' menor igual que 'b'
a<=>b # Compara 'a' contra 'b', si son iguales retorna 0, si el primero es mayor retorna 1, si el segundo es mayor retorna -1
a==b # Evalua 'a' es igual que 'b'
a.eql?(b) # Evalua si 'a' es igual tanto resultado como en tipo que 'b'
a.equal?(b) # Evalua si 'a' es igual tanto resultado como en tipo que 'b'
```

## Operadores Lógicos
Existen diversos tipos de operadores lógicos
```rb
a&&b # Evalua 'a' y 'b'
a||b # Evalua 'a' o 'b'
!a # Evalua el inverso de 'a' 
```

## Operador Splat
El operador Splat se usa siempre que no se desee especificar la cantidad de argumentos que se recibirá, se puede identificar ya que se coloca un `*` antes del argumento. Basicamente el operador Splat convertira los parámetros en un Array
```rb
def go(x, *args)
  puts args.inspect
end

go("a", "b", "c")
```
Si deseamos usar hashes debemos colocar dos asteriscos
```rb
def go(**params)
  puts params.inspect
end

go(x: 100, y: 200)
```



## Condicionales
Para el condicional IF - else tenemos
```rb
a = 3
b = 2
if a>b
    puts "Dio a"
elsif a == b
    puts "dio igual"
else
    puts "Dio b"
end

# Otra manera de escribir esto
if a == 0
    play = false
end

# Es así
play = false if a == 0
# o así
play = a != 0

```

El contrario del IF en ruby sería el `unless`, el cual si da falso entra
```rb
unless a>b
    puts "b es mayor"
end
```
El `unless` es equiparable a decir `if !(a)`
Para el operador ternario usaremos la siguiente sintaxis
```rb
user = "Coco"
puts (user == "Uriela" ? "tutor" else "Visitante" end) # Una manera de evaluarla
```

## Case
Es equiparable al switch
```rb
print "Dame tu calificación (1-20): "
calificacion = gets.chomp.to_i

case calificacion
when 10, 9
    puts "Muy Bien"
when 8
    puts "Aún puedes mejorar"
when 7
    puts "Se puede hacer mejor"
else
    "u.u"
end
```
## Array
Como funcionan los arreglos
```rb
arreglo = [3,'perro', true]
arreglo_dos = Array.new(5) # Inicializa un arreglo con 5 posiciones vacias
arreglos = %w[1 40 'a' true] # El %w permite usar arreglos e insertar cada posición con el espacio
arreglos << 'Hola' # Es equiparable a un push
arreglos.push('Hola') # Agrega un push
arreglos.delete_at(2) # Borra la posición 3 del array
arreglos.delete("perro") # Borra todos los perro del array



```

## Operaciones con Array
En ruby el método Array.join() es equiparable a usarse con el `*`

```rb
calificaciones = %w[10 7 8 9 5 6 4]
puts calificaciones.join(",") #output 10,7,8,9,5,6,4
puts calificaciones * "," # output 10,7,8,9,5,6,4
```

Para ordenar podemos usar el método Array.sort() que ordenará de menor a mayor, y luego usamos el método reverse para invertirlo
```rb
calificaciones = [10, 7, 8, 9, 5, 6, 4]
puts calificaciones.sort #output 4,5,6,7,8,9,10
puts calificaciones.sort.reverse #output 10,9,8,7,6,5,4
```

Para buscar un elemento dentro de él usamos el `include?` el cual nos retornará true si encontró o false si no encontró
```rb
calificaciones = [10, 7, 8, 9, 5, 6, 4]
puts calificaciones.include?(7) #output true
puts calificaciones.include?(3) #output false
```

Para devolver el primer elemento dentro de un arreglo usamos `first` y para el ultimo `last`
```rb
calificaciones = [10, 7, 8, 9, 5, 6, 4]
puts calificaciones.first #output 10
puts calificaciones.last #output 4
```

Para devolver un elemento aleatorio del arreglo usamos `sample`
```rb
calificaciones = [10, 7, 8, 9, 5, 6, 4]
puts calificaciones.sample #output random
```
## Rangos
Para un rango de valores usamos `(a..b)` o `(a...b)` donde a y b son variables, y los 2 puntos indican que incluyan el ultimo valor `b` mientras que con los 3 puntos no lo incluyen. Los rangos NO son arreglos

```rb
(1..10).each do |numero|
    print "#{numero},"
end
# output 1,2,3,4,5,6,7,8,9,10,

('a'..'z').each do |letra|
    print "#{letra},"
end
# output a,b,c,d,e,f,g...,z,
```

Si queremos ir en el rango entre una cantidad especifica (de 2 en 2, de 3 en 3, etc) usamos el método step
```rb
(1..10).step(2).each do |numero|
    print "#{numero},"
end
# output 1,3,5,7,9,
```

Si queremos sacar el valor mínimo del rango
```rb
puts (0..20).min # output 0
```

Si queremos sacar el valor máximo del rango
```rb
puts (0..20).min # output 20
```



## Iterardores
Es un método que inernamente construye un ciclo

#### For and Each
El equivalente a un bucle for sería
```rb
calificaciones = %w[10 7 8 9 5 6 4]
suma = 0

# El bucle for estandar
calificaciones.each do |calificacion|
    puts "El valor #{calificacion}"
end

# El También puede escribirse
calificaciones.each { |calificacion|
    puts "El valor #{calificacion}"
}

# El bucle for en una linea
calificaciones.each {|calificacion| puts "El valor #{calificacion}"}

# El bucle for estandar
for num in (1..10)
    puts num
end

# El bucle for con index
calificaciones.each_with_index do |calificacion,position|
    puts "El valor #{calificacion} en la posición #{position}"
end

# Si queremos sacar el promedio
calificaciones.each_with_index do |calificacion,position|
    suma += calificacion.to_i
end
puts "El promedio de tus calificaciones es #{suma.to_f / calificacion.length}"

# Si queremos obviar las siguientes lineas usamos el next
calificaciones.each do |calificacion|
    next if calificacion.to_i % 2 == 0
    puts "El valor #{calificacion}"
end

# Si queremos un loop infinito
num = 1
loop do
    puts num += 1    
end

# Si queremos cortar un for usamos el break
num = 1
loop do
    puts num += 1  
    break  
end
```

#### While and Until

El equivalente a while
```rb
i = 0
# El bucle while estandar
while i<10
    puts i
    i+=1
end
```

El contrario al while sería el `until` y básicamente hasta que la condición no de el valor indicado seguira ejecutandose
```rb
i = 0
# El bucle while estandar
until i== 10
    puts i
    i+=1
end
```
En palabra simple con while ejecutamos mientras la condición sea verdadero mientras con el until ejecutamos mientras la condición sea falsa

El equivalente al do-while
```rb
i = 0
# El bucle do-while estandar
begin
i = gets.chomp.to_i
end while i < 1
```

También aplica con until
```rb
i = 0
# El bucle do-while estandar
begin
i = gets.chomp.to_i
end until i == 1
```

#### Time
Permite ejecutar un ciclo X cantidad de veces sin necesidad obligatoria de una variable
```rb
4.times do
    puts "TIMES: 4" 
end
# Output TIMES: 4 TIMES: 4 TIMES: 4 TIMES: 4
```

Si se desea ejecutar con una variable
```rb
i=0
4.times do |i|
    puts i+=1
end
# Output TIMES: 1 2 3 4
```

En caso de no tener una variable declarada el bucle la inicializa automáticamente en 0
```rb
4.times do |i|
    puts i
end
# Output TIMES: 0 1 2 3
```

#### Upto
Permite ejecutar un ciclo X cantidad de veces iniciando desde una valor en particular y subiendo progresivamente al número que deseamos obtener
```rb
1.upto(4) do
    puts "TIMES: 4" 
end
# Output TIMES: 4 TIMES: 4 TIMES: 4 TIMES: 4
```

Si se desea ejecutar con una variable
```rb
i=0
1.upto(4) do |i|
    puts i+=1
end
# Output TIMES: 1 2 3 4
```

En caso de no tener una variable declarada el bucle la inicializa automáticamente en 0
```rb
1.upto(4) do |i|
    puts i
end
# Output TIMES: 0 1 2 3
```
De manera corta podemos escribirlo
```rb
0.upto(3) {|x| puts("Number: %x" % x)}
# Output Number: 0 Number: 1 Number: 2 Number: 3
```
Es el equivalente a decir
```ts
for (i = 0; i < 10; i++) {
    //syntax       
}
```

#### Downto
Permite ejecutar un ciclo X cantidad de veces iniciando desde una valor en particular y decreciendo progresivamente al número que deseamos obtener
```rb
10.downto(7) do
    puts "TIMES: 4" 
end
# Output TIMES: 4 TIMES: 4 TIMES: 4 TIMES: 4
```

Si se desea ejecutar con una variable
```rb
i=0
10.downto(7) do |i|
    puts i+=1
end
# Output TIMES: 1 2 3 4
```

En caso de no tener una variable declarada el bucle la inicializa automáticamente en el valor inicial del downto
```rb
10.downto(7) do |i|
    puts i
end
# Output TIMES: 10 9 8 7
```
De manera corta podemos escribirlo
```rb
10.downto(7) {|x| puts("Number: %x" % x)}
# Output Number: 10 Number: 9 Number: 8 Number: 7
```
Es el equivalente a decir
```ts
for (i = 10; i > 7; i--) {
    //syntax       
}
```

## Matriz
Para ser una matriz los arreglos internos deben tener la misma cantidad de elementos y todos sus valores deben ser números

```rb
arreglo = [[1,2,3],[1,2,3]]
```

En ruby hay una clase interna que valida un arreglo es una matrix
```rb
require 'matrix'
matriz = Matrix[[1,2,3],[1,2,3]]
puts matriz
#Output Matrix[[1,2,3],[1,2,3]]
```

Existen muchas cosas que podemos hacer con una matriz como sería iterarla
```rb
require 'matrix'
matriz = Matrix[[1,2,3],[5,6,7]]
matriz.each do |i|
    puts 1
end
#Output 1 2 3 5 6 7
```
Usando el each podemos imprimir la diagonal de la matriz
```rb
require 'matrix'
matriz = Matrix[[1,2,3],[5,6,7],[10,6,5]]
matriz.each(:diagonal) do |i|
    puts 1
end
# [
#     1 2 3
#     5 6 7
#    10 6 5
# ]
#Output 1 6 5
```

Usando el each podemos imprimir lo que esta debajo de la diagonal
```rb
require 'matrix'
matriz = Matrix[[1,2,3],[5,6,7],[10,6,5]]
matriz.each(:strict_lower) do |i|
    puts 1
end
# [
#     1 2 3
#     5 6 7
#    10 6 5
# ]
#Output 5 10 6
```

Usando el each podemos imprimir lo que esta arriba de la diagonal
```rb
require 'matrix'
matriz = Matrix[[1,2,3],[5,6,7],[10,6,5]]
matriz.each(:strict_upper) do |i|
    puts 1
end
# [
#     1 2 3
#     5 6 7
#    10 6 5
# ]
#Output 2 3 7
```

Si queremos verificar que una matriz sea cuadrada usamos
```rb
require 'matrix'
matriz = Matrix[[1,2,3],[5,6,7]]
puts matriz.diagonal?
#Error la matriz no es cuadrada

matriz = Matrix[[1,2,3],[5,6,7],[5,6,7]]
puts matriz.diagonal?
#Output false ya que la matriz diagonal posee 0 en el resto de valores distintos a la diagonal

matriz = Matrix[[1,0,0],[0,6,0],[0,0,7]]
puts matriz.diagonal?
#Output true ya que la matriz diagonal posee 0 en el resto de valores distintos a la diagonal
```
## Cadenas
Existen maneras para hacer que una cadena obtenga el resultado de una operación bien sea a través de la concatenación o la interpolación.
Para concatenar basta con agregar el valor `+` 
```rb
nombre = "Fernando"
puts "Hola " + nombre # Retorna 'Hola Fernando'
```
Para la interpolación basta con agregar `#{ variable }` dentro de la cadena
```rb
nombre = "Fernando"
puts "Hola #{nombre}" # Retorna 'Hola Fernando'
```

## Hashes
Un hash no es más que una colección de datos en donde cada valor está asociado a una llave. `{key => value}` o si usamos simbolos `{key: value}`
```rb
tutor = {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
puts tutor
# Output {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
```
Podemos crear un hash usando
```rb
tutor = Hash.new
puts tutor
# Output {}
```

Podemos asignar un valor por defecto a nuestro hash de modo que si se busca un key que no exista arroje dicho valor 
```rb
h = Hash.new("nothing here")
 
puts h
# {}
 
puts h["kitty"]
# nothing here
```
Si queremos acceder a un valor especifico del hash basta con hacer
```rb
tutor = {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
puts tutor["nombre"]
# Output Fernando

tutor = {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
puts tutor[[]]
# Output arreglo
```
También podemos agregarle valores o modificarle valores
```rb
tutor = {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
tutor["nombre"] = "Luis"
puts tutor["nombre"]
# Output Luis

tutor = {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
tutor["apellido"] = "Lovera"
puts tutor["apellido"]
# Output Lovera
```

Si intentamos acceder a una clave inexistente nos devuelve vacio
```rb
tutor = {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
puts tutor["test"]
# Output 
```

Podemos colocar un valor por defecto usando "default" para busquedas donde no hay llaves
```rb
tutor = {"nombre" => "Fernando", "edad" => 23, 20=>"Veinte", [] => "arreglo"}
tutor.default = ":)"
puts tutor["test"]
# Output :)
```


Podemos colocar los valores como simbolos `:simbolo` a fin de poder asimilarlo más a un JSON
```rb
tutor = {nombre: "Fernando", edad: 23, }
puts tutor[:edad]
# Output 23

# Si usamos simbolos debemos pedir la llamada con los simbolos
# En caso contrario retorna vacio
tutor = {nombre: "Fernando", edad: 23, }
puts tutor["edad"]
# Output 
```
Para iterar un hash usamos el método each el cual recibe key, value
```rb
tutor = {nombre: "Fernando", edad: 23, }
tutor.each do |key,value|
    puts "La clave: #{key} y su valor #{value}"
end
# Output La clave: nombre y su valor Fernando
# Output La clave: edad y su valor 23
```

Si deseamos obtener el tamaño de nuestro hash usamos length o size
```rb
tutor = {nombre: "Fernando", edad: 23, }
puts tutor.length
# Output 2
puts tutor.size
# Output 2
```

Si deseamos saber si una clave existe en el hash usamos `has_key?`
```rb
tutor = {nombre: "Fernando", edad: 23, }
puts tutor.has_key?(:nombre)
# Output true
puts tutor.has_key?(:test)
# Output false
```

Si deseamos saber si un valor existe en el hash usamos `has_value?`
```rb
tutor = {nombre: "Fernando", edad: 23, }
puts tutor.has_value?(23)
# Output true
puts tutor.has_value?("test")
# Output false
```


Si deseamos saber obtener solo las keys usamos `keys`
```rb
tutor = {nombre: "Fernando", edad: 23, }
puts tutor.keys
# Output nombre,edad un arreglo
```

Si deseamos obtener solo los values usamos `values`
```rb
tutor = {nombre: "Fernando", edad: 23, }
puts tutor.values
# Output Fenando, 23 un arreglo
```

Si deseamos limpiar el hash usamos `clear`
```rb
tutor = {nombre: "Fernando", edad: 23, }
puts tutor.clear
# Output {}
```

Si deseamos eliminar un elemento en una posición especifica usamos `delete`
```rb
tutor = {nombre: "Fernando", edad: 23, }
tutor.delete(:edad)
puts tutor
# Output {nombre: "Fernando"}
```

Si deseamos evaluar si nuestro hash esta vacio usamos `empty?`
```rb
tutor = {nombre: "Fernando", edad: 23, }
# tutor.delete(:edad)
puts tutor.empty?
# Output falso
```

Si deseamos obtener la clave de un valor en especifico usamos `key` o `index`
```rb
tutor = {nombre: "Fernando", edad: 23, }
# tutor.delete(:edad)
puts tutor.key("Fernando");
puts tutor.index("Fernando");
# Output nombre
```

Si deseamos invertir las clave en valores usamos `invert` 
```rb
tutor = {nombre: "Fernando", edad: 23, }
# tutor.delete(:edad)
puts tutor.invert
# Output {Fernando: "nombre", 23: "edad", }
```

Si deseamos combinar hashes usamos `merge`
```rb
tutor = {nombre: "Fernando", edad: 23}
tutorNew = {nombre: "Luis", edad: 50}

# tutor.delete(:edad)
puts tutor.merge(tutorNew)
# Output {nombre: "Fernando", edad: 23, nombre: "Luis", edad: 50}
```

## Simbolos
Es una cadena inmutable o no modificable en tiempo de ejecución, al momento de crearse el `object_id` de un simbolo es el mismo

```rb
cadena=:user 
cadena1=:user
```
Se debe usar simbolos cuando
*   Cuando no necesito modificar el string
*   Cuando no necesito los métodos del string
*   Los simbolos se usan como nombres

## I/O
Para la salida de datos se usa `puts` o `print`, en el caso del `put` imprime en lineas distintas mientras que el `print` en la misma linea 

```rb
puts "Hola"
puts "Fernando"
# Retorna Hola \n Fernando

print "Hola"
print "Fernando"
# Retorna Hola Fernando
```

Para la entrada de datos usamos `gets`

```rb
nombre = gets
apellido = gets
puts "Hola #{nombre} #{apellido}"
# Retorna "Hola {el nombre que coloques} + {el apellido que coloques}"
```

## Sintaxis
*   No es necesario escribir `;` al final de cada linea aunque el compilador puede ignorar que lo hagas
*   Los paréntesis en Ruby al pasar una función o método son opcionales

## Clases

En ruby similar a otros lenguajes de programación orientados a objetos se pueden instanciar las clases e inicializarlas con el método `new`
```rb
class Video
    attr_accesor :minutes, :title

    def play
    end

    def pause
    end
end

video_31_test = Video.new
```

#### Clases.constructor
En ruby al constructor de las clases se le denomina bajo el método `initialize` y basta con colocarlo para al momento de instanciar la clase tener que llamarla con los argumentos que este deba recibir

```rb
class Video   
    def initialize(title)
    end
end

video_31_test = Video.new("title de initialize")
```

## Métodos
Existen infinidades de métodos que se pueden ejecutar en Ruby, para verlos los disponibles podemos ejecutar `"".methods`

#### Definir un Método
Para definir un método usados `def..end`
```rb
def square(x)
    x * x
end

def saludar
    puts "Hola que tal"
end

# Llamamos al método
saludar()
puts square(2)

# Podemos ignorar los parentesis si queremos aunque se recomienda usarlos
saludar
puts square 2
```

Para retornar podemos usar `return` aunque en ruby se puede ignorar ya que los métodos retornan siempre lo que esta en la ultima linea. Se recomienda usar el return si se desea que se devuelva la respuesta con anterioridad
```rb
# Opción con return
def square(x)
    return x * x
end

# Opción sin return
def saludar
    puts "Hola que tal"
end

# Opción con return recomendadas
def square(x)
    return 2 if x == 1
    x * x 
end

```

#### String.class 
Método que retorna el tipo de dato

```rb
nombre = "Fernando"
puts nombre.class # string
```


#### String.upcase 
Método que retorna la cadena en mayuscula

```rb
nombre = "Fernando"
puts "Hola #{nombre.upcase}" # Retorna 'Hola FERNANDO'
```

#### String.downcase 
Método que retorna la cadena en minúscula

```rb
nombre = "Fernando"
puts "Hola #{nombre.downcase}" # Retorna 'Hola fernando'
```

#### String.capitalize 
Método que retorna la primera letra del string en mayúscula y las demás en minúsculas

```rb
nombre = "FeRNaNDo"
puts "Hola #{nombre.downcase}" # Retorna 'Hola Fernando'
```

#### String.length  
Método que retorna el largo del string

```rb
nombre = "Fernando"
puts "Hola #{nombre.upcase}" # Retorna 8
```
#### String.chomp  
Método que elimina la ultima letra agregada en ruby de forma automáticamente después de cada bit de entrada, (este carácter agregado de forma automática es un salto de linea `\n`)

```rb
nombre = gets
nombre = nombre.chomp

puts "Hola #{nombre.chomp}" # Retorna el nombre sin el salto de linea
```

#### String.reverse   
Método que retorna el string al revés

```rb
nombre = "Fernando"
puts "Hola #{nombre.upcase}" # Retorna 'Hola odnaneF'
```

#### String.to_i
Método que retorna el string a entero
```rb
numero = gets.chomp
numero = numero.to_i
puts "El número es #{numero}" # Retorna número entero
```

#### String.to_f
Método que retorna el string a flotante
```rb
numero = gets.chomp
numero = numero.to_f
puts "El número es #{numero}" # Retorna número flotante
```

#### String.to_a
Método que retorna el string a arreglo
```rb
rango = (0..5).to_a
puts "El array es #{numero}" # Retorna una lista
```

#### String.eql
Método que retorna si 2 objetos son iguales tanto en valor como en tipo
```rb
a = 'hola'
b = 'hola'
c = a.eql?(b)
puts "La respuesta es #{c}" # Retorna true
```

#### String.equal
Método que retorna si 2 objetos son copias uno de otro
```rb
a = 'hola'
b = 'hola'
c = a.equal?(b)
puts "La respuesta es #{c}" # Retorna false
```

#### String.gsub
Método que reemplaza las coincidencias en el string
```rb
a = 'hola'
c = a.gsub!(/h/,"p");
puts "La respuesta es #{c}" # Retorna pola
```

#### String.split
Método que convierte un string en un array separandolo por el valor indicado en el split
```rb
a = 'hola que tal'
a.split(",")
puts "La respuesta es #{a}" # Retorna ["hola", "que", "tal"]
```