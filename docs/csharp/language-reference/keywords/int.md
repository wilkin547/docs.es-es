---
title: "int (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "int_CSharpKeyword"
  - "int"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "int (palabra clave) [C#]"
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# int (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `int` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indica en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|Valor predeterminado|  
|----------|---------------|----------|----------------------------|--------------------------|  
|`int`|De \-2.147.483.648 a 2.147.483.647|Entero de 32 bits con signo|<xref:System.Int32?displayProperty=fullName>|0|  
  
## Literales  
 Las variables de tipo `int` se pueden declarar e inicializar como en el siguiente ejemplo:  
  
```  
  
int i = 123;  
```  
  
 Cuando un literal entero no tiene sufijo, su tipo es el primero de estos tipos en el que se puede representar su valor: `int`, [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md).  En este ejemplo, es del tipo `int`.  
  
## Conversiones  
 Existe una conversión implícita predefinida de `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  Por ejemplo:  
  
```  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 Existe una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`.  Por ejemplo, la instrucción de asignación siguiente genera un error de compilación si no se emplea una conversión explícita:  
  
```  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 Observe que no existe conversión implícita de tipos de punto flotante a `int`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
  
        int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 Para obtener más información sobre las expresiones aritméticas con tipos de punto flotante y tipos enteros, vea [float \(Referencia de C\#\)](../../../csharp/language-reference/keywords/float.md) y [double \(Referencia de C\#\)](../../../csharp/language-reference/keywords/double.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.Int32>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)