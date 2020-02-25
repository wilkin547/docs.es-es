---
title: Tipos de datos escalares de protobuf-gRPC para desarrolladores de WCF
description: Obtenga información sobre los tipos de datos básicos y conocidos que admiten protobuf y gRPC en .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: f5215550a6a2d54dfe2e859c574a34f641fdb68d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543162"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="2e4aa-103">Tipos de datos escalares de Protobuf</span><span class="sxs-lookup"><span data-stu-id="2e4aa-103">Protobuf scalar data types</span></span>

<span data-ttu-id="2e4aa-104">El búfer de protocolo (protobuf) admite un intervalo de tipos de valores escalares nativos.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="2e4aa-105">En la tabla siguiente se enumeran todos con C# su tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="2e4aa-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="2e4aa-106">Tipo protobuf</span><span class="sxs-lookup"><span data-stu-id="2e4aa-106">Protobuf type</span></span> | <span data-ttu-id="2e4aa-107">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="2e4aa-107">C# type</span></span>      | <span data-ttu-id="2e4aa-108">Notas</span><span class="sxs-lookup"><span data-stu-id="2e4aa-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="2e4aa-109">1</span><span class="sxs-lookup"><span data-stu-id="2e4aa-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="2e4aa-110">1</span><span class="sxs-lookup"><span data-stu-id="2e4aa-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="2e4aa-111">1</span><span class="sxs-lookup"><span data-stu-id="2e4aa-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="2e4aa-112">1</span><span class="sxs-lookup"><span data-stu-id="2e4aa-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="2e4aa-113">2</span><span class="sxs-lookup"><span data-stu-id="2e4aa-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="2e4aa-114">2</span><span class="sxs-lookup"><span data-stu-id="2e4aa-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="2e4aa-115">2</span><span class="sxs-lookup"><span data-stu-id="2e4aa-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="2e4aa-116">2</span><span class="sxs-lookup"><span data-stu-id="2e4aa-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="2e4aa-117">3</span><span class="sxs-lookup"><span data-stu-id="2e4aa-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="2e4aa-118">4</span><span class="sxs-lookup"><span data-stu-id="2e4aa-118">4</span></span>     |

<span data-ttu-id="2e4aa-119">Notas:</span><span class="sxs-lookup"><span data-stu-id="2e4aa-119">Notes:</span></span>

1. <span data-ttu-id="2e4aa-120">La codificación estándar para `int32` y `int64` es ineficaz cuando se trabaja con valores con signo.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="2e4aa-121">Si es probable que el campo contenga números negativos, use `sint32` o `sint64` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="2e4aa-122">Estos tipos se asignan C# a los tipos `int` y `long`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="2e4aa-123">Los campos de `fixed` siempre utilizan el mismo número de bytes, independientemente del valor que sea.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="2e4aa-124">Este comportamiento hace que la serialización y la deserialización sean más rápidas para los valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="2e4aa-125">Las cadenas protobuf son codificadas con UTF-8 (o ASCII de 7 bits).</span><span class="sxs-lookup"><span data-stu-id="2e4aa-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="2e4aa-126">La longitud codificada no puede ser mayor que 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="2e4aa-127">El tiempo de ejecución de protobuf proporciona un tipo de `ByteString` que se C# asigna fácilmente a `byte[]` matrices y desde ellas.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="2e4aa-128">Otros tipos primitivos de .NET</span><span class="sxs-lookup"><span data-stu-id="2e4aa-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="2e4aa-129">Fechas y horas</span><span class="sxs-lookup"><span data-stu-id="2e4aa-129">Dates and times</span></span>

<span data-ttu-id="2e4aa-130">Los tipos escalares nativos no proporcionan valores de fecha y hora, equivalentes a C#<xref:System.DateTimeOffset>, <xref:System.DateTime>y <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="2e4aa-131">Puede especificar estos tipos mediante el uso de algunas de las extensiones de "tipos conocidos" de Google.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="2e4aa-132">Estas extensiones proporcionan compatibilidad en tiempo de ejecución y generación de código para los tipos de campo complejos en las plataformas admitidas.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span> 

<span data-ttu-id="2e4aa-133">En la tabla siguiente se muestran los tipos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="2e4aa-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="2e4aa-134">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="2e4aa-134">C# type</span></span> | <span data-ttu-id="2e4aa-135">Protobuf Well-Known Type</span><span class="sxs-lookup"><span data-stu-id="2e4aa-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="2e4aa-136">Las propiedades generadas en C# la clase no son los tipos de fecha y hora de .net.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="2e4aa-137">Las propiedades usan las clases `Timestamp` y `Duration` en el espacio de nombres `Google.Protobuf.WellKnownTypes`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="2e4aa-138">Estas clases proporcionan métodos para realizar conversiones entre `DateTimeOffset`, `DateTime`y `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="2e4aa-139">El tipo de `Timestamp` funciona con horas UTC.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="2e4aa-140">los valores `DateTimeOffset` siempre tienen un desplazamiento de cero y la propiedad `DateTime.Kind` siempre es `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="2e4aa-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="2e4aa-141">System.Guid</span></span>

