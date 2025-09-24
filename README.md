
**Ejemplos:**
- Una instancia de la clase Fruta podría ser una manzana específica, con un color rojo y un sabor dulce.
- Una instancia de vehículo puede ser un Automóvil, con color rojo, locomoción por motor de combustión, y comportamientos de encender, frenar y apagar.

# Diagrama UML

```mermaid
classDiagram
    class Paciente {
        +idPaciente : int
        +nombre : string
        +edad : int
        +historialMedico : string
        +solicitarCita()
        +pagarFactura()
    }

    class Doctor {
        +idDoctor : int
        +nombre : string
        +especialidad : string
        +atenderCita()
    }

    class Cita {
        +idCita : int
        +fecha : date
        +hora : time
        +estado : string
        +programar()
        +cancelar()
    }

    class Receta {
        +idReceta : int
        +medicamentos[] : list
        +instrucciones : string
        +imprimir()
    }

    class Factura {
        +idFactura : int
        +monto : double
        +estado : string
        +generar()
        +pagar()
    }

    %% Relaciones
    Paciente "1" --> "1" Cita : tiene >
    Cita "1" --> "1" Doctor : atendida por >
    Cita "1" --> "0..1" Receta : genera >
    Paciente "1" --> "1" Factura : recibe >
