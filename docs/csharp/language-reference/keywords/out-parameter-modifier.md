---
title: "Modificador del par&#225;metro out (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "out (parámetros) [C#]"
  - "parámetros [C#], out"
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# Modificador del par&#225;metro out (Referencia de C#)
La palabra clave `out` produce argumentos que se van a pasar por referencia.  Ocurre igual que con la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md), excepto en que `ref` requiere que se inicialice la variable antes de pasarla.  Utilizar un parámetro `out`, la definición de método y el método de llamada deben utilizar explícitamente la palabra clave `out`.  Por ejemplo:  
  
 [!code-cs[csrefKeywordsMethodParams#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_1.cs)]  
  
 Aunque las variables que se pasan como argumentos `out` no tienen que inicializarse antes de pasarlas, se requiere que el método invocado asigne un valor antes de que se devuelva.  
  
 Aunque las palabras clave `out` y `ref` generan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la firma del método en tiempo de compilación.  Por consiguiente, no se pueden sobrecargar los métodos si la única diferencia consiste en que un método toma un argumento `ref` y el otro toma un argumento `out`.  Por ejemplo, el código siguiente no se compilará:  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_2.cs)]  
  
 Sin embargo, se puede realizar la sobrecarga si un método toma un argumento `ref` u `out` y el otro no utiliza ninguno de los dos, de la manera siguiente:  
  
 [!code-cs[csrefKeywordsMethodParams#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_3.cs)]  
  
 Las propiedades no son variables y, por consiguiente, no se pueden pasar como parámetros `out`.  
  
 Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 No puede usar palabras clave de `ref` y de `out` para los siguientes tipos de métodos:  
  
-   Métodos Async, que se define utilizando el modificador de [async](../../../csharp/language-reference/keywords/async.md) .  
  
-   Métodos de iterador, que incluyen un fragmento de [retorno de producción](../../../csharp/language-reference/keywords/yield.md) o de `yield break` .  
  
## Ejemplo  
 Declarar un método como `out` es útil cuando se desea que devuelva varios valores.  En el siguiente ejemplo, se usa `out` para devolver tres variables con una única llamada al método.  Observe que el tercer argumento se asigna a null.  Esto permite que los métodos devuelvan valores opcionalmente.  
  
 [!code-cs[csrefKeywordsMethodParams#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_4.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)