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
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="9d33c-103">Tipos de datos escalares de Protobuf</span><span class="sxs-lookup"><span data-stu-id="9d33c-103">Protobuf scalar data types</span></span>

<span data-ttu-id="9d33c-104">El búfer de protocolo (protobuf) admite un intervalo de tipos de valores escalares nativos.</span><span class="sxs-lookup"><span data-stu-id="9d33c-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="9d33c-105">En la tabla siguiente se enumeran todos con su tipo C# equivalente:</span><span class="sxs-lookup"><span data-stu-id="9d33c-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="9d33c-106">Tipo de Protobuf</span><span class="sxs-lookup"><span data-stu-id="9d33c-106">Protobuf type</span></span> | <span data-ttu-id="9d33c-107">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="9d33c-107">C# type</span></span>      | <span data-ttu-id="9d33c-108">Notas</span><span class="sxs-lookup"><span data-stu-id="9d33c-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="9d33c-109">1</span><span class="sxs-lookup"><span data-stu-id="9d33c-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="9d33c-110">1</span><span class="sxs-lookup"><span data-stu-id="9d33c-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="9d33c-111">1</span><span class="sxs-lookup"><span data-stu-id="9d33c-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="9d33c-112">1</span><span class="sxs-lookup"><span data-stu-id="9d33c-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="9d33c-113">2</span><span class="sxs-lookup"><span data-stu-id="9d33c-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="9d33c-114">2</span><span class="sxs-lookup"><span data-stu-id="9d33c-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="9d33c-115">2</span><span class="sxs-lookup"><span data-stu-id="9d33c-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="9d33c-116">2</span><span class="sxs-lookup"><span data-stu-id="9d33c-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="9d33c-117">3</span><span class="sxs-lookup"><span data-stu-id="9d33c-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="9d33c-118">4</span><span class="sxs-lookup"><span data-stu-id="9d33c-118">4</span></span>     |

<span data-ttu-id="9d33c-119">Notas:</span><span class="sxs-lookup"><span data-stu-id="9d33c-119">Notes:</span></span>

1. <span data-ttu-id="9d33c-120">La codificación estándar para `int32` y `int64` es ineficaz cuando se trabaja con valores con signo.</span><span class="sxs-lookup"><span data-stu-id="9d33c-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="9d33c-121">Si es probable que el campo contenga números negativos, use `sint32` o `sint64` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9d33c-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="9d33c-122">Estos tipos se asignan a `int` los `long` tipos C# y, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9d33c-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="9d33c-123">Los `fixed` campos siempre utilizan el mismo número de bytes, independientemente de cuál sea el valor.</span><span class="sxs-lookup"><span data-stu-id="9d33c-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="9d33c-124">Este comportamiento hace que la serialización y la deserialización sean más rápidas para los valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="9d33c-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="9d33c-125">Las cadenas protobuf son codificadas con UTF-8 (o ASCII de 7 bits).</span><span class="sxs-lookup"><span data-stu-id="9d33c-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="9d33c-126">La longitud codificada no puede ser mayor que 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="9d33c-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="9d33c-127">El tiempo de ejecución de protobuf proporciona un `ByteString` tipo que se asigna fácilmente a las matrices de C# y desde ellas `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="9d33c-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="9d33c-128">Otros tipos primitivos de .NET</span><span class="sxs-lookup"><span data-stu-id="9d33c-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="9d33c-129">Fechas y horas</span><span class="sxs-lookup"><span data-stu-id="9d33c-129">Dates and times</span></span>

