---
title: Tipos de datos escalares de protobuf-gRPC para desarrolladores de WCF
description: Obtenga información sobre los tipos de datos básicos y conocidos que admiten protobuf y gRPC en .NET Core.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: cae9cc483ffb791a9b53e6a2d9d7c0924d725a67
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841460"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="e41c1-103">Tipos de datos escalares de Protobuf</span><span class="sxs-lookup"><span data-stu-id="e41c1-103">Protobuf scalar data types</span></span>

<span data-ttu-id="e41c1-104">Protobuf admite un intervalo de tipos de valores escalares nativos.</span><span class="sxs-lookup"><span data-stu-id="e41c1-104">Protobuf supports a range of native scalar value types.</span></span> <span data-ttu-id="e41c1-105">En la tabla siguiente se enumeran todos con C# su tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="e41c1-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="e41c1-106">Tipo protobuf</span><span class="sxs-lookup"><span data-stu-id="e41c1-106">Protobuf type</span></span> | <span data-ttu-id="e41c1-107">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="e41c1-107">C# type</span></span>      | <span data-ttu-id="e41c1-108">Notas</span><span class="sxs-lookup"><span data-stu-id="e41c1-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="e41c1-109">1</span><span class="sxs-lookup"><span data-stu-id="e41c1-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="e41c1-110">1</span><span class="sxs-lookup"><span data-stu-id="e41c1-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="e41c1-111">1</span><span class="sxs-lookup"><span data-stu-id="e41c1-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="e41c1-112">1</span><span class="sxs-lookup"><span data-stu-id="e41c1-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="e41c1-113">2</span><span class="sxs-lookup"><span data-stu-id="e41c1-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="e41c1-114">2</span><span class="sxs-lookup"><span data-stu-id="e41c1-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="e41c1-115">2</span><span class="sxs-lookup"><span data-stu-id="e41c1-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="e41c1-116">2</span><span class="sxs-lookup"><span data-stu-id="e41c1-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="e41c1-117">3</span><span class="sxs-lookup"><span data-stu-id="e41c1-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="e41c1-118">4</span><span class="sxs-lookup"><span data-stu-id="e41c1-118">4</span></span>     |

## <a name="notes"></a><span data-ttu-id="e41c1-119">Notas</span><span class="sxs-lookup"><span data-stu-id="e41c1-119">Notes</span></span>

1. <span data-ttu-id="e41c1-120">La codificación estándar para `int32` y `int64` es ineficaz cuando se trabaja con valores con signo.</span><span class="sxs-lookup"><span data-stu-id="e41c1-120">The standard encoding for `int32` and `int64` is inefficient when working with signed values.</span></span> <span data-ttu-id="e41c1-121">Si es probable que el campo contenga números negativos, use `sint32` o `sint64` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e41c1-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="e41c1-122">Ambos tipos se asignan C# a los tipos `int` y `long`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e41c1-122">Both types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="e41c1-123">Los campos de `fixed` siempre utilizan el mismo número de bytes, independientemente del valor que sea.</span><span class="sxs-lookup"><span data-stu-id="e41c1-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="e41c1-124">Este comportamiento hace que la serialización y la deserialización sean más rápidas para los valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="e41c1-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="e41c1-125">Las cadenas protobuf son codificadas con UTF-8 (o ASCII de 7 bits) y la longitud codificada no puede ser mayor que 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="e41c1-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded, and the encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="e41c1-126">El tiempo de ejecución de protobuf proporciona un tipo de `ByteString` que se C# asigna fácilmente a `byte[]` matrices y desde ellas.</span><span class="sxs-lookup"><span data-stu-id="e41c1-126">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="e41c1-127">Otros tipos primitivos de .NET</span><span class="sxs-lookup"><span data-stu-id="e41c1-127">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="e41c1-128">Fechas y horas</span><span class="sxs-lookup"><span data-stu-id="e41c1-128">Dates and times</span></span>

