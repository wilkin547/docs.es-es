---
title: "Tipo parcial (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "partialtype"
  - "partialtype_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "tipos parciales [C#]"
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Tipo parcial (Referencia de C#)
Las definiciones de tipo parcial permiten dividir la definición de una clase, struct o interfaz en varios archivos.  
  
 En Archivo1.cs:  
  
 [!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/csharp/partial-type_1.cs)]  
  
 En Archivo2.cs, la declaración:  
  
 [!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/csharp/partial-type_2.cs)]  
  
## Comentarios  
 Dividir una clase, struct o tipo de interfaz en varios archivos puede ser útil cuando se trabaja con proyectos grandes o código generado automáticamente como el que proporciona el [Windows Forms Designer](http://msdn.microsoft.com/es-es/3c3d61f8-f36c-4d41-b9c3-398376fabb15).  Un tipo parcial puede contener un [método parcial](../../../csharp/language-reference/keywords/partial-method.md).  Para obtener más información, vea [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)