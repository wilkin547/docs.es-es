---
title: Campos repetidos para listas y matrices - gRPC para desarrolladores de WCF
description: Comprender cómo Protobuf controla las colecciones y cómo se relacionan con las colecciones de .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 63d99532d14deea7800673dd5a6350dd9362ad54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147976"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Campos repetidos para listas y matrices

Las listas se especifican en el búfer `repeated` de protocolo (Protobuf) mediante la palabra clave prefix. En el ejemplo siguiente se muestra cómo crear una lista:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

En el código `repeated` generado, los campos `Google.Protobuf.Collections.RepeatedField<T>` se representan mediante el tipo genérico en lugar de cualquiera de los tipos de colección .NET integrados.

El `RepeatedField<T>` tipo incluye el código necesario para serializar y deserializar la lista al formato de cable binario. Implementa todas las interfaces de colección <xref:System.Collections.Generic.IList%601> .NET estándar, como y <xref:System.Collections.Generic.IEnumerable%601>. Por lo tanto, puede usar consultas LINQ o convertirlas en una matriz o una lista fácilmente.

>[!div class="step-by-step"]
>[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)
