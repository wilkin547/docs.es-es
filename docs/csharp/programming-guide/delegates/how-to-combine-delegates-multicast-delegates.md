---
title: 'Procedimiento para combinar delegados (delegados de multidifusión): Guía de programación de C#'
description: Aprenda a combinar delegados para crear delegados de multidifusión. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 3e86c8ed4b7b091ee8c75930d427c22aa5bc0c52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185956"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a>Procedimiento para combinar delegados (delegados de multidifusión) (Guía de programación de C#)

En este ejemplo se muestra cómo crear delegados de multidifusión. Una propiedad útil de los objetos [delegados](../../language-reference/builtin-types/reference-types.md) es que puedan asignarse objetos múltiples a una instancia de delegado con el operador `+`. El delegado de multidifusión contiene una lista de los delegados asignados. Cuando se llama al delegado de multidifusión, invoca a los delegados de la lista, en orden. Solo los delegados del mismo tipo pueden combinarse.  
  
 El operador `-` puede usarse para quitar un delegado de componente de un delegado de multidifusión.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.MulticastDelegate>
- [Guía de programación de C#](../index.md)
- [Eventos](../events/index.md)
