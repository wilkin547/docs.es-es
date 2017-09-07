---
title: "Delegados con métodos con nombre y delegados con métodos anónimos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f82519f42e75008fc78fe475b7e37040985a21a1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>Delegados con métodos con nombre y delegados con métodos anónimos (Guía de programación de C#)
Un [delegado](../../../csharp/language-reference/keywords/delegate.md) puede asociarse con un método con nombre. Cuando crea una instancia de un delegado mediante un método con nombre, el método se pasa como un parámetro, por ejemplo:  
  
 [!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 Esto se llama con un método con nombre. Los delegados construidos con un método con nombre pueden encapsular un método [estático](../../../csharp/language-reference/keywords/static.md) o un método de instancia. Los métodos con nombre son la única manera de crear una instancia de un delegado en versiones anteriores de C#. En cambio, en una situación en la que crear un método nuevo es una sobrecarga no deseada, C# le permite crear una instancia de un delegado y especificar inmediatamente un bloque de código que el delegado procesará cuando se llame. El bloque puede contener una expresión lambda o un método anónimo. Para obtener más información, vea [Funciones anónimas](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## <a name="remarks"></a>Comentarios  
 El método que pasa como un parámetro de delegado debe tener la misma firma que la declaración de delegado.  
  
 Una instancia de delegado puede encapsular un método de instancia o estático.  
  
 Aunque el delegado puede usar un parámetro [out](../../../csharp/language-reference/keywords/out.md), no recomendamos su uso con delegados de eventos de multidifusión porque no puede conocer a qué delegado se llamará.  
  
## <a name="example-1"></a>Ejemplo 1  
 A continuación se muestra un ejemplo sencillo de cómo declarar y usar un delegado. Tenga en cuenta que tanto el delegado, `Del`, como el método asociado, `MultiplyNumbers`, tienen la misma firma  
  
 [!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a>Ejemplo 2  
 En el ejemplo siguiente, un delegado se asigna a métodos estáticos y de instancia y devuelve información específica de cada uno.  
  
 [!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [Cómo: Combinar delegados (delegados de multidifusión)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)

