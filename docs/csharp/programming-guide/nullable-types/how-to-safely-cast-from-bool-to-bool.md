---
title: "Cómo: Convertir con seguridad de bool? a bool (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
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
ms.openlocfilehash: 7648b9bb5d54b58dc13371e1308f038289df8e56
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a>Cómo: Convertir con seguridad de bool? a bool (Guía de programación de C#)
El tipo que acepta valores NULL `bool?` puede contener tres valores distintos: `true`, `false` y `null`. Por lo tanto, el tipo `bool?` no se puede usar en instrucciones condicionales como `if`, `for` o `while`. Por ejemplo, el siguiente código causa un error del compilador.  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 Esto no está permitido porque no está claro lo que `null` significa en el contexto de una instrucción condicional. Para usar un tipo `bool?` en una instrucción condicional, compruebe antes su propiedad <xref:System.Nullable%601.HasValue%2A> para asegurarse de que el valor no sea `null` y, después, conviértalo a `bool`. Para obtener más información, vea [bool](../../../csharp/language-reference/keywords/bool.md). Si realiza la conversión en un `bool?` con un valor `null`, se producirá una excepción <xref:System.InvalidOperationException> en la prueba condicional. En el siguiente ejemplo se muestra una forma de conversión segura de `bool?` a `bool`:  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de literales](../../../csharp/language-reference/keywords/literal-keywords.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Operador !](../../../csharp/language-reference/operators/null-conditional-operator.md)
