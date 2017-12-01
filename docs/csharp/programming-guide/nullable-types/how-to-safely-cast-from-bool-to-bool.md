---
title: "Cómo: Convertir con seguridad de bool? a bool (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a6fa65c15bb5f1da9960dbc17bd25b4087ab862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
