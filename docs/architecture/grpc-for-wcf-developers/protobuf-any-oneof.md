---
title: Protobuf any y de Fields for Variant Types-gRPC for WCF Developers
description: Aprenda a usar el tipo any y la palabra clave de para representar los tipos de objeto Variant en los mensajes.
ms.date: 09/09/2019
ms.openlocfilehash: af3ba22c238aa80a8c6119f62d5d8914770cad68
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971613"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a><span data-ttu-id="5843e-103">Protobuf todos los campos y de para los tipos Variant</span><span class="sxs-lookup"><span data-stu-id="5843e-103">Protobuf Any and Oneof fields for variant types</span></span>

<span data-ttu-id="5843e-104">El control de los tipos de propiedades dinámicas (es decir, las propiedades de tipo `object`) en WCF es complicado.</span><span class="sxs-lookup"><span data-stu-id="5843e-104">Handling dynamic property types (that is, properties of type `object`) in WCF is complicated.</span></span> <span data-ttu-id="5843e-105">Se deben especificar los serializadores, se deben proporcionar los atributos [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) , etc.</span><span class="sxs-lookup"><span data-stu-id="5843e-105">Serializers must be specified, [KnownType](xref:System.Runtime.Serialization.KnownTypeAttribute) attributes must be provided, and so on.</span></span>

<span data-ttu-id="5843e-106">Protobuf proporciona dos opciones más sencillas para tratar con valores que pueden ser de más de un tipo.</span><span class="sxs-lookup"><span data-stu-id="5843e-106">Protobuf provides two simpler options for dealing with values that may be of more than one type.</span></span> <span data-ttu-id="5843e-107">El tipo de `Any` puede representar cualquier tipo de mensaje conocido de protobuf, mientras que la palabra clave `oneof` permite especificar que solo se puede establecer un intervalo de campos en un mensaje determinado.</span><span class="sxs-lookup"><span data-stu-id="5843e-107">The `Any` type can represent any known Protobuf message type, while the `oneof` keyword allows you to specify that only one of a range of fields can be set in any given message.</span></span>

## <a name="any"></a><span data-ttu-id="5843e-108">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="5843e-108">Any</span></span>

<span data-ttu-id="5843e-109">`Any` es uno de los "tipos conocidos" de protobuf: una colección de tipos de mensajes útiles y reutilizables con implementaciones en todos los idiomas admitidos.</span><span class="sxs-lookup"><span data-stu-id="5843e-109">`Any` is one of Protobuf's "well-known types": a collection of useful, reusable message types with implementations in all supported languages.</span></span> <span data-ttu-id="5843e-110">Para usar el tipo de `Any`, debe importar la definición de `google/protobuf/any.proto`.</span><span class="sxs-lookup"><span data-stu-id="5843e-110">To use the `Any` type, you must import the `google/protobuf/any.proto` definition.</span></span>

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

<span data-ttu-id="5843e-111">En el C# código, la clase `Any` proporciona métodos para establecer el campo, extraer el mensaje y comprobar el tipo.</span><span class="sxs-lookup"><span data-stu-id="5843e-111">In the C# code, the `Any` class provides methods for setting the field, extracting the message, and checking the type.</span></span>

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

<span data-ttu-id="5843e-112">El código de reflexión interno de protobuf usa el campo estático `Descriptor` en cada tipo generado para resolver `Any` tipos de campo.</span><span class="sxs-lookup"><span data-stu-id="5843e-112">The `Descriptor` static field on each generated type is used by Protobuf's internal reflection code to resolve `Any` field types.</span></span> <span data-ttu-id="5843e-113">También hay un método `TryUnpack<T>`, pero que crea una instancia no inicializada de `T` incluso cuando se produce un error, por lo que es mejor usar el método `Is` tal y como se mostró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5843e-113">There's also a `TryUnpack<T>` method, but that creates an uninitialized instance of `T` even when it fails, so it's better to use the `Is` method as shown above.</span></span>

## <a name="oneof"></a><span data-ttu-id="5843e-114">De</span><span class="sxs-lookup"><span data-stu-id="5843e-114">Oneof</span></span>

<span data-ttu-id="5843e-115">Los campos de de son una característica de lenguaje: el compilador controla la palabra clave `oneof` cuando genera la clase de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5843e-115">Oneof fields are a language feature: the `oneof` keyword is handled by the compiler when it generates the message class.</span></span> <span data-ttu-id="5843e-116">El uso de `oneof` para especificar el mensaje de `ChangeNotification` podría ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5843e-116">Using `oneof` to specify the `ChangeNotification` message might look like this:</span></span>

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

<span data-ttu-id="5843e-117">Los campos del conjunto de `oneof` deben tener números de campo únicos dentro de la declaración de mensaje global.</span><span class="sxs-lookup"><span data-stu-id="5843e-117">Fields within the `oneof` set must have unique field numbers within the overall message declaration.</span></span>

<span data-ttu-id="5843e-118">Cuando se usa `oneof`, el código C# generado incluye una enumeración que especifica cuál de los campos se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="5843e-118">When you use `oneof`, the generated C# code includes an enum that specifies which of the fields has been set.</span></span> <span data-ttu-id="5843e-119">Puede probar la enumeración para buscar el campo que se establece.</span><span class="sxs-lookup"><span data-stu-id="5843e-119">You can test the enum to find which field is set.</span></span> <span data-ttu-id="5843e-120">Los campos que no se establecen devuelven `null` o el valor predeterminado, en lugar de producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="5843e-120">Fields that aren't set return `null` or the default value, rather than throwing an exception.</span></span>

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

<span data-ttu-id="5843e-121">Al establecer cualquier campo que forme parte de un conjunto de `oneof` se borrarán automáticamente los demás campos del conjunto.</span><span class="sxs-lookup"><span data-stu-id="5843e-121">Setting any field that is part of a `oneof` set will automatically clear any other fields in the set.</span></span> <span data-ttu-id="5843e-122">No se puede usar `repeated` con `oneof`.</span><span class="sxs-lookup"><span data-stu-id="5843e-122">You can't use `repeated` with `oneof`.</span></span> <span data-ttu-id="5843e-123">En su lugar, puede crear un mensaje anidado con el campo repetido o el `oneof` establecido para evitar esta limitación.</span><span class="sxs-lookup"><span data-stu-id="5843e-123">Instead, you can create a nested message with either the repeated field or the `oneof` set to work around this limitation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5843e-124">[Anterior](protobuf-reserved.md)
>[Siguiente](protobuf-enums.md)</span><span class="sxs-lookup"><span data-stu-id="5843e-124">[Previous](protobuf-reserved.md)
[Next](protobuf-enums.md)</span></span>
