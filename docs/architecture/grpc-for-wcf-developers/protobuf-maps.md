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
# <a name="protobuf-maps-for-dictionaries"></a>Mapas de Protobuf para diccionarios

Es importante poder representar colecciones arbitrarias de valores con nombre en los mensajes. En .NET, esto se controla normalmente a través de los tipos de diccionario. El equivalente del tipo de <xref:System.Collections.Generic.IDictionary%602> de .NET en el búfer de protocolo (protobuf) es el tipo de `map<key_type, value_type>`. En esta sección se muestra cómo declarar un tipo de `map` en protobuf y cómo usar el código generado.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

En el código generado, `map` campos utilizan la clase `Google.Protobuf.Collections.MapField<TKey, TValue>`. Esta clase implementa las interfaces de colección estándar de .NET, incluido <xref:System.Collections.Generic.IDictionary%602>.

Los campos de mapa no se pueden repetir directamente en una definición de mensaje. Sin embargo, puede crear un mensaje anidado que contenga una asignación y usar `repeated` en el tipo de mensaje, como en el ejemplo siguiente:

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

## <a name="further-reading"></a>Lecturas adicionales

Para obtener más información sobre protobuf, consulte la [documentación](https://developers.google.com/protocol-buffers/docs/overview)oficial de protobuf.

>[!div class="step-by-step"]
>[Anterior](protobuf-enums.md)
>[Siguiente](wcf-services-to-grpc-comparison.md)
