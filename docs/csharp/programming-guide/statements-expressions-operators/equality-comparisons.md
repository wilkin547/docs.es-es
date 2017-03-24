---
title: "Comparaciones de igualdad (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "igualdad de objetos [C#]"
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Comparaciones de igualdad (Gu&#237;a de programaci&#243;n de C#)
A veces es necesario comparar si dos valores son iguales.  En algunos casos, se prueba la *igualdad de valores*, también denominada *equivalencia*, lo que significa que los valores contenidos en las dos variables son iguales.  En otros casos, hay que determinar si dos variables hacen referencia al mismo objeto subyacente de la memoria.  Este tipo de igualdad se denomina *igualdad de referencia* o *identidad*.  En este tema se describen estos dos tipos de igualdad y se proporcionan vínculos a otros temas para obtener más información.  
  
## Igualdad de referencia  
 La igualdad de referencias significa que dos referencias de objeto hacen referencia al mismo objeto subyacente.  Esto puede suceder mediante una asignación simple, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]  
  
 En este código, se crean dos objetos, pero después de la instrucción de asignación, ambas referencias hacen referencia al mismo objeto.  Por consiguiente, presentan igualdad de referencia.  El método <xref:System.Object.ReferenceEquals%2A> se utiliza para determinar si dos referencias hacen referencia al mismo objeto.  
  
 El concepto de igualdad de la referencia sólo se aplica a los tipos de referencia.  Los objetos de tipo de valor no pueden presentar igualdad de referencia porque al asignar una instancia de un tipo de valor a una variable, se realiza una copia del valor.  Por consiguiente, nunca puede haber dos structs con conversión unboxing que hagan referencia a la misma ubicación de la memoria.  Además, si se utiliza <xref:System.Object.ReferenceEquals%2A> para comparar dos tipos de valor, el resultado siempre será `false`, aunque todos los valores que contengan los objetos sean idénticos.  Esto se debe a que a cada variable se aplica la conversión boxing en una instancia de objeto independiente.  Para obtener más información, vea [Cómo: Probar la igualdad de referencia \(Identidad\)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).  
  
## Igualdad de valores  
 La igualdad de valores significa que dos objetos contienen el mismo valor o valores.  Para los tipos de valor primitivos, como [int](../../../csharp/language-reference/keywords/int.md) o [bool](../../../csharp/language-reference/keywords/bool.md), las pruebas de igualdad de valores son sencillas.  Puede utilizar el operador [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md), tal como se muestra en el ejemplo siguiente.  
  
```c#  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.   
if( b == a)   
{  
    // The two integers are equal.  
}  
```  
  
 Para la mayoría de los otros tipos, las pruebas de igualdad de valores son más complejas, porque es preciso entender cómo la define el tipo.  Para las clases y los structs que tienen varios campos o propiedades, la igualdad de valores suele definirse de modo que significa que todos los campos o propiedades tienen el mismo valor.  Por ejemplo, podrían definirse dos objetos `Point` que fueran equivalentes si pointA.X es igual a pointB.X y pointA.Y es igual a pointB.Y.  
  
 Sin embargo, no hay ningún requisito que exija que la equivalencia se base en todos los campos de un tipo.  Se puede basar en un subconjunto.  Al comparar tipos que no sean de su propiedad, es importante asegurarse concretamente de cómo se define la equivalencia para ese tipo.  Para obtener más información sobre cómo definir la igualdad de valores en sus propias clases y structs, vea [Cómo: Definir la igualdad de valores para un tipo](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).  
  
### Igualdad de valores en valores de punto flotante  
 Las comparaciones de igualdad de valores de punto flotante \([double](../../../csharp/language-reference/keywords/double.md) y [float](../../../csharp/language-reference/keywords/float.md)\) son problemáticas debido a la imprecisión de la aritmética de coma flotante en los equipos binarios.  Para obtener más información, vea los comentarios del tema <xref:System.Double?displayProperty=fullName>.  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Cómo: Probar la igualdad de referencia \(Identidad\)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)|Describe cómo determinar si dos variables presentan igualdad de referencia.|  
|[Cómo: Definir la igualdad de valores para un tipo](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)|Describe cómo proporcionar una definición personalizada de igualdad de valores para un tipo.|  
|[Guía de programación de C\#](../../../csharp/programming-guide/index.md)|Proporciona vínculos a información detallada sobre importantes las características del lenguaje C\# y características que están disponibles para C\# a través de .NET Framework.|  
|[Tipos](../../../csharp/programming-guide/types/index.md)|Proporciona información sobre el sistema de tipos de C\# y vínculos a información adicional.|  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)