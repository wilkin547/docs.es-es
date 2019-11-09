---
title: 'Campos repetidos para listas y matrices: gRPC para desarrolladores de WCF'
description: Comprenda cómo se administran las colecciones mediante protobuf y cómo se relacionan con las colecciones de .NET.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 740af8af39af9bf31be17ad831f481176e30d81f
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841400"
---
# <a name="repeated-fields-for-lists-and-arrays"></a>Campos repetidos para listas y matrices

Las listas se especifican en protobuf con la palabra clave prefix `repeated`. En el ejemplo siguiente se muestra cómo crear una lista:

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

En el código generado, `repeated` campos se representan mediante el tipo genérico `Google.Protobuf.Collections.RepeatedField<T>` en lugar de cualquiera de los tipos de colección .NET integrados. El tipo de `RepeatedField<T>` incluye el código necesario para serializar y deserializar la lista en el formato de conexión binaria. Implementa todas las interfaces de colección estándar de .NET como <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IEnumerable%601>, de modo que puede usar consultas LINQ o convertirlas en una matriz o una lista fácilmente.

>[!div class="step-by-step"]
>[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)
