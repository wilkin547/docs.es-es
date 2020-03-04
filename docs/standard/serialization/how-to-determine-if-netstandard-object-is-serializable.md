---
title: Cómo determinar si un objeto .NET Standard es serializable
description: Muestra cómo determinar si un tipo de .NET Standard se puede serializar en tiempo de ejecución.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159902"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Cómo determinar si un objeto .NET Standard es serializable

El .NET Standard es una especificación que define los tipos y miembros que deben estar presentes en implementaciones de .NET específicas que se ajusten a esa versión del estándar. Sin embargo, el .NET Standard no define si un tipo es serializable. Los tipos definidos en la biblioteca .NET Standard no están marcados con el atributo <xref:System.SerializableAttribute>. En su lugar, las implementaciones de .NET específicas, como la .NET Framework y .NET Core, son gratuitas para determinar si un tipo determinado es serializable.

Si ha desarrollado una biblioteca que tiene como destino el .NET Standard, la biblioteca puede utilizarla cualquier implementación de .NET que admita la .NET Standard. Esto significa que no puede saber de antemano si un tipo determinado es serializable; solo puede determinar si es serializable en tiempo de ejecución.

Puede determinar si un objeto es serializable en tiempo de ejecución recuperando el valor de la propiedad <xref:System.Type.IsSerializable> de un objeto <xref:System.Type> que representa el tipo de ese objeto. En el ejemplo siguiente se proporciona una implementación de. Define un método de extensión `IsSerializable(Object)` que indica si se puede serializar cualquier instancia de <xref:System.Object>.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

Después, puede pasar cualquier objeto al método para determinar si se puede serializar y deserializar en la implementación actual de .NET, como se muestra en el ejemplo siguiente:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>Vea también

- [Serialización binaria](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