<span data-ttu-id="9d33c-130">Los tipos escalares nativos no proporcionan valores de fecha y hora, equivalentes a <xref:System.DateTimeOffset> , <xref:System.DateTime> y de C# <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="9d33c-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="9d33c-131">Puede especificar estos tipos mediante el uso de algunas de las extensiones de "tipos conocidos" de Google.</span><span class="sxs-lookup"><span data-stu-id="9d33c-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="9d33c-132">Estas extensiones proporcionan compatibilidad con el entorno de ejecución y la generación de código para los tipos de campo complejos en las plataformas admitidas.</span><span class="sxs-lookup"><span data-stu-id="9d33c-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="9d33c-133">En la tabla siguiente se muestran los tipos de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="9d33c-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="9d33c-134">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="9d33c-134">C# type</span></span> | <span data-ttu-id="9d33c-135">Tipo conocido de Protobuf</span><span class="sxs-lookup"><span data-stu-id="9d33c-135">Protobuf well-known type</span></span> |
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

<span data-ttu-id="9d33c-136">Las propiedades generadas en la clase C# no son los tipos de fecha y hora de .NET.</span><span class="sxs-lookup"><span data-stu-id="9d33c-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="9d33c-137">Las propiedades usan las clases `Timestamp` y `Duration` en el espacio de nombres `Google.Protobuf.WellKnownTypes`.</span><span class="sxs-lookup"><span data-stu-id="9d33c-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="9d33c-138">Estas clases proporcionan métodos para realizar conversiones a `DateTimeOffset`, `DateTime` y `TimeSpan`, y desde estas.</span><span class="sxs-lookup"><span data-stu-id="9d33c-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

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
> <span data-ttu-id="9d33c-139">El tipo `Timestamp` funciona con horas UTC.</span><span class="sxs-lookup"><span data-stu-id="9d33c-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="9d33c-140">Los valores `DateTimeOffset` siempre tienen un desplazamiento de cero, y la propiedad `DateTime.Kind` siempre es `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="9d33c-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="9d33c-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="9d33c-141">System.Guid</span></span>

<span data-ttu-id="9d33c-142">Protobuf no es compatible directamente con el <xref:System.Guid> tipo, conocido como `UUID` en otras plataformas.</span><span class="sxs-lookup"><span data-stu-id="9d33c-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="9d33c-143">No hay ningún tipo conocido para ella.</span><span class="sxs-lookup"><span data-stu-id="9d33c-143">There's no well-known type for it.</span></span>