<span data-ttu-id="2e4aa-142">Protobuf no admite directamente el tipo de <xref:System.Guid>, conocido como `UUID` en otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="2e4aa-143">No hay ningún tipo conocido para ella.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-143">There's no well-known type for it.</span></span> 

<span data-ttu-id="2e4aa-144">El mejor enfoque es controlar los valores de `Guid` como un campo `string`, mediante el formato hexadecimal de `8-4-4-4-12` estándar (por ejemplo, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span><span class="sxs-lookup"><span data-stu-id="2e4aa-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="2e4aa-145">Todos los lenguajes y plataformas pueden analizar ese formato.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="2e4aa-146">No use un campo de `bytes` para los valores de `Guid`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="2e4aa-147">Los problemas con *modos endian* ([definición de Wikipedia](https://en.wikipedia.org/wiki/Endianness)) pueden dar lugar a un comportamiento errático cuando protobuf interactúa con otras plataformas, como Java.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="2e4aa-148">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="2e4aa-148">Nullable types</span></span>

<span data-ttu-id="2e4aa-149">La generación de código protobuf C# para usa los tipos nativos, como `int` para `int32`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="2e4aa-150">Por lo tanto, los valores siempre se incluyen y no pueden ser null.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-150">So the values are always included and can't be null.</span></span> 

<span data-ttu-id="2e4aa-151">En el caso de los valores que requieren valores NULL explícitos, C# como el uso de `int?` en el código, los "tipos conocidos" de protobuf incluyen contenedores C# que se compilan en tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="2e4aa-152">Para usarlos, importe `wrappers.proto` en el archivo `.proto`, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2e4aa-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="2e4aa-153">Protobuf usará el `T?` simple (por ejemplo, `int?`) para la propiedad de mensaje generada.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="2e4aa-154">En la tabla siguiente se muestra la lista completa de tipos de contenedor C# con su tipo equivalente:</span><span class="sxs-lookup"><span data-stu-id="2e4aa-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="2e4aa-155">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="2e4aa-155">C# type</span></span>   | <span data-ttu-id="2e4aa-156">Contenedor de tipo conocido</span><span class="sxs-lookup"><span data-stu-id="2e4aa-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="2e4aa-157">Los tipos conocidos `Timestamp` y `Duration` se representan en .NET como clases, por lo que no hay necesidad de una versión que acepte valores NULL.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes, so there's no need for a nullable version.</span></span> <span data-ttu-id="2e4aa-158">Pero es importante comprobar si hay valores NULL en las propiedades de esos tipos cuando se realiza la conversión en `DateTimeOffset` o `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-158">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="2e4aa-159">Decimals</span><span class="sxs-lookup"><span data-stu-id="2e4aa-159">Decimals</span></span>

<span data-ttu-id="2e4aa-160">Protobuf no admite de forma nativa el tipo de `decimal` .NET, simplemente `double` y `float`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-160">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="2e4aa-161">En el proyecto protobuf, hay una discusión en curso sobre la posibilidad de agregar un tipo de `Decimal` estándar a los tipos conocidos, con compatibilidad de plataforma para los lenguajes y marcos que lo admiten.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-161">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="2e4aa-162">Todavía no se ha implementado nada.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-162">Nothing has been implemented yet.</span></span>

<span data-ttu-id="2e4aa-163">Es posible crear una definición de mensaje para representar el tipo de `decimal` que funcionaría para la serialización segura entre clientes y servidores .NET.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-163">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="2e4aa-164">Sin embargo, los desarrolladores de otras plataformas tendrían que conocer el formato que se usa e implementar su propio control.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-164">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="2e4aa-165">Crear un tipo decimal personalizado para protobuf</span><span class="sxs-lookup"><span data-stu-id="2e4aa-165">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="2e4aa-166">Una implementación sencilla podría ser similar al tipo de `Money` no estándar que usan algunas API de Google, sin el campo `currency`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-166">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="2e4aa-167">El campo `nanos` representa los valores de `0.999_999_999` a `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-167">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="2e4aa-168">Por ejemplo, el valor de `decimal` `1.5m` se representaría como `{ units = 1, nanos = 500_000_000 }`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-168">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="2e4aa-169">Este es el motivo por el que el campo de `nanos` de este ejemplo usa el tipo de `sfixed32`, que codifica de forma más eficaz que `int32` para los valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-169">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="2e4aa-170">Si el campo `units` es negativo, el campo de `nanos` también debe ser negativo.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-170">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="2e4aa-171">Existen varios algoritmos para codificar los valores `decimal` como cadenas de bytes, pero este mensaje es más fácil de entender que cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-171">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="2e4aa-172">Los valores no se ven afectados por modos endian en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-172">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="2e4aa-173">La conversión entre este tipo y el tipo de `decimal` BCL podría implementarse de C# la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2e4aa-173">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="2e4aa-174">Siempre que use tipos de mensaje personalizados como este, *debe* documentarlos con comentarios en `.proto`.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-174">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="2e4aa-175">A continuación, otros desarrolladores pueden implementar la conversión a y desde el tipo equivalente en su propio lenguaje o marco.</span><span class="sxs-lookup"><span data-stu-id="2e4aa-175">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2e4aa-176">[Anterior](protobuf-messages.md)
>[Siguiente](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="2e4aa-176">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
