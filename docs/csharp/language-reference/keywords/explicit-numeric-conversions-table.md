---
title: "Tabla de conversiones num&#233;ricas expl&#237;citas (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "conversiones [C#], numéricas explícitas"
  - "conversión numérica explícita [C#]"
  - "conversiones numéricas [C#], explícita"
  - "tipos de datos numéricos [C#]"
  - "conversión de tipos [C#], numéricas explícitas"
  - "tipos [C#], conversiones numéricas explícitas"
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Tabla de conversiones num&#233;ricas expl&#237;citas (Referencia de C#)
Las conversiones numéricas explícitas se utilizan para convertir cualquier tipo numérico a cualquier otro tipo numérico, para el que no existe conversión implícita, mediante una expresión que utilice el operador de conversión explícita.  La siguiente tabla muestra estas conversiones.  
  
 Para obtener más información sobre las conversiones, vea [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
|From|Para|  
|----------|----------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` o `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` o `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`,  `byte`,  `ushort`,  `uint`,  `ulong` o  `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`,  `byte`,  `short` o  `char`|  
|[Valor int.](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`, `` o `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`,  `short`,  `ushort`,  `int` o  `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`,  `byte`, `short`, `ushort`,  `int`, `uint`, `ulong` o  `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`,  `byte`, `short`, `ushort`,  `int`, `uint`, `long` o  `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte` o  `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` ``  o `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` ``  o `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `double`|  
  
## Comentarios  
  
-   Las conversiones numéricas explícitas pueden producir pérdida de precisión o provocar excepciones.  
  
-   Cuando se convierte un valor `decimal` en un tipo entero, este valor se redondea hacia cero al valor entero más próximo.  Si el valor entero resultante queda fuera del intervalo del tipo de destino, se produce una excepción <xref:System.OverflowException>.  
  
-   Cuando se convierte un valor `double` o `float` en un tipo entero, el valor se trunca.  Si el valor entero resultante queda fuera del intervalo del valor de destino, el resultado depende del contexto de comprobación de desbordamiento.  En un contexto comprobado, se produce una excepción `OverflowException`, mientras que en un contexto no comprobado, el resultado es un valor no especificado del tipo de destino.  
  
-   Cuando se convierte `double` en `float`, el valor `double` se redondea al valor `float` más próximo.  Si el valor de tipo `double` es demasiado pequeño o demasiado grande para ajustarse al tipo de destino, el resultado será cero o infinito.  
  
-   Cuando se convierte `float` o `double` en `decimal`, el valor de origen se convierte en una representación `decimal` y se redondea al número más próximo después de la vigésimo octava posición decimal si es necesario.  Según el valor de origen, se puede producir uno de los siguientes resultados:  
  
    -   Si el valor de origen es demasiado pequeño para representarlo como `decimal`, el resultado se convierte en cero.  
  
    -   Si el valor de origen es NaN \(no es un número\), infinito o demasiado grande para ser representado como `decimal`, se produce una excepción `OverflowException`.  
  
-   Cuando se convierte `decimal` en `float` o `double`, el valor `decimal` se redondea al valor `double` o `float` más próximo.  
  
 Para obtener más información sobre conversión explícita, vea Explícita en la Especificación del lenguaje C\#.  Para obtener información sobre cómo tener acceso a la especificación, vea [Especificación del lenguaje C\#](../../../csharp/language-reference/language-specification.md).  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [\(\) \(operador\)](../../../csharp/language-reference/operators/invocation-operator.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)