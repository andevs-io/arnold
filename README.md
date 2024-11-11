# arnold
Simple ERP for texting operations 

```mermaid
classDiagram
    class Cliente {
        +String id
        +String nombre
        +String contacto-email
    }

    class Lote {
        +String id
        +String ClientId
        +String Nombre
        +String Referencia
        +String FechaCreación
        +int Cantidad
        +double valorUnidadPactado
        +Date fechaComprometida
        +EstadoLote estadoActual
    }

    class Factura {
        +String id
        +String loteId
        +Date FechaVencimiento
        +double ValorPagado
        +EstadoFactura estadoActual
    }

    class EstadoFactura {
        +String id
        +Time fecha
        +Estado estado
        +String observacion
        +String facturaId
    }

        class EstadoLote {
        +int id
        +Time fecha
        +Estado estado
        +String observacion
        +String loteId
    }

    

    Cliente "1" --> "*" Lote: tiene
    Lote "1" --> "*"Factura : tiene
    Lote "1" --> "*"EstadoLote : tiene
    Factura "1" --> "*"EstadoFactura : tiene
```
