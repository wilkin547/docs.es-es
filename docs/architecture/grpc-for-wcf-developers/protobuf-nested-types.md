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
# <a name="protobuf-nested-types"></a><span data-ttu-id="34345-103">Tipos anidados de Protobuf</span><span class="sxs-lookup"><span data-stu-id="34345-103">Protobuf nested types</span></span>

<span data-ttu-id="34345-104">Del mismo C# modo que permite declarar clases dentro de otras clases, protobuf permite anidar definiciones de mensajes dentro de otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="34345-104">Just like C# allows you to declare classes inside other classes, Protobuf allows you to nest message definitions within other messages.</span></span> <span data-ttu-id="34345-105">En el ejemplo siguiente se muestra cómo crear tipos de mensajes anidados:</span><span class="sxs-lookup"><span data-stu-id="34345-105">The following example shows how to create nested message types:</span></span>

```protobuf
message Outer {
    message Inner {
        string text = 1;
    }
    Inner inner = 1;
}
```

<span data-ttu-id="34345-106">En el código C# generado, el tipo de `Inner` se declarará en una clase de `Types` estática anidada dentro de la clase `HelloRequest`:</span><span class="sxs-lookup"><span data-stu-id="34345-106">In the generated C# code, the `Inner` type will be declared in a nested static `Types` class within the `HelloRequest` class:</span></span>

```csharp
var inner = new Outer.Types.Inner { Text = "Hello" };
```

>[!div class="step-by-step"]
><span data-ttu-id="34345-107">[Anterior](protobuf-data-types.md)
>[Siguiente](protobuf-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="34345-107">[Previous](protobuf-data-types.md)
[Next](protobuf-repeated.md)</span></span>
