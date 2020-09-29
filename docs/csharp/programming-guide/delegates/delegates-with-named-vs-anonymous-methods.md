---
title: 'Delegados con métodos con nombre y Métodos anónimos: Guía de programación de C#'
description: Aprenda sobre los delegados con nombre frente a los métodos anónimos. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: d8d2c6d8c7792b81f2fc2e25d0836e3780e58e52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202505"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>Delegados con métodos con nombre y Métodos anónimos (Guía de programación de C#)

Un [delegado](../../language-reference/builtin-types/reference-types.md) puede asociarse con un método con nombre. Cuando crea una instancia de un delegado mediante un método con nombre, el método se pasa como un parámetro, por ejemplo:  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 Esto se llama con un método con nombre. Los delegados construidos con un método con nombre pueden encapsular un método [estático](../../language-reference/keywords/static.md) o un método de instancia. Los métodos con nombre son la única manera de crear una instancia de un delegado en versiones anteriores de C#. En cambio, en una situación en la que crear un método nuevo es una sobrecarga no deseada, C# le permite crear una instancia de un delegado y especificar inmediatamente un bloque de código que el delegado procesará cuando se llame. El bloque puede contener una expresión lambda o un método anónimo. Para obtener más información, vea [Funciones anónimas](../statements-expressions-operators/anonymous-functions.md).  
  
## <a name="remarks"></a>Comentarios  

 El método que pasa como un parámetro de delegado debe tener la misma firma que la declaración de delegado.  
  
 Una instancia de delegado puede encapsular un método de instancia o estático.  
  
 Aunque el delegado puede usar un parámetro [out](../../language-reference/keywords/out-parameter-modifier.md), no recomendamos su uso con delegados de eventos de multidifusión porque no puede conocer a qué delegado se llamará.  
  
## <a name="example-1"></a>Ejemplo 1  

 A continuación se muestra un ejemplo sencillo de cómo declarar y usar un delegado. Tenga en cuenta que tanto el delegado, `Del`, como el método asociado, `MultiplyNumbers`, tienen la misma firma  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a>Ejemplo 2  

 En el ejemplo siguiente, un delegado se asigna a métodos estáticos y de instancia y devuelve información específica de cada uno.  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Delegados](./index.md)
- [Procedimiento para combinar delegados (delegados de multidifusión)](./how-to-combine-delegates-multicast-delegates.md)
- [Eventos](../events/index.md)
