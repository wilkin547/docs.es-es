---
title: Tipos de datos escalares de protobuf-gRPC para desarrolladores de WCF
description: Obtenga información sobre los tipos de datos básicos y conocidos que admiten protobuf y gRPC en .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: 5447067b953d257258950d020636e0b38245e20d
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "91573649"
---
# <a name="protobuf-scalar-data-types"></a>Tipos de datos escalares de Protobuf

El búfer de protocolo (protobuf) admite un intervalo de tipos de valores escalares nativos. En la tabla siguiente se enumeran todos con su tipo C# equivalente:

| Tipo de Protobuf | Tipo de C#      | Notas |
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

1. La codificación estándar para `int32` y `int64` es ineficaz cuando se trabaja con valores con signo. Si es probable que el campo contenga números negativos, use `sint32` o `sint64` en su lugar. Estos tipos se asignan a `int` los `long` tipos C# y, respectivamente.
2. Los `fixed` campos siempre utilizan el mismo número de bytes, independientemente de cuál sea el valor. Este comportamiento hace que la serialización y la deserialización sean más rápidas para los valores más grandes.
3. Las cadenas protobuf son codificadas con UTF-8 (o ASCII de 7 bits). La longitud codificada no puede ser mayor que 2<sup>32</sup>.
4. El tiempo de ejecución de protobuf proporciona un `ByteString` tipo que se asigna fácilmente a las matrices de C# y desde ellas `byte[]` .

## <a name="other-net-primitive-types"></a>Otros tipos primitivos de .NET

### <a name="dates-and-times"></a>Fechas y horas

Los tipos escalares nativos no proporcionan valores de fecha y hora, equivalentes a <xref:System.DateTimeOffset> , <xref:System.DateTime> y de C# <xref:System.TimeSpan> . Puede especificar estos tipos mediante el uso de algunas de las extensiones de "tipos conocidos" de Google. Estas extensiones proporcionan compatibilidad con el entorno de ejecución y la generación de código para los tipos de campo complejos en las plataformas admitidas.

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

Las propiedades generadas en la clase C# no son los tipos de fecha y hora de .NET. Las propiedades usan las clases `Timestamp` y `Duration` en el espacio de nombres `Google.Protobuf.WellKnownTypes`. Estas clases proporcionan métodos para realizar conversiones a `DateTimeOffset`, `DateTime` y `TimeSpan`, y desde estas.

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
> El tipo `Timestamp` funciona con horas UTC. Los valores `DateTimeOffset` siempre tienen un desplazamiento de cero, y la propiedad `DateTime.Kind` siempre es `DateTimeKind.Utc`.

### <a name="systemguid"></a>System.Guid

Protobuf no es compatible directamente con el <xref:System.Guid> tipo, conocido como `UUID` en otras plataformas. No hay ningún tipo conocido para ella.

El mejor enfoque es controlar `Guid` los valores como un `string` campo, utilizando el `8-4-4-4-12` formato hexadecimal estándar (por ejemplo, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` ). Todos los lenguajes y plataformas pueden analizar ese formato.

No use un `bytes` campo para `Guid` los valores. Los problemas con *modos endian* ([definición de Wikipedia](https://en.wikipedia.org/wiki/Endianness)) pueden dar lugar a un comportamiento errático cuando protobuf interactúa con otras plataformas, como Java.

### <a name="nullable-types"></a>Tipos que aceptan valores NULL

La generación de código de Protobuf para C# usa los tipos nativos, como `int` para `int32`. Por lo tanto, los valores siempre se incluyen y no pueden ser null.

En el caso de los valores que requieren valores NULL explícitos, como `int?` el uso de en el código de c#, los "tipos conocidos" de protobuf incluyen contenedores que se compilan en tipos de C# que aceptan valores NULL. Para usarlos, importe `wrappers.proto` en el `.proto` archivo, de la siguiente manera:

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

Protobuf usará el simple `T?` (por ejemplo, `int?` ) para la propiedad de mensaje generada.

En la tabla siguiente se muestra la lista completa de tipos de contenedor con su tipo C# equivalente:

| Tipo de C#   | Contenedor de Tipo conocido       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

Los tipos conocidos `Timestamp` y `Duration` se representan en .net como clases. En C# 8 y versiones posteriores, puede usar tipos de referencia que aceptan valores NULL. Pero es importante comprobar si hay valores NULL en las propiedades de esos tipos cuando se realiza la conversión a `DateTimeOffset` o `TimeSpan` .

## <a name="decimals"></a>Decimals

Protobuf no admite de forma nativa el tipo `decimal` de .NET, solo `double` y `float`. En el proyecto protobuf, hay una discusión en curso sobre la posibilidad de agregar un `Decimal` tipo estándar a los tipos conocidos, con compatibilidad de plataforma para los lenguajes y marcos que lo admiten. Todavía no se ha implementado nada.

Es posible crear una definición de mensaje para representar el `decimal` tipo que funcionaría para la serialización segura entre clientes y servidores .net. Sin embargo, los desarrolladores de otras plataformas tendrían que conocer el formato que se usa e implementar su propio control.

### <a name="creating-a-custom-decimal-type-for-protobuf"></a>Creación de un tipo decimal personalizado para Protobuf

Una implementación sencilla podría ser similar al `Money` tipo no estándar que usan algunas API de Google, sin el `currency` campo.

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message DecimalValue {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

El campo `nanos` representa los valores de `0.999_999_999` a `-0.999_999_999`. Por ejemplo, el valor `decimal` `1.5m` se representaría como `{ units = 1, nanos = 500_000_000 }`. Este es el motivo por el que el campo `nanos` de este ejemplo usa el tipo `sfixed32`, que codifica de forma más eficaz que `int32` para los valores más grandes. Si el campo `units` es negativo, el campo `nanos` también debe serlo.

> [!NOTE]
> Existen varios algoritmos para codificar los valores `decimal` como cadenas de bytes, pero este mensaje es más fácil de entender que cualquiera de ellos. Los valores no se ven afectados por modos endian en distintas plataformas.

La conversión entre este tipo y el tipo `decimal` de BCL podría implementarse en C# de la siguiente manera:

```csharp
namespace CustomTypes
{
    public partial class DecimalValue
    {
        private const decimal NanoFactor = 1_000_000_000;
        public DecimalValue(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.DecimalValue grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.DecimalValue(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.DecimalValue(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> Siempre que use tipos de mensaje personalizados como este, *debe* documentarlos con comentarios en `.proto` . A continuación, otros desarrolladores pueden implementar la conversión a y desde el tipo equivalente en su propio lenguaje o marco.

>[!div class="step-by-step"]
>[Anterior](protobuf-messages.md)
>[Siguiente](protobuf-nested-types.md)
