---
title: dynamic (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- dynamic_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 7cec26e59a865e78bf02a84cfe2d3b5177fa55af
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017

---
# <a name="dynamic-c-reference"></a>dynamic (Referencia de C#)
El tipo `dynamic` permite que las operaciones en las que se produce omitan la comprobación de tipo en tiempo de compilación. En su lugar, se resuelven estas operaciones en tiempo de ejecución. El tipo `dynamic` simplifica el acceso a las API de COM como las API de automatización de Office y también a API dinámicas como las bibliotecas de IronPython, y a Document Object Model (DOM) HTML.  
  
 El tipo `dynamic` se comporta como el tipo `object` en la mayoría de las circunstancias. En cambio, el compilador no resuelve o no comprueba el tipo de las operaciones que contienen expresiones de tipo `dynamic`. El compilador empaqueta información sobre la operación y esa información se usa después para evaluar la operación en tiempo de ejecución. Como parte del proceso, las variables de tipo `dynamic` están compiladas en las variables de tipo `object`. Por consiguiente, el tipo `dynamic` solo existe en tiempo de compilación, no en tiempo de ejecución.  
  
 En el siguiente ejemplo se contrasta una variable de tipo `dynamic` con una variable de tipo `object`. Para comprobar el tipo de cada variable en tiempo de compilación, coloque el puntero del mouse sobre `dyn` u `obj` en las instrucciones `WriteLine`. IntelliSense muestra **dynamic** para `dyn` y **object** para `obj`.  
  
 [!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]  
  
 Las instrucciones `WriteLine` muestran los tipos en tiempo de ejecución de `dyn` y `obj`. En ese punto, ambos tienen el mismo tipo, entero. Se produce el siguiente resultado:  
  
 `System.Int32`  
  
 `System.Int32`  
  
 Para ver la diferencia entre `dyn` y `obj` en tiempo de compilación, agregue las dos líneas siguientes entre las declaraciones y las instrucciones `WriteLine` en el ejemplo anterior.  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 Un error del compilador se notifica para el intento de suma de un entero y un objeto en la expresión `obj + 3`. En cambio, no se notifica ningún error para `dyn + 3`. En tiempo de compilación no se comprueba la expresión que contiene `dyn` porque el tipo de `dyn` es `dynamic`.  
  
## <a name="context"></a>Contexto  
 La palabra clave `dynamic` puede aparecer directamente o como un componente de un tipo construido en las siguientes situaciones:  
  
-   En declaraciones, como el tipo de una propiedad, un campo, un indexador, un parámetro, un valor devuelto, una variable local o una restricción de tipo. La siguiente definición de clase usa `dynamic` en varias declaraciones diferentes.  
  
     [!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]  
  
-   En conversiones de tipos explícitas, como el tipo de destino de una conversión.  
  
     [!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]  
  
-   En cualquier contexto donde los tipos actúen como valores, por ejemplo, en el lado derecho de un operador `is` o un operador `as`, o como argumento de `typeof` como parte de un tipo construido. Por ejemplo, se puede usar `dynamic` en las siguientes expresiones.  
  
     [!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente usa `dynamic` en varias declaraciones. El método `Main` también contrasta la comprobación de tipo en tiempo de compilación con la comprobación de tipo en tiempo de ejecución.  
  
 [!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]  
  
 Para obtener más información y ejemplos, vea [Uso de tipo dinámico (Guía de programación de C#)](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Dynamic.ExpandoObject?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Uso de tipo dinámico](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [object](../../../csharp/language-reference/keywords/object.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [Cómo: Realizar conversiones seguras usando los operadores is y as (Guía de programación de C#)](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)   
 [Walkthrough: Creating and Using Dynamic Objects](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md) (Tutorial: Crear y usar objetos dinámicos [C# y Visual Basic])
