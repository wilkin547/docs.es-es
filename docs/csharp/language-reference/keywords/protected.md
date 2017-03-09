---
title: "protected (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "protected"
  - "protected_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "protected (palabra clave) [C#]"
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# protected (Referencia de C#)
La palabra clave `protected` es un modificador de acceso a miembros.  Un miembro protegido es accesible dentro de su clase y por instancias de clases derivadas.  Encontrará una comparación de `protected` con los otros modificadores de acceso en [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## Ejemplo  
 Se puede obtener acceso a un miembro protegido de una clase base en una clase derivada sólo si el acceso se realiza a través del tipo de la clase derivada.  Por ejemplo, considere el siguiente segmento de código:  
  
 [!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#11)]  
  
 La instrucción `a.x = 10` genera un error porque se realiza dentro del método estático Main y no de una instancia de la clase B.  
  
 Los miembros de un struct no se pueden proteger, ya que el struct no se puede heredar.  
  
## Ejemplo  
 En este ejemplo, la clase `DerivedPoint` se deriva de `Point`.  Por lo tanto, puede obtener acceso a los miembros protegidos de la clase base directamente desde la clase derivada.  
  
 [!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#12)]  
  
 Si se cambian los niveles de acceso de `x` e `y` a [private](../../../csharp/language-reference/keywords/private.md), el compilador producirá los siguientes mensajes de error:  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Niveles de accesibilidad](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)