---
title: 'Procedimiento Combinar delegados (delegados de multidifusión): Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d7098bb5518b92b407f905ddabbfafdcb77536bf
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423349"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Procedimiento Combinar delegados (delegados de multidifusión) (Guía de programación de C#)
En este ejemplo se muestra cómo crear delegados de multidifusión. Una propiedad útil de los objetos [delegados](../../language-reference/builtin-types/reference-types.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`. El delegado de multidifusión contiene una lista de los delegados asignados. Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden. Solo los delegados del mismo tipo pueden combinarse.  
  
 El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.MulticastDelegate>
- [Guía de programación de C#](../index.md)
- [Eventos](../events/index.md)
