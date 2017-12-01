---
title: "where (restricción de tipo genérico) (Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords: where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2b7b159689aa771d3f9d59e3b1dd340c85b1d79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="where-generic-type-constraint-c-reference"></a>where (restricción de tipo genérico) (Referencia de C#)
En una definición de tipo genérico, la cláusula `where` se usa para especificar restricciones sobre los tipos que se pueden usar como argumentos para un parámetro de tipo definido en una declaración genérica. Por ejemplo, se puede declarar una clase genérica, `MyGenericClass`, de modo que el parámetro de tipo `T` implemente la interfaz <xref:System.IComparable%601>:  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  Para obtener más información sobre la cláusula where en una expresión de consulta, vea [where (Cláusula)](../../../csharp/language-reference/keywords/where-clause.md).  
  
 Además de las restricciones de interfaz, una cláusula `where` puede incluir una restricción de clase base, que establece que un tipo debe tener la clase especificada como clase base (o ser la propia clase) para poder usarse como un argumento de tipo para ese tipo genérico. Si se usa este tipo de restricción, debe aparecer antes que cualquier otra restricción sobre ese parámetro de tipo.  
  
 [!code-csharp[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 Puede que la cláusula `where` incluya también una restricción de constructor. Es posible crear una instancia de un parámetro de tipo usando el operador new; pero, para ello, el parámetro de tipo debe restringirse mediante la restricción de constructor, `new()`. La [restricción new()](../../../csharp/language-reference/keywords/new-constraint.md) permite que el compilador sepa que cualquier argumento de tipo especificado debe tener accesible un constructor sin parámetros o el constructor predeterminado. Por ejemplo:  
  
 [!code-csharp[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 La restricción `new()` aparece en último lugar en la cláusula `where`.  
  
 Con varios parámetros de tipo, use una cláusula `where` para cada parámetro de tipo, por ejemplo:  
  
 [!code-csharp[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 También puede asociar restricciones a parámetros de tipo de métodos genéricos, de la siguiente manera:  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 Observe que la sintaxis para describir las restricciones de parámetro de tipo en delegados es igual que la de métodos:  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 Para obtener información sobre los delegados genéricos, vea [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
 Para obtener más información sobre la sintaxis y el uso de restricciones, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [new (restricción)](../../../csharp/language-reference/keywords/new-constraint.md)  
 [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
