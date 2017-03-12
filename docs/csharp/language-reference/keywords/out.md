---
title: "out (Referencia de C#) | Microsoft Docs"
ms.date: "2017-03-01"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "out_CSharpKeyword"
  - "out"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "out [C#]"
  - "out (palabra clave) [C#]"
ms.assetid: 7e911a0c-3f98-4536-87be-d539b7536ca8
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# out (Referencia de C#)
Puede utilizar la palabra clave contextual `out` en dos contextos \(cada uno es un vínculo a información detallada\), como un [modificador de parámetro](../../../csharp/language-reference/keywords/out-parameter-modifier.md) o en las [declaraciones de parámetro de tipo genérico](../../../csharp/language-reference/keywords/out-generic-modifier.md) en interfaces y delegados.  En este tema se describe el modificador de parámetro, pero puede ver [este otro tema](../../../csharp/language-reference/keywords/out-generic-modifier.md) para obtener información sobre las declaraciones de parámetros de tipo genérico.  
  
 La palabra clave `out` hace que los argumentos se pasen por referencia.  En esto es como la palabra clave [ref](../../../csharp/language-reference/keywords/ref.md), salvo que `ref` requiere que se inicialice la variable antes de pasarla.  Para usar un parámetro `out`, tanto la definición de método como el método de llamada deben utilizar explícitamente la palabra clave `out`.  Por ejemplo:  
  
 [!code-cs[csrefKeywordsMethodParams#1](../../../csharp/language-reference/keywords/codesnippet/csharp/out_1.cs)]  
  
 Aunque las variables que se pasan como argumentos `out` no tienen que inicializarse antes de pasarse, es necesario que el método llamado asigne un valor antes de que el método devuelva un resultado.  
  
 Aunque las palabras clave `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación.  Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` y el otro toma un argumento `out`.  Por ejemplo, el código siguiente, no se compilará:  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../csharp/language-reference/keywords/codesnippet/csharp/out_2.cs)]  
  
 La sobrecarga es posible, sin embargo, si un método toma un argumento `ref` o `out` y el otro no utiliza ninguno, así:  
  
 [!code-cs[csrefKeywordsMethodParams#3](../../../csharp/language-reference/keywords/codesnippet/csharp/out_3.cs)]  
  
 Las propiedades no son variables y, por tanto, no pueden pasarse como parámetros `out`.  
  
 Para obtener información sobre cómo pasar matrices, vea [Pasar matrices mediante Ref y Out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Las palabras clave `ref` y `out` no pueden usarse para los siguientes tipos de métodos:  
  
-   Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.  
  
## Ejemplo  
 Declarar un método `out` resulta útil cuando se desea que devuelva varios valores.  En el ejemplo siguiente, se utiliza `out` para devolver tres variables con una única llamada al método.  Tenga en cuenta que el tercer argumento se asigna a null.  Esto permite que los métodos devuelvan valores opcionalmente.  
  
 [!code-cs[csrefKeywordsMethodParams#4](../../../csharp/language-reference/keywords/codesnippet/csharp/out_4.cs)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)