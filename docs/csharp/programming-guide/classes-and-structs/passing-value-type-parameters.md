---
title: "Pasar par&#225;metros de tipo de valor (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "parámetros de métodos [C#], tipos de valor"
  - "parámetros [C#], de valor"
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Pasar par&#225;metros de tipo de valor (Gu&#237;a de programaci&#243;n de C#)
Una variable de [tipo de valor](../../../csharp/language-reference/keywords/value-types.md) contiene directamente los datos, a diferencia de una variable de [tipo de referencia](../../../csharp/language-reference/keywords/reference-types.md), que contiene una referencia a los datos.  Pasar una variable de tipo de valor a un método por valor significa pasar una copia de la variable al método.  Cualquier cambio en el parámetro que tenga lugar dentro del método no tiene ningún efecto en los datos originales almacenados en la variable de argumento.  Si desea que el método denominado para cambiar el valor del parámetro, debe pasarlo por referencia, mediante la palabra clave de [referencia](../../../csharp/language-reference/keywords/ref.md) o de [out](../../../csharp/language-reference/keywords/out.md) .  Para simplificar, los siguientes ejemplos utilizan `ref`.  
  
## Pasar tipos de valor por valor  
 El siguiente ejemplo ilustra el paso de parámetros de tipo de valor por valor.  La variable `n` se pasa por valor al método `SquareIt`.  Cualquier cambio que se produzca dentro del método no afectará al valor original de la variable.  
  
 [!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]  
  
 `n` variable es un tipo de valor.  Contiene los datos, el valor `5`.  Cuando se invoca `SquareIt`, el contenido de `n` se copia en el parámetro `x`, el cual se eleva al cuadrado dentro del método.  En `Main`, sin embargo, el valor de `n` es igual después de llamar al método de `SquareIt` que antes.  El cambio que tiene lugar dentro del método afecta sólo a la variable local `x`.  
  
## Pasar tipos de valor por referencia  
 El ejemplo siguiente es igual que el ejemplo anterior, excepto que el argumento se pasa como parámetro de `ref` .  El valor del argumento subyacente, `n`, cambia a `x` cambia en el método.  
  
 [!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]  
  
 En este ejemplo, no se pasa el valor de `n`, sino una referencia a `n`.  El parámetro `x` no es de tipo [int](../../../csharp/language-reference/keywords/int.md); es una referencia a un valor de tipo `int`, en este caso, una referencia a `n`.  Por consiguiente, cuando `x` se eleva dentro del método, lo que se eleva realmente es a lo que se conoce `x` , `n`.  
  
## Intercambiar tipos de valor  
 Un ejemplo común de cambiar los valores de argumentos es un método de intercambio, donde se pasan dos variables al método, y el método intercambia su contenido.  Debe pasar los argumentos del método de intercambio por referencia.  Si no, se intercambia copias locales de los parámetros en el método, y no se produce ningún cambio en el método de llamada.  El ejemplo siguiente se cambia valores enteros.  
  
 [!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]  
  
 Cuando se llama al método de `SwapByRef` , utilice la palabra clave de `ref` en la llamada, como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Pasar parámetros](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Pasar parámetros Reference\-Type](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)