---
title: Tipos de datos escalares de Protobuf - gRPC para desarrolladores de WCF
description: Obtenga información sobre los tipos de datos básicos y conocidos que protobuf y gRPC admiten en .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: ea3b53426ecf6f50f3bae22a537e227b07248508
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249440"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="9d7a1-103">Tipos de datos escalares de Protobuf</span><span class="sxs-lookup"><span data-stu-id="9d7a1-103">Protobuf scalar data types</span></span>

<span data-ttu-id="9d7a1-104">El búfer de protocolo (Protobuf) admite un intervalo de tipos de valor escalar nativos.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="9d7a1-105">En la tabla siguiente se enumeran todos ellos con su tipo equivalente de C-:</span><span class="sxs-lookup"><span data-stu-id="9d7a1-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="9d7a1-106">Tipo de protobuf</span><span class="sxs-lookup"><span data-stu-id="9d7a1-106">Protobuf type</span></span> | <span data-ttu-id="9d7a1-107">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="9d7a1-107">C# type</span></span>      | <span data-ttu-id="9d7a1-108">Notas</span><span class="sxs-lookup"><span data-stu-id="9d7a1-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="9d7a1-109">1</span><span class="sxs-lookup"><span data-stu-id="9d7a1-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="9d7a1-110">1</span><span class="sxs-lookup"><span data-stu-id="9d7a1-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="9d7a1-111">1</span><span class="sxs-lookup"><span data-stu-id="9d7a1-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="9d7a1-112">1</span><span class="sxs-lookup"><span data-stu-id="9d7a1-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="9d7a1-113">2</span><span class="sxs-lookup"><span data-stu-id="9d7a1-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="9d7a1-114">2</span><span class="sxs-lookup"><span data-stu-id="9d7a1-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="9d7a1-115">2</span><span class="sxs-lookup"><span data-stu-id="9d7a1-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="9d7a1-116">2</span><span class="sxs-lookup"><span data-stu-id="9d7a1-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="9d7a1-117">3</span><span class="sxs-lookup"><span data-stu-id="9d7a1-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="9d7a1-118">4</span><span class="sxs-lookup"><span data-stu-id="9d7a1-118">4</span></span>     |

<span data-ttu-id="9d7a1-119">Notas:</span><span class="sxs-lookup"><span data-stu-id="9d7a1-119">Notes:</span></span>

1. <span data-ttu-id="9d7a1-120">La codificación `int32` `int64` estándar para y es ineficiente cuando se trabaja con valores firmados.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="9d7a1-121">Si es probable que el campo `sint32` `sint64` contenga números negativos, úselo o en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="9d7a1-122">Estos tipos se asignan `int` `long` a los tipos y C- y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="9d7a1-123">Los `fixed` campos siempre utilizan el mismo número de bytes independientemente del valor.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="9d7a1-124">Este comportamiento hace que la serialización y la deserialización sean más rápidas para valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="9d7a1-125">Las cadenas Protobuf están codificadas en UTF-8 (o ASCII de 7 bits).</span><span class="sxs-lookup"><span data-stu-id="9d7a1-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="9d7a1-126">La longitud codificada no puede ser mayor que 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="9d7a1-127">El tiempo de ejecución `ByteString` de Protobuf proporciona `byte[]` un tipo que se asigna fácilmente hacia y desde matrices de C.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="9d7a1-128">Otros tipos primitivos de .NET</span><span class="sxs-lookup"><span data-stu-id="9d7a1-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="9d7a1-129">Fechas y horas</span><span class="sxs-lookup"><span data-stu-id="9d7a1-129">Dates and times</span></span>

<span data-ttu-id="9d7a1-130">Los tipos escalares nativos no proporcionan valores de fecha y <xref:System.DateTimeOffset>hora, equivalentes a Los valores de C's , <xref:System.DateTime>, y <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="9d7a1-131">Puede especificar estos tipos mediante algunas de las extensiones "Tipos bien conocidos" de Google.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="9d7a1-132">Estas extensiones proporcionan compatibilidad de generación de código y tiempo de ejecución para tipos de campo complejos en las plataformas admitidas.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="9d7a1-133">En la tabla siguiente se muestran los tipos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="9d7a1-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="9d7a1-134">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="9d7a1-134">C# type</span></span> | <span data-ttu-id="9d7a1-135">Tipo conocido de Protobuf</span><span class="sxs-lookup"><span data-stu-id="9d7a1-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="9d7a1-136">Las propiedades generadas en la clase de C- no son los tipos de fecha y hora de .NET.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="9d7a1-137">Las propiedades `Timestamp` usan `Duration` las `Google.Protobuf.WellKnownTypes` clases y del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="9d7a1-138">Estas clases proporcionan métodos `DateTimeOffset`para `DateTime`convertir `TimeSpan`a , , y .</span><span class="sxs-lookup"><span data-stu-id="9d7a1-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="9d7a1-139">El `Timestamp` tipo funciona con las horas UTC.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="9d7a1-140">`DateTimeOffset`los valores siempre tienen un `DateTime.Kind` desplazamiento de `DateTimeKind.Utc`cero y la propiedad siempre es .</span><span class="sxs-lookup"><span data-stu-id="9d7a1-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="9d7a1-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="9d7a1-141">System.Guid</span></span>

