## Codigo plantUML de clases del problema
~~~
@startuml
abstract class Figura{
    # nombre : string
    # color : string
    # area : double
    # perimetro : double
    --
    + {abstract} informacion() : void
    + {abstract} area() : double
    + {abstract} perimetro() : double


}


class Rectangulo{
    - base : double
    - altura : double
    --
    + Rectangulo()
    + Rectangulo(double : b, double : a)
    + Rectangulo(Rectangulo : r)
    + informacion(): void
    + area() : void
    + perimetro() : void
    + setBase(double : b) : void
    + getBase() : double
    + setAltura(double : a)
    + getAltura()
    
}

class Circulo{
    - radio : double

    --
    + Circulo()
    + Circulo(double : radio)
    + Circulo(Circulo c)
    + informacion(): void
    + area() : void
    + perimetro() : void
    + setRadio(double : radio) : void
    + getRadio() : double
}

class Triangulo{
    - base : double
    - altura : double
    --
    + Triangulo() 
    + Triangulo(double : base, double altura)
    + Triangulo(Triangulo t)
    + informacion(): void
    + area() : void
    + perimetro() : void
    + setBase(double : Base): void
    + getBase() : double
    + setAltura(double : Altura) : void
    + getAltura() : double
    
}

class Principal {
  + {static} main(String[] args) :void
    
}

Figura <|-- Rectangulo
Figura <|-- Circulo
Figura <|-- Triangulo

Rectangulo -- Principal
Circulo -- Principal
Triangulo -- Principal



@enduml

~~~