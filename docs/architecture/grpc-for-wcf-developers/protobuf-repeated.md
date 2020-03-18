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
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="30e98-103">Campos repetidos para listas y matrices</span><span class="sxs-lookup"><span data-stu-id="30e98-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="30e98-104">Las listas se especifican en el búfer `repeated` de protocolo (Protobuf) mediante la palabra clave prefix.</span><span class="sxs-lookup"><span data-stu-id="30e98-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="30e98-105">En el ejemplo siguiente se muestra cómo crear una lista:</span><span class="sxs-lookup"><span data-stu-id="30e98-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="30e98-106">En el código `repeated` generado, los campos `Google.Protobuf.Collections.RepeatedField<T>` se representan mediante el tipo genérico en lugar de cualquiera de los tipos de colección .NET integrados.</span><span class="sxs-lookup"><span data-stu-id="30e98-106">In the generated code, `repeated` fields are represented by the `Google.Protobuf.Collections.RepeatedField<T>` generic type rather than any of the built-in .NET collection types.</span></span>

<span data-ttu-id="30e98-107">El `RepeatedField<T>` tipo incluye el código necesario para serializar y deserializar la lista al formato de cable binario.</span><span class="sxs-lookup"><span data-stu-id="30e98-107">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span> <span data-ttu-id="30e98-108">Implementa todas las interfaces de colección <xref:System.Collections.Generic.IList%601> .NET estándar, como y <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="30e98-108">It implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="30e98-109">Por lo tanto, puede usar consultas LINQ o convertirlas en una matriz o una lista fácilmente.</span><span class="sxs-lookup"><span data-stu-id="30e98-109">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="30e98-110">[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="30e98-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
