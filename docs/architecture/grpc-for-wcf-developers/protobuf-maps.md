---
title: 'Mapas de protobuf para diccionarios: gRPC para desarrolladores de WCF'
description: Aprenda a usar protobuf Maps para representar tipos de diccionario en .NET.
ms.date: 12/15/2020
ms.openlocfilehash: d38270d4bc320cf1f758080c18843ed1d716b350
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938551"
---
# <a name="protobuf-maps-for-dictionaries"></a><span data-ttu-id="a6742-103">Mapas de Protobuf para diccionarios</span><span class="sxs-lookup"><span data-stu-id="a6742-103">Protobuf maps for dictionaries</span></span>

<span data-ttu-id="a6742-104">Es importante poder representar colecciones arbitrarias de valores con nombre en los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a6742-104">It's important to be able to represent arbitrary collections of named values in messages.</span></span> <span data-ttu-id="a6742-105">En .NET, esta actividad se controla normalmente a través de los tipos de diccionario.</span><span class="sxs-lookup"><span data-stu-id="a6742-105">In .NET, this activity is commonly handled through dictionary types.</span></span> <span data-ttu-id="a6742-106">El equivalente del tipo .NET <xref:System.Collections.Generic.IDictionary%602> en el búfer de protocolo (protobuf) es el `map<key_type, value_type>` tipo.</span><span class="sxs-lookup"><span data-stu-id="a6742-106">The equivalent of the .NET <xref:System.Collections.Generic.IDictionary%602> type in Protocol Buffer (Protobuf) is the `map<key_type, value_type>` type.</span></span> <span data-ttu-id="a6742-107">En esta sección se muestra cómo declarar un `map` tipo en protobuf y cómo usar el código generado.</span><span class="sxs-lookup"><span data-stu-id="a6742-107">This section shows how to declare a `map` type in Protobuf, and how to use the generated code.</span></span>

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

<span data-ttu-id="a6742-108">En el código generado, `map` los campos se representan mediante propiedades de solo lectura del [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] tipo.</span><span class="sxs-lookup"><span data-stu-id="a6742-108">In the generated code, `map` fields are represented by read-only properties of the [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] type.</span></span> <span data-ttu-id="a6742-109">Este tipo implementa las interfaces de colección estándar de .NET, incluido <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="a6742-109">This type implements the standard .NET collection interfaces, including <xref:System.Collections.Generic.IDictionary%602>.</span></span>

<span data-ttu-id="a6742-110">Los campos de mapa no se pueden repetir directamente en una definición de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a6742-110">Map fields can't be directly repeated in a message definition.</span></span> <span data-ttu-id="a6742-111">Sin embargo, puede crear un mensaje anidado que contenga un mapa y usarlo `repeated` en el tipo de mensaje, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6742-111">But you can create a nested message that contains a map and use `repeated` on the message type, as in the following example:</span></span>

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a><span data-ttu-id="a6742-112">Usar las propiedades MapField en el código</span><span class="sxs-lookup"><span data-stu-id="a6742-112">Using MapField properties in code</span></span>

<span data-ttu-id="a6742-113">Las `MapField` propiedades generadas a partir de `map` campos son de solo lectura y nunca lo serán `null` .</span><span class="sxs-lookup"><span data-stu-id="a6742-113">The `MapField` properties generated from `map` fields are read-only, and will never be `null`.</span></span> <span data-ttu-id="a6742-114">Para establecer una propiedad de asignación, use el `Add(IDictionary<TKey,TValue> values)` método en la `MapField` propiedad Empty para copiar los valores de cualquier Diccionario de .net.</span><span class="sxs-lookup"><span data-stu-id="a6742-114">To set a map property, use the `Add(IDictionary<TKey,TValue> values)` method on the empty `MapField` property to copy values from any .NET dictionary.</span></span>

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a><span data-ttu-id="a6742-115">Lecturas adicionales</span><span class="sxs-lookup"><span data-stu-id="a6742-115">Further reading</span></span>

<span data-ttu-id="a6742-116">Para obtener más información sobre protobuf, consulte la [documentación](https://developers.google.com/protocol-buffers/docs/overview)oficial de protobuf.</span><span class="sxs-lookup"><span data-stu-id="a6742-116">For more information about Protobuf, see the official [Protobuf documentation](https://developers.google.com/protocol-buffers/docs/overview).</span></span>

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
><span data-ttu-id="a6742-117">[Anterior](protobuf-enums.md)
>[Siguiente](wcf-services-to-grpc-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="a6742-117">[Previous](protobuf-enums.md)
[Next](wcf-services-to-grpc-comparison.md)</span></span>
