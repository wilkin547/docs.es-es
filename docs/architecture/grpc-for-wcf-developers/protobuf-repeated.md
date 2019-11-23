---
title: 'Campos repetidos para listas y matrices: gRPC para desarrolladores de WCF'
description: Comprenda cómo se administran las colecciones mediante protobuf y cómo se relacionan con las colecciones de .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 17c579bc98ba62ea74b9452bdb28efd96fc51406
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967363"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="f7ac9-103">Campos repetidos para listas y matrices</span><span class="sxs-lookup"><span data-stu-id="f7ac9-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="f7ac9-104">Las listas se especifican en protobuf con la palabra clave prefix `repeated`.</span><span class="sxs-lookup"><span data-stu-id="f7ac9-104">Lists are specified in Protobuf using the `repeated` prefix keyword.</span></span> <span data-ttu-id="f7ac9-105">En el ejemplo siguiente se muestra cómo crear una lista:</span><span class="sxs-lookup"><span data-stu-id="f7ac9-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="f7ac9-106">En el código generado, `repeated` campos se representan mediante el tipo genérico `Google.Protobuf.Collections.RepeatedField<T>` en lugar de cualquiera de los tipos de colección .NET integrados.</span><span class="sxs-lookup"><span data-stu-id="f7ac9-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="f7ac9-107">El tipo de `RepeatedField<T>` incluye el código necesario para serializar y deserializar la lista en el formato de conexión binaria.</span><span class="sxs-lookup"><span data-stu-id="f7ac9-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="f7ac9-108">Implementa todas las interfaces de colección estándar de .NET como <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IEnumerable%601>, de modo que puede usar consultas LINQ o convertirlas en una matriz o una lista fácilmente.</span><span class="sxs-lookup"><span data-stu-id="f7ac9-108">It implements all the standard .NET collection interfaces such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>, so you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f7ac9-109">[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="f7ac9-109">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
