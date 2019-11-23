---
title: 'Protobuf tipos anidados: gRPC para desarrolladores de WCF'
description: Obtenga información sobre los tipos de mensajes anidados en protobuf y gRPC y cómo se C#generan en.
ms.date: 09/09/2019
ms.openlocfilehash: bbc7ed41516d29f867bbc9da5b258f6a3c9ff261
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967396"
---
# <a name="protobuf-nested-types"></a>Tipos anidados de Protobuf

Del mismo C# modo que permite declarar clases dentro de otras clases, protobuf permite anidar definiciones de mensajes dentro de otros mensajes. En el ejemplo siguiente se muestra cómo crear tipos de mensajes anidados:

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

En el código C# generado, el tipo de `Inner` se declarará en una clase de `Types` estática anidada dentro de la clase `HelloRequest`:

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
>[Anterior](protobuf-data-types.md)
>[Siguiente](protobuf-repeated.md)
