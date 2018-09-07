---
title: Cómo determinar si un objeto de .NET Standard es serializable
description: Se muestra cómo determinar si un tipo de .NET Standard se puede serializar en tiempo de ejecución.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079895"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Cómo determinar si un objeto de .NET Standard es serializable

.NET Standard es una especificación que define los tipos y miembros que deben estar presentes en implementaciones específicas de .NET que cumplen con esa versión del estándar. Sin embargo, .NET Standard no define si un tipo es serializable. Los tipos definidos en la biblioteca .NET Standard no están marcados con el <xref:System.SerializableAttribute> atributo. En su lugar, las implementaciones de .NET concretas, como .NET Framework y .NET Core, son gratis determinar si un tipo determinado es serializable. 

Si ha desarrollado una biblioteca que tiene como destino .NET Standard, la biblioteca puede usarse en cualquier implementación de .NET que admita .NET Standard. Esto significa que no se conoce de antemano si un tipo determinado es serializable; solo puede determinar si es serializable en tiempo de ejecución.

Puede determinar si un objeto es serializable en tiempo de ejecución al recuperar el valor de la <xref:System.Type.IsSerializable> propiedad de un <xref:System.Type> objeto que representa el tipo del objeto. El ejemplo siguiente proporciona una implementación. Define un `IsSerializable(Object)` método de extensión que indica si algún <xref:System.Object> se puede serializar la instancia.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

A continuación, puede pasar cualquier objeto al método para determinar si se puede serializar y deserializar en la implementación actual. NET, como se muestra en el ejemplo siguiente:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>Vea también

- [Serialización binaria](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
