## Reto 2
Desarrolle la mayoría de ejercicios en clase. Para cada punto cree un programa individual. Al finalizar suba todo a un repo y súbalo al canal reto_2 en slack.

1. Elija un problema de la vida real (sistema de gestión de biblioteca, negocio de compra-venta, automóvil, etc) que se pueda modelar a través de objetos y clases. Plantee las relaciones de clases, composiciones, propiedades y comportamientos del sistema en uno mas diagramas tipo UML.

**Solucion:**
- Para este reto he decidido tomar el ejemplo de el sistema de un hospital a la hora de atender a un usuario 

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
    Paciente "1" --* "0..1" Cita : tiene >
    Cita "1" --* "1" Doctor : atendida por >
    Cita "1" --* "0..1" Receta : genera >
    Paciente "1" --* "1" Factura : recibe >

