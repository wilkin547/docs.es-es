---
title: 'Campos repetidos para listas y matrices: gRPC para desarrolladores de WCF'
description: Comprenda cómo protobuf controla las colecciones y cómo se relacionan con las colecciones de .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867508"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Campos repetidos para listas y matrices

Las listas se especifican en el búfer de protocolo (protobuf) mediante la `repeated` palabra clave prefix. En el ejemplo siguiente se muestra cómo crear una lista:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

En el código generado, `repeated` los campos se representan mediante propiedades de solo lectura del [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] tipo en lugar de cualquiera de los tipos de colección de .net integrados. Este tipo implementa todas las interfaces de colección estándar de .NET, como <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IEnumerable%601> . Por lo tanto, puede usar consultas LINQ o convertirlos en una matriz o una lista fácilmente.

El `RepeatedField<T>` tipo incluye el código necesario para serializar y deserializar la lista en el formato de conexión binaria.

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
>[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)