<span data-ttu-id="e41c1-129">Los tipos escalares nativos no proporcionan valores de fecha y hora, equivalentes a C#<xref:System.DateTimeOffset>, <xref:System.DateTime>y <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="e41c1-129">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="e41c1-130">Estos tipos se pueden especificar usando algunas de las extensiones de "tipos conocidos" de Google, que proporcionan compatibilidad de generación de código y en tiempo de ejecución para tipos de campo más complejos en las plataformas admitidas.</span><span class="sxs-lookup"><span data-stu-id="e41c1-130">These types can be specified using some of Google's "Well Known Types" extensions, which provide code generation and runtime support for more complex field types across the supported platforms.</span></span> <span data-ttu-id="e41c1-131">En la tabla siguiente se muestran los tipos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="e41c1-131">The following table shows the date and time types:</span></span>

| <span data-ttu-id="e41c1-132">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="e41c1-132">C# type</span></span> | <span data-ttu-id="e41c1-133">Protobuf Well-Known Type</span><span class="sxs-lookup"><span data-stu-id="e41c1-133">Protobuf well-known type</span></span> |
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

<span data-ttu-id="e41c1-134">Las propiedades generadas en C# la clase no son los tipos de fecha y hora de .net.</span><span class="sxs-lookup"><span data-stu-id="e41c1-134">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="e41c1-135">Las propiedades usan las clases `Timestamp` y `Duration` en el espacio de nombres `Google.Protobuf.WellKnownTypes`, que proporcionan métodos para realizar conversiones entre `DateTimeOffset`, `DateTime`y `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="e41c1-135">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace, which provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="e41c1-136">El tipo de `Timestamp` funciona con las horas UTC; los valores de `DateTimeOffset` siempre tienen un desplazamiento de cero y la propiedad `DateTime.Kind` siempre se `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="e41c1-136">The `Timestamp` type works with UTC times; `DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property will always be `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="e41c1-137">System.Guid</span><span class="sxs-lookup"><span data-stu-id="e41c1-137">System.Guid</span></span>

<span data-ttu-id="e41c1-138">El tipo de <xref:System.Guid>, conocido como `UUID` en otras plataformas, no es compatible directamente con protobuf y no hay ningún tipo conocido para él.</span><span class="sxs-lookup"><span data-stu-id="e41c1-138">The <xref:System.Guid> type, known as `UUID` on other platforms, isn't directly supported by Protobuf and there's no well-known type for it.</span></span> <span data-ttu-id="e41c1-139">El mejor enfoque consiste en controlar `Guid` valores como `string` campo, con el formato hexadecimal de `8-4-4-4-12` estándar (por ejemplo, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), que puede analizarse en todos los lenguajes y plataformas.</span><span class="sxs-lookup"><span data-stu-id="e41c1-139">The best approach is to handle `Guid` values as `string` field, using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`), which can be parsed by all languages and platforms.</span></span> <span data-ttu-id="e41c1-140">No use un campo de `bytes` para `Guid` valores, ya que los problemas con modos endian pueden producir un comportamiento errático al interactuar con otras plataformas, como Java.</span><span class="sxs-lookup"><span data-stu-id="e41c1-140">Don't use a `bytes` field for `Guid` values, as problems with endianness can result in erratic behavior when interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="e41c1-141">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="e41c1-141">Nullable types</span></span>

<span data-ttu-id="e41c1-142">La generación de código protobuf C# para usa los tipos nativos, como `int` para `int32`.</span><span class="sxs-lookup"><span data-stu-id="e41c1-142">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="e41c1-143">Esto significa que los valores siempre se incluyen y no pueden ser null.</span><span class="sxs-lookup"><span data-stu-id="e41c1-143">This means that the values are always included and can't be null.</span></span> <span data-ttu-id="e41c1-144">En el caso de los valores que requieren valores NULL explícitos, C# como el uso de `int?` en el código, los "tipos conocidos" de protobuf incluyen contenedores C# que se compilan en tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="e41c1-144">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="e41c1-145">Para usarlos, importe `wrappers.proto` en el archivo `.proto`, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e41c1-145">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="e41c1-146">Protobuf usará el `T?` simple (por ejemplo, `int?`) para la propiedad de mensaje generada.</span><span class="sxs-lookup"><span data-stu-id="e41c1-146">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="e41c1-147">En la tabla siguiente se muestra la lista completa de tipos de contenedor C# con su tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="e41c1-147">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="e41c1-148">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="e41c1-148">C# type</span></span>   | <span data-ttu-id="e41c1-149">Contenedor de tipo conocido</span><span class="sxs-lookup"><span data-stu-id="e41c1-149">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="e41c1-150">Los tipos conocidos `Timestamp` y `Duration` se representan en .NET como clases, por lo que no hay necesidad de una versión que acepte valores NULL, pero es importante comprobar si hay valores NULL en las propiedades de esos tipos al convertirlos a `DateTimeOffset` o `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="e41c1-150">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version, but it's important to check for null on properties of those types when converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="e41c1-151">decimales</span><span class="sxs-lookup"><span data-stu-id="e41c1-151">Decimals</span></span>

