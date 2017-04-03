---
title: delegado (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cf100a5ad3adf001d5435ef6f67e2aa670456649
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-c-reference"></a>delegado (Referencia de C#)
La declaración de un tipo delegado es similar a una firma de método. Tiene un valor devuelto y un número cualquiera de parámetros de cualquier tipo:  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 Un `delegate` es un tipo de referencia que puede usarse para encapsular un método con nombre o anónimo. Los delegados son similares a los punteros de función en C++; pero son más seguros y proporcionan mayor seguridad de tipos. Para las aplicaciones de delegados, vea [Delegados](../../../csharp/programming-guide/delegates/index.md) y [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
## <a name="remarks"></a>Comentarios  
 Los delegados son la base de los [eventos](../../../csharp/programming-guide/events/index.md).  
  
 Se pueden crear instancias de un delegado asociándolo a un método con nombre o anónimo. Para obtener más información, vea [Métodos con nombre](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) y [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
 Para crear instancias del delegado debe usarse un método o una expresión lambda que tenga un tipo de valor devuelto y parámetros de entrada compatibles. Para obtener más información sobre el grado de variación permitida en la firma de método, vea [Varianza en delegados](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca). Para el uso con métodos anónimos, el delegado y el código que se van a asociar se declaran juntos. En esta sección se describen las dos maneras de crear instancias de delegados.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Delegados con métodos con nombre y delegados con métodos anónimos](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)   
 [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
