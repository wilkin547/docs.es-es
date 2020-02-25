---
title: Protobuf any y de Fields for Variant Types-gRPC for WCF Developers
description: Aprenda a usar el tipo any y la palabra clave de para representar los tipos de objeto Variant en los mensajes.
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543201"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="94e55-103">Protobuf todos los campos y de para los tipos Variant</span><span class="sxs-lookup"><span data-stu-id="94e55-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="94e55-104">Controlar los tipos de propiedades dinámicas (es decir, las propiedades de tipo `object`) en Windows Communication Foundation (WCF) es complicado.</span><span class="sxs-lookup"><span data-stu-id="94e55-104">Handling dynamic property types (that is, properties of type `object`) in Windows Communication Foundation (WCF) is complicated.</span></span> <span data-ttu-id="94e55-105">Por ejemplo, debe especificar los serializadores y proporcionar los atributos [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) .</span><span class="sxs-lookup"><span data-stu-id="94e55-105">For example, you must specify serializers and provide [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes.</span></span>

<span data-ttu-id="94e55-106">El búfer de protocolo (protobuf) proporciona dos opciones más sencillas para tratar con valores que pueden ser de más de un tipo.</span><span class="sxs-lookup"><span data-stu-id="94e55-106">Protocol Buffer (Protobuf) provides two simpler options for dealing with values that might be of more than one type.</span></span> <span data-ttu-id="94e55-107">El tipo de `Any` puede representar cualquier tipo de mensaje protobuf conocido.</span><span class="sxs-lookup"><span data-stu-id="94e55-107">The `Any` type can represent any known Protobuf message type.</span></span> <span data-ttu-id="94e55-108">Y puede utilizar la palabra clave `oneof` para especificar que solo se puede establecer un intervalo de campos en cualquier mensaje.</span><span class="sxs-lookup"><span data-stu-id="94e55-108">And you can use the `oneof` keyword to specify that only one of a range of fields can be set in any message.</span></span>

## <a name="any"></a><span data-ttu-id="94e55-109">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="94e55-109">Any</span></span>

<span data-ttu-id="94e55-110">`Any` es uno de los "tipos conocidos" de protobuf: una colección de tipos de mensajes útiles y reutilizables con implementaciones en todos los idiomas admitidos.</span><span class="sxs-lookup"><span data-stu-id="94e55-110">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="94e55-111">Para usar el tipo de `Any`, debe importar la definición de `google/protobuf/any.proto`.</span><span class="sxs-lookup"><span data-stu-id="94e55-111">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

<span data-ttu-id="94e55-112">En el C# código, la clase `Any` proporciona métodos para establecer el campo, extraer el mensaje y comprobar el tipo.</span><span class="sxs-lookup"><span data-stu-id="94e55-112">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="94e55-113">El código de reflexión interno de protobuf usa el `Descriptor` campo estático en cada tipo generado para resolver `Any` tipos de campo.</span><span class="sxs-lookup"><span data-stu-id="94e55-113">Protobuf's internal reflection code uses the `Descriptor` static field on each generated type to resolve `Any` field types.</span></span> <span data-ttu-id="94e55-114">También hay un método `TryUnpack<T>`, pero que crea una instancia no inicializada de `T` incluso cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="94e55-114">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails.</span></span> <span data-ttu-id="94e55-115">Es mejor usar el método `Is` tal y como se mostró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="94e55-115">It's better to use the `Is` method as shown earlier.</span></span>

## <a name="oneof"></a><span data-ttu-id="94e55-116">De</span><span class="sxs-lookup"><span data-stu-id="94e55-116">Oneof</span></span>

<span data-ttu-id="94e55-117">Los campos de de son una característica de lenguaje: el compilador controla la palabra clave `oneof` cuando genera la clase de mensaje.</span><span class="sxs-lookup"><span data-stu-id="94e55-117">Oneof fields are a language feature: the compiler handles the `oneof` keyword when it generates the message class.</span></span> <span data-ttu-id="94e55-118">El uso de `oneof` para especificar el mensaje de `ChangeNotification` podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="94e55-118">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

<span data-ttu-id="94e55-119">Los campos del conjunto de `oneof` deben tener números de campo únicos en la declaración de mensaje global.</span><span class="sxs-lookup"><span data-stu-id="94e55-119">Fields within the `oneof` set must have unique field numbers in the overall message declaration.</span></span>

<span data-ttu-id="94e55-120">Cuando se usa `oneof`, el código C# generado incluye una enumeración que especifica cuál de los campos se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="94e55-120">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="94e55-121">Puede probar la enumeración para buscar el campo que se establece.</span><span class="sxs-lookup"><span data-stu-id="94e55-121">You can test the enum to find which field is set.</span></span> <span data-ttu-id="94e55-122">Los campos que no se establecen devuelven `null` o el valor predeterminado, en lugar de producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="94e55-122">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

<span data-ttu-id="94e55-123">Al establecer cualquier campo que forme parte de un conjunto de `oneof` se borrarán automáticamente los demás campos del conjunto.</span><span class="sxs-lookup"><span data-stu-id="94e55-123">Setting any field that's part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="94e55-124">No se puede usar `repeated` con `oneof`.</span><span class="sxs-lookup"><span data-stu-id="94e55-124">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="94e55-125">En su lugar, puede crear un mensaje anidado con el campo repetido o el `oneof` establecido para evitar esta limitación.</span><span class="sxs-lookup"><span data-stu-id="94e55-125">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="94e55-126">[Anterior](protobuf-reserved.md)
>[Siguiente](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="94e55-126">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
