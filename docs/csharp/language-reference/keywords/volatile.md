---
title: "volatile (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "volatile_CSharpKeyword"
  - "volatile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "volatile (palabra clave) [C#]"
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 29
---
# volatile (Referencia de C#)
La palabra clave `volatile` indica que varios subprocesos que se ejecutan a la vez podrían modificar un campo.  Los campos que se declaran como `volatile` no están sujetos a optimizaciones del compilador que suponen el acceso por un subproceso único.  Esto garantiza que el valor más actualizado está en todo momento presente en el campo.  
  
 El modificador `volatile` suele utilizarse para un campo al que tengan acceso varios subprocesos sin utilizar la instrucción [lock](../../../csharp/language-reference/keywords/lock-statement.md) para serializar el acceso.  
  
 La palabra clave `volatile` se puede aplicar a los campos de estos tipos:  
  
-   Tipos de referencia.  
  
-   Tipos de puntero \(en un contexto no seguro\).  Tenga en cuenta que aunque el propio puntero puede ser volátil, no ocurre lo mismo con el objeto al que apunta.  Es decir, no puede declarar un "puntero como volátil".  
  
-   Tipos como sbyte, byte, short, ushort, int, uint, char, float y bool.  
  
-   Un tipo de enumeración con uno de los siguientes tipos base: byte, sbyte, short, ushort, int o uint.  
  
-   Parámetros de tipo genéricos que se sabe que son tipos de referencia.  
  
-   <xref:System.IntPtr> y <xref:System.UIntPtr>.  
  
 La palabra clave volatile sólo se puede aplicar a los campos de una clase o struct.  Las variables locales no se pueden declarar como `volatile`.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo declarar una variable de campo pública como `volatile`.  
  
 [!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un subproceso auxiliar o de trabajo, y utilizarlo para realizar el procesamiento en paralelo con el del subproceso primario.  Para obtener información básica sobre multithreading, vea [Threading](../Topic/Managed%20Threading.md) y [Subprocesos](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
 [!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)