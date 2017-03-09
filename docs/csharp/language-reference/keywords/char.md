---
title: "char (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "char"
  - "char_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "char (tipo de datos) [C#]"
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# char (Referencia de C#)
La palabra clave de `char` se utiliza para declarar una instancia de la estructura de <xref:System.Char?displayProperty=fullName> que .NET Framework utiliza para representar un carácter Unicode.  El valor de un objeto de `Char` es un valor \(ordinal\) numérico de 16 bits.  
  
 Los caracteres Unicode se utilizan para representar la mayor parte de los idiomas escritos en el mundo.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`char`|De U\+0000 a U\+FFFF|Carácter Unicode de 16 bits|<xref:System.Char?displayProperty=fullName>|  
  
## Literales  
 Las constantes de tipo `char` se pueden escribir como literales de cadena, secuencias de escape hexadecimales o representaciones Unicode.  Los códigos de caracteres integrales se pueden convertir explícitamente al tipo char.  En el ejemplo siguiente se inicializan cuatro variables `char` con el mismo carácter `X`:  
  
 [!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/csharp/char_1.cs)]  
  
## Conversiones  
 Un tipo `char` se puede convertir implícitamente en [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  Sin embargo, no existen conversiones implícitas desde otros tipo al tipo `char`.  
  
 El tipo <xref:System.Char?displayProperty=fullName> proporciona varios métodos estáticos para trabajar con valores `char`.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.Char>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Cadenas](../../../csharp/programming-guide/strings/index.md)