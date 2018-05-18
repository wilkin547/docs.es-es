---
title: 'Cómo: Combinar delegados (delegados de multidifusión) (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: e1214a4d281dbcb9d8186770b68510d3d9a4b15f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Cómo: Combinar delegados (delegados de multidifusión) (Guía de programación de C#)
En este ejemplo se muestra cómo crear delegados de multidifusión. Una propiedad útil de los objetos [delegados](../../../csharp/language-reference/keywords/delegate.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`. El delegado de multidifusión contiene una lista de los delegados asignados. Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden. Solo los delegados del mismo tipo pueden combinarse.  
  
 El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.MulticastDelegate>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Eventos](../../../csharp/programming-guide/events/index.md)
