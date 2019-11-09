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
# <a name="protobuf-maps-for-dictionaries"></a>Mapas de Protobuf para diccionarios

Es importante poder representar colecciones arbitrarias de valores con nombre en los mensajes. En .NET, esto se controla normalmente mediante tipos de diccionario. El equivalente de protobuf del tipo de <xref:System.Collections.Generic.IDictionary%602> de .NET es el tipo de `map<key_type, value_type>`. En esta sección se muestra cómo declarar un `map` en protobuf y cómo usar el código generado.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

En el código generado, `map` campos utilizan la clase `Google.Protobuf.Collections.MapField<TKey, TValue>`, que implementa las interfaces de colección estándar de .NET, incluido <xref:System.Collections.Generic.IDictionary%602>.

Los campos de mapa no se pueden repetir directamente en una definición de mensaje, pero puede crear un mensaje anidado que contenga una asignación y usar `repeated` en el tipo de mensaje, como en el ejemplo siguiente:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Usar las propiedades MapField en el código

Las `MapField` propiedades generadas a partir de `map` campos son de solo lectura y nunca se `null`. Para establecer una propiedad de asignación, use el método `Add(IDictionary<TKey,TValue> values)` en la propiedad `MapField` vacía para copiar los valores de cualquier Diccionario .NET.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Información adicional

Para obtener más información sobre protobuf, consulte la [documentación](https://developers.google.com/protocol-buffers/docs/overview)oficial de protobuf.

>[!div class="step-by-step"]
>[Anterior](protobuf-enums.md)
>[Siguiente](wcf-services-to-grpc-comparison.md)