<span data-ttu-id="9d33c-144">El mejor enfoque es controlar `Guid` los valores como un `string` campo, utilizando el `8-4-4-4-12` formato hexadecimal estándar (por ejemplo, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` ).</span><span class="sxs-lookup"><span data-stu-id="9d33c-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="9d33c-145">Todos los lenguajes y plataformas pueden analizar ese formato.</span><span class="sxs-lookup"><span data-stu-id="9d33c-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="9d33c-146">No use un `bytes` campo para `Guid` los valores.</span><span class="sxs-lookup"><span data-stu-id="9d33c-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="9d33c-147">Los problemas con *modos endian* ([definición de Wikipedia](https://en.wikipedia.org/wiki/Endianness)) pueden dar lugar a un comportamiento errático cuando protobuf interactúa con otras plataformas, como Java.</span><span class="sxs-lookup"><span data-stu-id="9d33c-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="9d33c-148">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="9d33c-148">Nullable types</span></span>

<span data-ttu-id="9d33c-149">La generación de código de Protobuf para C# usa los tipos nativos, como `int` para `int32`.</span><span class="sxs-lookup"><span data-stu-id="9d33c-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="9d33c-150">Por lo tanto, los valores siempre se incluyen y no pueden ser null.</span><span class="sxs-lookup"><span data-stu-id="9d33c-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="9d33c-151">En el caso de los valores que requieren valores NULL explícitos, como `int?` el uso de en el código de c#, los "tipos conocidos" de protobuf incluyen contenedores que se compilan en tipos de C# que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9d33c-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="9d33c-152">Para usarlos, importe `wrappers.proto` en el `.proto` archivo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9d33c-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="9d33c-153">Protobuf usará el simple `T?` (por ejemplo, `int?` ) para la propiedad de mensaje generada.</span><span class="sxs-lookup"><span data-stu-id="9d33c-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="9d33c-154">En la tabla siguiente se muestra la lista completa de tipos de contenedor con su tipo C# equivalente:</span><span class="sxs-lookup"><span data-stu-id="9d33c-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="9d33c-155">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="9d33c-155">C# type</span></span>   | <span data-ttu-id="9d33c-156">Contenedor de Tipo conocido</span><span class="sxs-lookup"><span data-stu-id="9d33c-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="9d33c-157">Los tipos conocidos `Timestamp` y `Duration` se representan en .net como clases.</span><span class="sxs-lookup"><span data-stu-id="9d33c-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="9d33c-158">En C# 8 y versiones posteriores, puede usar tipos de referencia que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9d33c-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="9d33c-159">Pero es importante comprobar si hay valores NULL en las propiedades de esos tipos cuando se realiza la conversión a `DateTimeOffset` o `TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="9d33c-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="9d33c-160">Decimals</span><span class="sxs-lookup"><span data-stu-id="9d33c-160">Decimals</span></span>

<span data-ttu-id="9d33c-161">Protobuf no admite de forma nativa el tipo `decimal` de .NET, solo `double` y `float`.</span><span class="sxs-lookup"><span data-stu-id="9d33c-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="9d33c-162">En el proyecto protobuf, hay una discusión en curso sobre la posibilidad de agregar un `Decimal` tipo estándar a los tipos conocidos, con compatibilidad de plataforma para los lenguajes y marcos que lo admiten.</span><span class="sxs-lookup"><span data-stu-id="9d33c-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="9d33c-163">Todavía no se ha implementado nada.</span><span class="sxs-lookup"><span data-stu-id="9d33c-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="9d33c-164">Es posible crear una definición de mensaje para representar el `decimal` tipo que funcionaría para la serialización segura entre clientes y servidores .net.</span><span class="sxs-lookup"><span data-stu-id="9d33c-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="9d33c-165">Sin embargo, los desarrolladores de otras plataformas tendrían que conocer el formato que se usa e implementar su propio control.</span><span class="sxs-lookup"><span data-stu-id="9d33c-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="9d33c-166">Creación de un tipo decimal personalizado para Protobuf</span><span class="sxs-lookup"><span data-stu-id="9d33c-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="9d33c-167">Una implementación sencilla podría ser similar al `Money` tipo no estándar que usan algunas API de Google, sin el `currency` campo.</span><span class="sxs-lookup"><span data-stu-id="9d33c-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

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

<span data-ttu-id="9d33c-168">El campo `nanos` representa los valores de `0.999_999_999` a `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="9d33c-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="9d33c-169">Por ejemplo, el valor `decimal` `1.5m` se representaría como `{ units = 1, nanos = 500_000_000 }`.</span><span class="sxs-lookup"><span data-stu-id="9d33c-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="9d33c-170">Este es el motivo por el que el campo `nanos` de este ejemplo usa el tipo `sfixed32`, que codifica de forma más eficaz que `int32` para los valores más grandes.</span><span class="sxs-lookup"><span data-stu-id="9d33c-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="9d33c-171">Si el campo `units` es negativo, el campo `nanos` también debe serlo.</span><span class="sxs-lookup"><span data-stu-id="9d33c-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="9d33c-172">Existen varios algoritmos para codificar los valores `decimal` como cadenas de bytes, pero este mensaje es más fácil de entender que cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="9d33c-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="9d33c-173">Los valores no se ven afectados por modos endian en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="9d33c-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="9d33c-174">La conversión entre este tipo y el tipo `decimal` de BCL podría implementarse en C# de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9d33c-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

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
> <span data-ttu-id="9d33c-175">Siempre que use tipos de mensaje personalizados como este, *debe* documentarlos con comentarios en `.proto` .</span><span class="sxs-lookup"><span data-stu-id="9d33c-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="9d33c-176">A continuación, otros desarrolladores pueden implementar la conversión a y desde el tipo equivalente en su propio lenguaje o marco.</span><span class="sxs-lookup"><span data-stu-id="9d33c-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9d33c-177">[Anterior](protobuf-messages.md)
>[Siguiente](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="9d33c-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
