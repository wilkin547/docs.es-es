---
title: "Cómo: determinar si un objeto .NET estándar es serializable"
description: "Muestra cómo determinar si se puede serializar un tipo de .NET estándar en tiempo de ejecución."
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0460fe27228fb9e17bde2d10652164707cd47a8b
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>Cómo: determinar si un objeto .NET estándar es serializable

El estándar de .NET es una especificación que define los tipos y miembros que deben estar presentes en las implementaciones específicas de .NET que se ajustan a esa versión del estándar. Sin embargo, el estándar de .NET no define si un tipo es serializable. Los tipos definidos en la biblioteca estándar de .NET no están marcados con el <xref:System.SerializableAttribute> atributo. En su lugar, las implementaciones específicas. NET, como .NET Framework y .NET Core, son gratuitas determinar si un tipo determinado es serializable. 

Si ha desarrollado una biblioteca que tiene como destino .NET Standard, la biblioteca se puede utilizar en cualquier implementación de .NET que admita el estándar. NET. Esto significa que no se conoce de antemano si un tipo determinado es serializable; solo puede determinar si es serializable en tiempo de ejecución.

Puede determinar si un objeto es serializable en tiempo de ejecución al recuperar el valor de la <xref:System.Type.IsSerializable> propiedad de un <xref:System.Type> objeto que representa el tipo del objeto. En el ejemplo siguiente se proporciona una implementación. Define un `IsSerializable(Object)` método de extensión que indica si alguno <xref:System.Object> se puede serializar la instancia.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

A continuación, puede pasar cualquier objeto al método para determinar si se puede serializar y deserializar en la implementación actual. NET, como se muestra en el ejemplo siguiente:

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a>Vea también

[Serialización binaria](binary-serialization.md)   
<xref:System.SerializableAttribute?displayProperty=fullName>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
