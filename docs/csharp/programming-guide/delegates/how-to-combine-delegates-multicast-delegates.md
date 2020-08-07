---
title: 'Procedimiento para combinar delegados (delegados de multidifusión): Guía de programación de C#'
description: Aprenda a combinar delegados para crear delegados de multidifusión. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d23ea758c9da2c3399f5d98e81360cc250b428a1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302742"
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
