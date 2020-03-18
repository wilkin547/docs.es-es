---
title: Tipos de datos escalares de Protobuf - gRPC para desarrolladores de WCF
description: Obtenga información sobre los tipos de datos básicos y conocidos que protobuf y gRPC admiten en .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: a40f51fa32ddb97ba417ec01f31e1f0187f0d544
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148132"
---
# <a name="protobuf-scalar-data-types"></a>Tipos de datos escalares de Protobuf

El búfer de protocolo (Protobuf) admite un intervalo de tipos de valor escalar nativos. En la tabla siguiente se enumeran todos ellos con su tipo equivalente de C-:

| Tipo de protobuf | Tipo de C#      | Notas |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | 1     |
| `int64`       | `long`       | 1     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | 1     |
| `sint64`      | `long`       | 1     |
| `fixed32`     | `uint`       | 2     |
| `fixed64`     | `ulong`      | 2     |
| `sfixed32`    | `int`        | 2     |
| `sfixed64`    | `long`       | 2     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | 3     |
| `bytes`       | `ByteString` | 4     |

Notas:

1. La codificación `int32` `int64` estándar para y es ineficiente cuando se trabaja con valores firmados. Si es probable que el campo `sint32` `sint64` contenga números negativos, úselo o en su lugar. Estos tipos se asignan `int` `long` a los tipos y C- y, respectivamente.
2. Los `fixed` campos siempre utilizan el mismo número de bytes independientemente del valor. Este comportamiento hace que la serialización y la deserialización sean más rápidas para valores más grandes.
3. Las cadenas Protobuf están codificadas en UTF-8 (o ASCII de 7 bits). La longitud codificada no puede ser mayor que 2<sup>32</sup>.
4. El tiempo de ejecución `ByteString` de Protobuf proporciona `byte[]` un tipo que se asigna fácilmente hacia y desde matrices de C.

## <a name="other-net-primitive-types"></a>Otros tipos primitivos de .NET

### <a name="dates-and-times"></a>Fechas y horas

Los tipos escalares nativos no proporcionan valores de fecha y <xref:System.DateTimeOffset>hora, equivalentes a Los valores de C's , <xref:System.DateTime>, y <xref:System.TimeSpan>. Puede especificar estos tipos mediante algunas de las extensiones "Tipos bien conocidos" de Google. Estas extensiones proporcionan compatibilidad de generación de código y tiempo de ejecución para tipos de campo complejos en las plataformas admitidas.

En la tabla siguiente se muestran los tipos de fecha y hora:

| Tipo de C# | Tipo conocido de Protobuf |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

Las propiedades generadas en la clase de C- no son los tipos de fecha y hora de .NET. Las propiedades `Timestamp` usan `Duration` las `Google.Protobuf.WellKnownTypes` clases y del espacio de nombres. Estas clases proporcionan métodos `DateTimeOffset`para `DateTime`convertir `TimeSpan`a , , y .

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> El `Timestamp` tipo funciona con las horas UTC. `DateTimeOffset`los valores siempre tienen un `DateTime.Kind` desplazamiento de `DateTimeKind.Utc`cero y la propiedad siempre es .

### <a name="systemguid"></a>System.Guid

Protobuf no admite directamente el <xref:System.Guid> `UUID` tipo, conocido como en otras plataformas. No hay ningún tipo conocido para ello.

El mejor enfoque `Guid` es controlar `string` los valores como `8-4-4-4-12` un campo, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`utilizando el formato hexadecimal estándar (por ejemplo, ). Todos los idiomas y plataformas pueden analizar ese formato.

No use un `bytes` campo `Guid` para los valores. Los problemas con *la endianidad* [(definición](https://en.wikipedia.org/wiki/Endianness)de Wikipedia) pueden dar lugar a un comportamiento errático cuando Protobuf está interactuando con otras plataformas, como Java.

### <a name="nullable-types"></a>Tipos que aceptan valores NULL

La generación de código Protobuf para C- usa los tipos nativos, como `int` para `int32`. Por lo tanto, los valores siempre se incluyen y no pueden ser null.

En el caso de los `int?` valores que requieren null explícito, como el uso en el código de C, los "Tipos bien conocidos" de Protobuf incluyen contenedores que se compilan en tipos de C. Para usarlos, `wrappers.proto` importe `.proto` en su archivo, así:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf usará la `T?` simple (por ejemplo, `int?`) para la propiedad de mensaje generada.

En la tabla siguiente se muestra la lista completa de tipos de contenedor con su tipo equivalente de C-:

| Tipo de C#   | Envoltura de tipo bien conocido       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Los tipos `Timestamp` conocidos `Duration` y se representan en .NET como clases, por lo que no hay necesidad de una versión que acepta valores NULL. Pero es importante comprobar si es null en las propiedades de `DateTimeOffset` `TimeSpan`esos tipos cuando se convierte a o .

## <a name="decimals"></a>Decimals

Protobuf no admite de forma `decimal` nativa el `double` `float`tipo .NET, solo y . Hay una discusión en curso en el proyecto Protobuf sobre la posibilidad de agregar un tipo estándar `Decimal` a los tipos conocidos, con soporte de plataforma para lenguajes y marcos que lo admiten. Aún no se ha implementado nada.

Es posible crear una definición de `decimal` mensaje para representar el tipo que funcionaría para la serialización segura entre clientes y servidores .NET. Pero los desarrolladores de otras plataformas tendrían que entender el formato que se está utilizando e implementar su propio manejo para él.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Creación de un tipo decimal personalizado para Protobuf

Una implementación simple podría ser `Money` similar al tipo no estándar `currency` que usan algunas API de Google, sin el campo.

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message Decimal {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

El `nanos` campo representa `0.999_999_999` valores `-0.999_999_999`de to . Por ejemplo, `decimal` `1.5m` el valor se `{ units = 1, nanos = 500_000_000 }`representaría como . Esta es `nanos` la razón por `sfixed32` la que el campo `int32` de este ejemplo utiliza el tipo, que codifica más eficazmente que para valores más grandes. Si `units` el campo es `nanos` negativo, el campo también debe ser negativo.

> [!NOTE]
> Hay varios otros algoritmos `decimal` para codificar valores como cadenas de bytes, pero este mensaje es más fácil de entender que cualquiera de ellos. Los valores no se ven afectados por la endianidad en diversas plataformas.

La conversión entre este `decimal` tipo y el tipo DeBCL podría implementarse en C- de la siguiente manera:

```csharp
namespace CustomTypes
{
    public partial class GrpcDecimal
    {
        private const decimal NanoFactor = 1_000_000_000;
        public GrpcDecimal(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.Decimal grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.Decimal(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.Decimal(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> Siempre que utilice tipos de *must* mensajes personalizados como `.proto`este, debe documentarlos con comentarios en . A continuación, otros desarrolladores pueden implementar la conversión hacia y desde el tipo equivalente en su propio lenguaje o marco de trabajo.

>[!div class="step-by-step"]
>[Anterior](protobuf-messages.md)
>[Siguiente](protobuf-nested-types.md)
