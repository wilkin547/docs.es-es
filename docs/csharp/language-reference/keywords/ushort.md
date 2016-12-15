---
title: "ushort (Referencia de C#) | Microsoft Docs"
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
  - "ushort"
  - "ushort_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ushort (palabra clave) [C#]"
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ushort (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `ushort` indica un tipo de datos integral que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`ushort`|De 0 a 65.535|Entero de 16 bits sin signo|<xref:System.UInt16?displayProperty=fullName>|  
  
## Literales  
 Las variables de tipo `ushort` se pueden declarar e inicializar como en el siguiente ejemplo:  
  
```  
  
ushort myShort = 65535;  
```  
  
 En la declaración anterior, el literal entero `65535` se convierte implícitamente del tipo [int](../../../csharp/language-reference/keywords/int.md) al tipo `ushort`.  Si el literal entero supera el intervalo de valores del tipo `ushort`, se producirá un error de compilación.  
  
 Para llamar a métodos sobrecargados, debe utilizarse una conversión explícita de tipos.  Considere, por ejemplo, los dos métodos sobrecargados siguientes que utilizan parámetros de tipo `ushort` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
  
 Si se utiliza la conversión explícita al tipo `ushort`, se garantiza la llamada al tipo correcto; por ejemplo:  
  
```  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## Conversiones  
 Existe una conversión implícita predefinida de `ushort` a [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Existe una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ushort`.  En cualquier otro caso, se debe utilizar una conversión explícita.  Considere, por ejemplo, las dos variables siguientes de tipo `ushort`, `x` e `y`:  
  
```  
  
ushort x = 5, y = 12;  
```  
  
 La instrucción de asignación siguiente producirá un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa de forma predeterminada como `int`.  
  
```  
  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 Para solucionar este problema, utilice una conversión explícita:  
  
```  
  
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 Sin embargo, es posible utilizar las instrucciones siguientes, donde la variable de destino tiene un tamaño de almacenamiento igual o superior:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Observe que no existe conversión implícita de tipos de punto flotante a `ushort`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 Para obtener información acerca de las expresiones aritméticas con tipos de punto flotante y tipos enteros, consulte [float \(Referencia de C\#\)](../../../csharp/language-reference/keywords/float.md) y [double \(Referencia de C\#\)](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información acerca de reglas de conversión numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.UInt16>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)