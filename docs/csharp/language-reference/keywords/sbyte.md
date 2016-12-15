---
title: "sbyte (Referencia de C#) | Microsoft Docs"
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
  - "sbyte_CSharpKeyword"
  - "sbyte"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "sbyte (palabra clave) [C#]"
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# sbyte (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `sbyte` indica un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`sbyte`|De \-128 a 127|Entero de 8 bits con signo|<xref:System.SByte?displayProperty=fullName>|  
  
## Literales  
 Puede declarar e inicializar una variable `sbyte` de esta manera:  
  
```  
  
sbyte sByte1 = 127;  
```  
  
 En la declaración anterior, el literal entero 127 se convierte implícitamente del tipo [int](../../../csharp/language-reference/keywords/int.md) al tipo `sbyte`.  Si el literal entero supera el intervalo de valores del tipo `sbyte`, se producirá un error de compilación.  
  
 Debe utilizarse una conversión de tipos al llamar a métodos sobrecargados.  Considere, por ejemplo, los dos métodos sobrecargados siguientes que utilizan parámetros de tipo `sbyte` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(sbyte b) {}  
```  
  
 Si se utiliza la conversión explícita al tipo `sbyte`, se garantiza la llamada al tipo correcto; por ejemplo:  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the sbyte parameter:  
SampleMethod((sbyte)5);  
```  
  
## Conversiones  
 Existe una conversión implícita predefinida de `sbyte` a [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 No se pueden convertir implícitamente tipos numéricos no literales cuyo tamaño de almacenamiento sea superior a `sbyte` \(vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros\).  Considere, por ejemplo, las dos variables siguientes de tipo `sbyte`, `x` e `y`:  
  
```  
  
sbyte x = 10, y = 20;  
```  
  
 La instrucción de asignación siguiente producirá un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa de forma predeterminada como [int](../../../csharp/language-reference/keywords/int.md).  
  
```  
  
sbyte z = x + y;   // Error: conversion from int to sbyte  
```  
  
 Para corregir este problema, convierta explícitamente la expresión como en el ejemplo siguiente:  
  
```  
  
sbyte z = (sbyte)(x + y);   // OK: explicit conversion  
```  
  
 Sin embargo, es posible utilizar las instrucciones siguientes, donde la variable de destino tiene un tamaño de almacenamiento igual o superior:  
  
```  
  
        sbyte x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Observe que no existe conversión implícita de tipos de punto flotante a `sbyte`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
  
        sbyte x = 3.0;         // Error: no implicit conversion from double  
sbyte y = (sbyte)3.0;  // OK: explicit conversion  
```  
  
 Para obtener información acerca de las expresiones aritméticas con tipos de punto flotante y tipos enteros, consulte [float \(Referencia de C\#\)](../../../csharp/language-reference/keywords/float.md) y [double \(Referencia de C\#\)](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información acerca de reglas de conversión numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.SByte>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)