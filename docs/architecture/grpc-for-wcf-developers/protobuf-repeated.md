---
title: 'Campos repetidos para listas y matrices: gRPC para desarrolladores de WCF'
description: Comprenda cómo protobuf controla las colecciones y cómo se relacionan con las colecciones de .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 16f2b5a54b032f32c8fcb9d572d5284fe589cb01
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542964"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Campos repetidos para listas y matrices

Las listas se especifican en el búfer de protocolo (protobuf) mediante la palabra clave de prefijo `repeated`. En el ejemplo siguiente se muestra cómo crear una lista:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

En el código generado, `repeated` campos se representan mediante el tipo genérico `Google.Protobuf.Collections.RepeatedField<T>` en lugar de cualquiera de los tipos de colección .NET integrados. 

El tipo de `RepeatedField<T>` incluye el código necesario para serializar y deserializar la lista en el formato de conexión binaria. Implementa todas las interfaces de colección estándar de .NET, como <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IEnumerable%601>. Por lo tanto, puede usar consultas LINQ o convertirlos en una matriz o una lista fácilmente.

>[!div class="step-by-step"]
>[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)
