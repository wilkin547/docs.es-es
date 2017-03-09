---
title: "M&#233;todos gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "genéricos [C#], métodos"
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# M&#233;todos gen&#233;ricos (Gu&#237;a de programaci&#243;n de C#)
Un método genérico es un método que se declara con parámetros de tipo, como se muestra a continuación:  
  
 [!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_1.cs)]  
  
 El siguiente ejemplo de código muestra una manera de llamar al método utilizando `int` para el argumento de tipo:  
  
 [!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_2.cs)]  
  
 También puede omitir el argumento de tipo y el compilador lo inferirá.  La siguiente llamada a `Swap` es equivalente a la llamada anterior:  
  
 [!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_3.cs)]  
  
 Las mismas reglas para la inferencia de tipo se aplican a los métodos estáticos y a los métodos de instancia.  El compilador es capaz de inferir los parámetros de tipo según los argumentos que se pasan al método; no es posible inferir los parámetros de tipo únicamente a partir de una restricción o un valor devuelto.  Por consiguiente, la inferencia de tipo no funciona con métodos que no tienen parámetros.  La inferencia de tipo tiene lugar en tiempo de compilación antes de que el compilador intente resolver las firmas de los métodos sobrecargados.  El compilador aplica la lógica de inferencia de tipo a todos los métodos genéricos que comparten el mismo nombre.  En el paso de resolución de sobrecarga, el compilador incluye sólo aquellos métodos genéricos en los cuales la inferencia se realizó correctamente.  
  
 Dentro de una clase genérica, los métodos no genéricos pueden tener acceso a los parámetros de tipo de nivel de clase, como sigue a continuación:  
  
 [!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_4.cs)]  
  
 Si define un método genérico que acepta los mismos parámetros de tipo que la clase contenedora, el compilador genera la advertencia CS0693, ya que, dentro del ámbito del método, el argumento suministrado para el `T` interno oculta el argumento suministrado para el `T` externo.  Si necesita la flexibilidad de llamar a un método de clase genérico con argumentos de tipo distintos de los suministrados cuando se crearon instancias de la clase, considere la posibilidad de suministrar otro identificador para el parámetro de tipo del método, como se muestra en `GenericList2<T>` en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_5.cs)]  
  
 Utilice las restricciones para habilitar las operaciones más especializadas en parámetros de tipo en métodos.  Esta versión de `Swap<T>`, ahora denominada `SwapIfGreater<T>`, sólo se puede utilizar con argumentos de tipo que implementan <xref:System.IComparable%601>.  
  
 [!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_6.cs)]  
  
 Los métodos genéricos se pueden sobrecargar en varios parámetros de tipo.  Por ejemplo, los siguientes métodos se pueden encontrar todos en la misma clase:  
  
 [!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/csharp/generic-methods_7.cs)]  
  
## Especificación del lenguaje C\#  
 Para obtener más información, vea [Especificación del lenguaje C\#](../../../csharp/language-reference/language-specification.md).  
  
## Vea también  
 <xref:System.Collections.Generic>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)