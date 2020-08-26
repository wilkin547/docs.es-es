---
title: 'Campos repetidos para listas y matrices: gRPC para desarrolladores de WCF'
description: Comprenda cómo protobuf controla las colecciones y cómo se relacionan con las colecciones de .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867508"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="803ee-103">Campos repetidos para listas y matrices</span><span class="sxs-lookup"><span data-stu-id="803ee-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="803ee-104">Las listas se especifican en el búfer de protocolo (protobuf) mediante la `repeated` palabra clave prefix.</span><span class="sxs-lookup"><span data-stu-id="803ee-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="803ee-105">En el ejemplo siguiente se muestra cómo crear una lista:</span><span class="sxs-lookup"><span data-stu-id="803ee-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="803ee-106">En el código generado, `repeated` los campos se representan mediante propiedades de solo lectura del [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] tipo en lugar de cualquiera de los tipos de colección de .net integrados.</span><span class="sxs-lookup"><span data-stu-id="803ee-106">In the generated code, `repeated` fields are represented by read-only properties of the [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="803ee-107">Este tipo implementa todas las interfaces de colección estándar de .NET, como <xref:System.Collections.Generic.IList%601> y <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="803ee-107">This type implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="803ee-108">Por lo tanto, puede usar consultas LINQ o convertirlos en una matriz o una lista fácilmente.</span><span class="sxs-lookup"><span data-stu-id="803ee-108">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

<span data-ttu-id="803ee-109">El `RepeatedField<T>` tipo incluye el código necesario para serializar y deserializar la lista en el formato de conexión binaria.</span><span class="sxs-lookup"><span data-stu-id="803ee-109">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span>

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
><span data-ttu-id="803ee-110">[Anterior](protobuf-nested-types.md)
>[Siguiente](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="803ee-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