<span data-ttu-id="e41c1-152">Protobuf no admite de forma nativa el tipo de `decimal` .NET, simplemente `double` y `float`.</span><span class="sxs-lookup"><span data-stu-id="e41c1-152">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="e41c1-153">Hay una explicación en curso en el proyecto protobuf sobre la posibilidad de agregar un tipo de `Decimal` estándar a los tipos conocidos, con compatibilidad de plataforma para los lenguajes y marcos que lo admiten, pero aún no se ha implementado nada.</span><span class="sxs-lookup"><span data-stu-id="e41c1-153">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it, but nothing has been implemented yet.</span></span>

<span data-ttu-id="e41c1-154">Es posible crear una definición de mensaje para representar el tipo de `decimal` que funcionaría para la serialización segura entre clientes y servidores de .NET, pero los desarrolladores de otras plataformas tendrían que comprender el formato que se usa e implementar su propio control.</span><span class="sxs-lookup"><span data-stu-id="e41c1-154">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers, but developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="e41c1-155">Crear un tipo decimal personalizado para protobuf</span><span class="sxs-lookup"><span data-stu-id="e41c1-155">Creating a custom Decimal type for Protobuf</span></span>

<span data-ttu-id="e41c1-156">Una implementación muy sencilla podría ser similar al tipo de `Money` no estándar usado por algunas API de Google, sin el campo `currency`.</span><span class="sxs-lookup"><span data-stu-id="e41c1-156">A very simple implementation could be similar to the non-standard `Money` type used by some Google APIs, without the `currency` field.</span></span>

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

<span data-ttu-id="e41c1-157">El campo `nanos` representa los valores de `0.999_999_999` a `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="e41c1-157">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="e41c1-158">Por ejemplo, el valor de `decimal` `1.5m` se representaría como `{ units = 1, nanos = 500_000_000 }` (este es el motivo por el que el campo `nanos` de este ejemplo usa el tipo de `sfixed32`, que codifica de forma más eficaz que `int32` para valores mayores).</span><span class="sxs-lookup"><span data-stu-id="e41c1-158">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }` (this is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values).</span></span> <span data-ttu-id="e41c1-159">Si el campo `units` es negativo, el campo de `nanos` también debe ser negativo.</span><span class="sxs-lookup"><span data-stu-id="e41c1-159">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="e41c1-160">Existen varios algoritmos para codificar los valores `decimal` como cadenas de bytes, pero este mensaje es mucho más fácil de entender que cualquiera de ellos, y los valores no se ven afectados por *[modos endian](https://en.wikipedia.org/wiki/Endianness)* en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="e41c1-160">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is much easier to understand than any of them, and the values are not affected by *[endianness](https://en.wikipedia.org/wiki/Endianness)* on different platforms.</span></span>

<span data-ttu-id="e41c1-161">La conversión entre este tipo y el tipo de `decimal` BCL podría implementarse de C# la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="e41c1-161">Conversion between this type and the BCL `decimal` type could be implemented in C# like this.</span></span>

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
> <span data-ttu-id="e41c1-162">Siempre que use tipos de mensaje de utilidad personalizados como este, **debe** documentarlos con comentarios en el `.proto` para que otros desarrolladores puedan implementar la conversión a y desde el tipo equivalente en su propio lenguaje o marco.</span><span class="sxs-lookup"><span data-stu-id="e41c1-162">Whenever you use custom utility message types like this, you **must** document them with comments in the `.proto` so that other developers can implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e41c1-163">[Anterior](protobuf-messages.md)
>[Siguiente](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="e41c1-163">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
