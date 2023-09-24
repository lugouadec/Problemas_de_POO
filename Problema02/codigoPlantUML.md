# Codigo PlantUML

~~~

@startuml

class Vuelo {
  - numeroVuelo: String
  - origen: String
  - destino: String
  - fecha: String
  - hora: String
  - capacidadMaxima: int
  - precioAsiento: float
  + consultarDisponibilidad(): int
  + reservarAsiento(pasajero: Pasajero, numAsientos: int): Reserva
  + calcularPrecioTotal(numAsientos: int): float
}

class Pasajero {
  - nombre: String
  - apellido: String
  - numPasaporte: String
  - reservas: List<Reserva>
  + hacerReserva(vuelo: Vuelo, numAsientos: int): Reserva
  + cancelarReserva(reserva: Reserva): void
  + consultarReservas(): List<Reserva>
  + calcularCostoTotalReservas(): float
}

class SistemaReservas {
  - vuelosDisponibles: List<Vuelo>
  - pasajeros: List<Pasajero>
  + agregarVuelo(vuelo: Vuelo): void
  + registrarPasajero(pasajero: Pasajero): void
  + buscarVuelosDisponibles(origen: String, destino: String, fecha: String): List<Vuelo>
  + realizarReserva(pasajero: Pasajero, vuelo: Vuelo, numAsientos: int): Reserva
  + cancelarReserva(pasajero: Pasajero, reserva: Reserva): void
  + generarInforme(): String
}

class Reserva {
  - vuelo: Vuelo
  - pasajero: Pasajero
  - numAsientos: int
  + calcularCostoTotal(): float
}

Vuelo --* Reserva
Pasajero --* Reserva

@enduml

~~~