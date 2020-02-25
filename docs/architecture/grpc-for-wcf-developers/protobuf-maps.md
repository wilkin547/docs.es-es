---
title: 'Mapas de protobuf para diccionarios: gRPC para desarrolladores de WCF'
description: Aprenda a usar protobuf Maps para representar tipos de diccionario en .NET.
ms.date: 09/09/2019
ms.openlocfilehash: bf848bbc7e3618f6d78e280fcd85d5eb88d5cfae
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543136"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="33d36-103">Mapas de Protobuf para diccionarios</span><span class="sxs-lookup"><span data-stu-id="33d36-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="33d36-104">Es importante poder representar colecciones arbitrarias de valores con nombre en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="33d36-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="33d36-105">En .NET, esto se controla normalmente a través de los tipos de diccionario.</span><span class="sxs-lookup"><span data-stu-id="33d36-105">In .NET, this is commonly handled through dictionary types.</span></span> <span data-ttu-id="33d36-106">El equivalente del tipo de <xref:System.Collections.Generic.IDictionary%602> de .NET en el búfer de protocolo (protobuf) es el tipo de `map<key_type, value_type>`.</span><span class="sxs-lookup"><span data-stu-id="33d36-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="33d36-107">En esta sección se muestra cómo declarar un tipo de `map` en protobuf y cómo usar el código generado.</span><span class="sxs-lookup"><span data-stu-id="33d36-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="33d36-108">En el código generado, `map` campos utilizan la clase `Google.Protobuf.Collections.MapField<TKey, TValue>`.</span><span class="sxs-lookup"><span data-stu-id="33d36-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class.</span></span> <span data-ttu-id="33d36-109">Esta clase implementa las interfaces de colección estándar de .NET, incluido <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="33d36-109">This class implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="33d36-110">Los campos de mapa no se pueden repetir directamente en una definición de mensaje.</span><span class="sxs-lookup"><span data-stu-id="33d36-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="33d36-111">Sin embargo, puede crear un mensaje anidado que contenga una asignación y usar `repeated` en el tipo de mensaje, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33d36-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="33d36-112">Usar las propiedades MapField en el código</span><span class="sxs-lookup"><span data-stu-id="33d36-112">Using MapField properties in code</span></span>

<span data-ttu-id="33d36-113">Las `MapField` propiedades generadas a partir de `map` campos son de solo lectura y nunca se `null`.</span><span class="sxs-lookup"><span data-stu-id="33d36-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="33d36-114">Para establecer una propiedad de asignación, use el método `Add(IDictionary<TKey,TValue> values)` en la propiedad `MapField` vacía para copiar los valores de cualquier Diccionario .NET.</span><span class="sxs-lookup"><span data-stu-id="33d36-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="33d36-115">Lecturas adicionales</span><span class="sxs-lookup"><span data-stu-id="33d36-115">Further reading</span></span>

<span data-ttu-id="33d36-116">Para obtener más información sobre protobuf, consulte la [documentación](https://developers.google.com/protocol-buffers/docs/overview)oficial de protobuf.</span><span class="sxs-lookup"><span data-stu-id="33d36-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="33d36-117">[Anterior](protobuf-enums.md)
>[Siguiente](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="33d36-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
