---
title: 'Mapas de protobuf para diccionarios: gRPC para desarrolladores de WCF'
description: Aprenda a usar protobuf Maps para representar. Tipos de Diccionario de la red.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: aef6b0f378e7a63f362ec42642cae15b32d49a08
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841454"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="5f7c5-103">Mapas de Protobuf para diccionarios</span><span class="sxs-lookup"><span data-stu-id="5f7c5-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="5f7c5-104">Es importante poder representar colecciones arbitrarias de valores con nombre en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="5f7c5-105">En .NET, esto se controla normalmente mediante tipos de diccionario.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-105">In .NET this is commonly handled using dictionary types.</span></span> <span data-ttu-id="5f7c5-106">El equivalente de protobuf del tipo de <xref:System.Collections.Generic.IDictionary%602> de .NET es el tipo de `map<key_type, value_type>`.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-106">Protobuf's equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="5f7c5-107">En esta sección se muestra cómo declarar un `map` en protobuf y cómo usar el código generado.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-107">This section shows how to declare a `map` in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="5f7c5-108">En el código generado, `map` campos utilizan la clase `Google.Protobuf.Collections.MapField<TKey, TValue>`, que implementa las interfaces de colección estándar de .NET, incluido <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-108">In the generated code, `map` fields use the `Google.Protobuf.Collections.MapField<TKey, TValue>` class, which implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="5f7c5-109">Los campos de mapa no se pueden repetir directamente en una definición de mensaje, pero puede crear un mensaje anidado que contenga una asignación y usar `repeated` en el tipo de mensaje, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f7c5-109">Map fields can't be directly repeated in a message definition, but you can create a nested message containing a map and use `repeated` on the message type, like in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="5f7c5-110">Usar las propiedades MapField en el código</span><span class="sxs-lookup"><span data-stu-id="5f7c5-110">Using MapField properties in code</span></span>

<span data-ttu-id="5f7c5-111">Las `MapField` propiedades generadas a partir de `map` campos son de solo lectura y nunca se `null`.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-111">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="5f7c5-112">Para establecer una propiedad de asignación, use el método `Add(IDictionary<TKey,TValue> values)` en la propiedad `MapField` vacía para copiar los valores de cualquier Diccionario .NET.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-112">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="5f7c5-113">Información adicional</span><span class="sxs-lookup"><span data-stu-id="5f7c5-113">Further reading</span></span>

<span data-ttu-id="5f7c5-114">Para obtener más información sobre protobuf, consulte la [documentación](https://developers.google.com/protocol-buffers/docs/overview)oficial de protobuf.</span><span class="sxs-lookup"><span data-stu-id="5f7c5-114">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5f7c5-115">[Anterior](protobuf-enums.md)
>[Siguiente](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="5f7c5-115">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