<span data-ttu-id="9d7a1-142">Protobuf no admite directamente el <xref:System.Guid> `UUID` tipo, conocido como en otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="9d7a1-143">No hay ningún tipo conocido para ello.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-143">There's no well-known type for it.</span></span>

<span data-ttu-id="9d7a1-144">El mejor enfoque `Guid` es controlar `string` los valores como `8-4-4-4-12` un campo, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`utilizando el formato hexadecimal estándar (por ejemplo, ).</span><span class="sxs-lookup"><span data-stu-id="9d7a1-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="9d7a1-145">Todos los idiomas y plataformas pueden analizar ese formato.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="9d7a1-146">No use un `bytes` campo `Guid` para los valores.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="9d7a1-147">Los problemas con *la endianidad* [(definición](https://en.wikipedia.org/wiki/Endianness)de Wikipedia) pueden dar lugar a un comportamiento errático cuando Protobuf está interactuando con otras plataformas, como Java.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="9d7a1-148">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="9d7a1-148">Nullable types</span></span>

<span data-ttu-id="9d7a1-149">La generación de código Protobuf para C- usa los tipos nativos, como `int` para `int32`.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="9d7a1-150">Por lo tanto, los valores siempre se incluyen y no pueden ser null.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="9d7a1-151">En el caso de los `int?` valores que requieren null explícito, como el uso en el código de C, los "Tipos bien conocidos" de Protobuf incluyen contenedores que se compilan en tipos de C.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="9d7a1-152">Para usarlos, `wrappers.proto` importe `.proto` en su archivo, así:</span><span class="sxs-lookup"><span data-stu-id="9d7a1-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="9d7a1-153">Protobuf usará la `T?` simple (por ejemplo, `int?`) para la propiedad de mensaje generada.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="9d7a1-154">En la tabla siguiente se muestra la lista completa de tipos de contenedor con su tipo equivalente de C-:</span><span class="sxs-lookup"><span data-stu-id="9d7a1-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="9d7a1-155">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="9d7a1-155">C# type</span></span>   | <span data-ttu-id="9d7a1-156">Envoltura de tipo bien conocido</span><span class="sxs-lookup"><span data-stu-id="9d7a1-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="9d7a1-157">Los tipos `Timestamp` conocidos `Duration` y se representan en .NET como clases.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="9d7a1-158">En C-8 y posteriores, puede usar tipos de referencia que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="9d7a1-159">Pero es importante comprobar si es null en las propiedades de `DateTimeOffset` `TimeSpan`esos tipos cuando se convierte a o .</span><span class="sxs-lookup"><span data-stu-id="9d7a1-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="9d7a1-160">Decimals</span><span class="sxs-lookup"><span data-stu-id="9d7a1-160">Decimals</span></span>

<span data-ttu-id="9d7a1-161">Protobuf no admite de forma `decimal` nativa el `double` `float`tipo .NET, solo y .</span><span class="sxs-lookup"><span data-stu-id="9d7a1-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="9d7a1-162">Hay una discusión en curso en el proyecto Protobuf sobre la posibilidad de agregar un tipo estándar `Decimal` a los tipos conocidos, con soporte de plataforma para lenguajes y marcos que lo admiten.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="9d7a1-163">Aún no se ha implementado nada.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="9d7a1-164">Es posible crear una definición de `decimal` mensaje para representar el tipo que funcionaría para la serialización segura entre clientes y servidores .NET.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="9d7a1-165">Pero los desarrolladores de otras plataformas tendrían que entender el formato que se está utilizando e implementar su propio manejo para él.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="9d7a1-166">Creación de un tipo decimal personalizado para Protobuf</span><span class="sxs-lookup"><span data-stu-id="9d7a1-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="9d7a1-167">Una implementación simple podría ser `Money` similar al tipo no estándar `currency` que usan algunas API de Google, sin el campo.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="9d7a1-168">El `nanos` campo representa `0.999_999_999` valores `-0.999_999_999`de to .</span><span class="sxs-lookup"><span data-stu-id="9d7a1-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="9d7a1-169">Por ejemplo, `decimal` `1.5m` el valor se `{ units = 1, nanos = 500_000_000 }`representaría como .</span><span class="sxs-lookup"><span data-stu-id="9d7a1-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="9d7a1-170">Esta es `nanos` la razón por `sfixed32` la que el campo `int32` de este ejemplo utiliza el tipo, que codifica más eficazmente que para valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="9d7a1-171">Si `units` el campo es `nanos` negativo, el campo también debe ser negativo.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="9d7a1-172">Hay varios otros algoritmos `decimal` para codificar valores como cadenas de bytes, pero este mensaje es más fácil de entender que cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="9d7a1-173">Los valores no se ven afectados por la endianidad en diversas plataformas.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="9d7a1-174">La conversión entre este `decimal` tipo y el tipo DeBCL podría implementarse en C- de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9d7a1-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="9d7a1-175">Siempre que utilice tipos de *must* mensajes personalizados como `.proto`este, debe documentarlos con comentarios en .</span><span class="sxs-lookup"><span data-stu-id="9d7a1-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="9d7a1-176">A continuación, otros desarrolladores pueden implementar la conversión hacia y desde el tipo equivalente en su propio lenguaje o marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9d7a1-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9d7a1-177">[Anterior](protobuf-messages.md)
>[Siguiente](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="9d7a1-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
