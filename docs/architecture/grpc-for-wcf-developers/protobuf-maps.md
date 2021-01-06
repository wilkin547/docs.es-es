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
# <a name="protobuf-maps-for-dictionaries"></a>Mapas de Protobuf para diccionarios

Es importante poder representar colecciones arbitrarias de valores con nombre en los mensajes. En .NET, esta actividad se controla normalmente a través de los tipos de diccionario. El equivalente del tipo .NET <xref:System.Collections.Generic.IDictionary%602> en el búfer de protocolo (protobuf) es el `map<key_type, value_type>` tipo. En esta sección se muestra cómo declarar un `map` tipo en protobuf y cómo usar el código generado.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

En el código generado, `map` los campos se representan mediante propiedades de solo lectura del [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] tipo. Este tipo implementa las interfaces de colección estándar de .NET, incluido <xref:System.Collections.Generic.IDictionary%602> .

Los campos de mapa no se pueden repetir directamente en una definición de mensaje. Sin embargo, puede crear un mensaje anidado que contenga un mapa y usarlo `repeated` en el tipo de mensaje, como en el ejemplo siguiente:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Usar las propiedades MapField en el código

Las `MapField` propiedades generadas a partir de `map` campos son de solo lectura y nunca lo serán `null` . Para establecer una propiedad de asignación, use el `Add(IDictionary<TKey,TValue> values)` método en la `MapField` propiedad Empty para copiar los valores de cualquier Diccionario de .net.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Lecturas adicionales

Para obtener más información sobre protobuf, consulte la [documentación](https://developers.google.com/protocol-buffers/docs/overview)oficial de protobuf.

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
>[Anterior](protobuf-enums.md)
>[Siguiente](wcf-services-to-grpc-comparison.md)
