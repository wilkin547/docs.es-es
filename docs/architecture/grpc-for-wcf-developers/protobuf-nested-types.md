---
title: 'Protobuf tipos anidados: gRPC para desarrolladores de WCF'
description: Obtenga información sobre los tipos de mensajes anidados en protobuf y gRPC y cómo se C#generan en.
ms.date: 09/09/2019
ms.openlocfilehash: 7b9a331336ebe1ca7bc75fdd164b7b88ae4f9db2
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542851"
---
# <a name="protobuf-nested-types"></a>Tipos anidados de Protobuf

Del mismo C# modo que permite declarar clases dentro de otras clases, el búfer de protocolo (protobuf) permite anidar definiciones de mensajes dentro de otros mensajes. En el ejemplo siguiente se muestra cómo crear tipos de mensajes anidados:

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
