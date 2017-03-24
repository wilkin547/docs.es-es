---
title: "Tabla de conversiones num&#233;ricas impl&#237;citas (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "conversiones [C#], numéricas implícitas"
  - "conversiones numéricas implícitas [C#]"
  - "conversiones numéricas [C#], implícita"
  - "tipos [C#], conversiones numéricas implícitas"
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Tabla de conversiones num&#233;ricas impl&#237;citas (Referencia de C#)
La tabla siguiente muestra las conversiones numéricas implícitas predefinidas.  Las conversiones implícitas se pueden dar en muchas ocasiones, incluidas la invocación a métodos y las instrucciones de asignación.  
  
|From|Para|  
|----------|----------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`, `int`, `long`, `float`, `double` o `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`, `long`, `float`, `double` o `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[Valor int.](../../../csharp/language-reference/keywords/int.md)|`long`, `float`, `double` o `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`, `ulong`, `float`, `double` o `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`, `double` o `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`,  `double` o `decimal`|  
  
## Comentarios  
  
-   Es posible que se puede perder precisión, pero no magnitud en las conversiones de `int`, `uint`, `long`, o `ulong` a `float` y `long` o `ulong` a `double`.  
  
-   No existen conversiones implícitas al tipo `char`.  
  
-   No hay ninguna conversión implícita entre los tipos de punto flotante y el tipo `decimal`.  
  
-   Una expresión constante de tipo `int` se puede convertir a `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que el valor de la expresión constante quede dentro del intervalo del tipo de destino.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)