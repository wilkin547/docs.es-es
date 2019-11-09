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
# <a name="protobuf-nested-types"></a><span data-ttu-id="cd94d-103">Tipos anidados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="cd94d-103">Protobuf nested types</span></span>

<span data-ttu-id="cd94d-104">Del mismo C# modo que permite declarar clases dentro de otras clases, protobuf permite anidar definiciones de mensajes dentro de otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="cd94d-104">Just like C# allows you to declare classes inside other classes, Protobuf allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="cd94d-105">En el ejemplo siguiente se muestra cómo crear tipos de mensajes anidados:</span><span class="sxs-lookup"><span data-stu-id="cd94d-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="cd94d-106">En el código C# generado, el tipo de `Inner` se declarará en una clase de `Types` estática anidada dentro de la clase `HelloRequest`:</span><span class="sxs-lookup"><span data-stu-id="cd94d-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="cd94d-107">[Anterior](protobuf-data-types.md)
>[Siguiente](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="cd94d-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
