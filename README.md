## UN Code Generator

It takes as input a PlantUML class diagram and outputs the JAVA classes that match it


En caso de que se quiera probar algún UML distinto a los de los ejemplos se deberá tener en cuenta los caracteres que se manejan dentro del propio código y como están organizados (el orden en el que se pueden poner las "palabras clave", los cuales son: 

* Caracteres y Orden en clases -> abstract*opcional* - class - (a-z, A-Z, y 0-9) extens*opcional* - (a-z, A-Z, y 0-9)*si se pone el extens*
* Orden de enum -> enum (a-z, A-Z, y 0-9) {([^\}])+)\}
* Caracteres y Orden de Métodos -> (+#-) (tipo de dato) (nombre) parámetros

Aclaraciones: 
(a-z, A-Z, y 0-9) -> Lo que puede contener el nombre (letras mayúsculas, minúsculas, y números).
{([^\}])+)\} -> Toma lo que esté dentro de las llaves menos la llave de cierre "}" (ej. LUNES, MARTES, MIERCOLES)

Miembros del grupo: 
Cesar Augusto Jarava González y Andrés Emilio Serpa Castellar

Ejemplos:

@startuml
abstract class Animal {
    + String nombre
    + void hacerSonido()
}

class Perro extends Animal {
    + void hacerSonido()
}
@enduml

@startuml
abstract class Animal {
    + String nombre
    + void hacerSonido()
}

class Perro {
    + void hacerSonido()
}

Perro --|> Animal
@enduml

@startuml
enum DiaSemana {
    LUNES, MARTES, MIERCOLES
}
@enduml

@startuml
class Profesor {
    + String nombre
}

class Curso {
    + String titulo
}

Profesor "1" -- "*" Curso
@enduml
