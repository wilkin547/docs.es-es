---
title: 'Protobuf tipos anidados: gRPC para desarrolladores de WCF'
description: Obtenga información sobre los tipos de mensajes anidados en protobuf y gRPC y cómo se C#generan en.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: ec9fc522619230c1201bfef1e8128f7356936212
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841406"
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
