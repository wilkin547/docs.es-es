---
title: "byte (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "byte"
  - "byte_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "byte (palabra clave) [C#]"
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# byte (Referencia de C#)
La palabra clave `byte` denota un tipo entero que almacena valores según se muestra en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`byte`|De 0 a 255|Entero de 8 bits sin signo|<xref:System.Byte?displayProperty=fullName>|  
  
## Literales  
 Las variables de tipo `byte` se pueden declarar e inicializar como en el siguiente ejemplo:  
  
```  
byte myByte = 255;  
```  
  
 En la declaración anterior, el literal entero `255` se convierte implícitamente del tipo [int](../../../csharp/language-reference/keywords/int.md) al tipo `byte`.  Si el literal entero supera el intervalo de valores del tipo `byte`, se producirá un error de compilación.  
  
## Conversiones  
 Hay una conversión implícita predefinida de `byte` a [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [longo](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 No es posible convertir implícitamente a `byte` otros tipos numéricos no literales de mayor tamaño de almacenamiento.  Para obtener más información acerca de los tamaños de almacenamiento de tipos enteros, vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md).  Considere, por ejemplo, las dos variables siguientes de tipo `byte`, `x` e `y`:  
  
```  
  
byte x = 10, y = 20;  
```  
  
 La instrucción de asignación siguiente producirá un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa de forma predeterminada como `int`.  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 Para solucionar este problema, utilice una conversión explícita:  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 Sin embargo, es posible utilizar las instrucciones siguientes, donde la variable de destino tiene un tamaño de almacenamiento igual o superior:  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Sin embargo, no existe conversión implícita de tipos de punto flotante a tipo `byte`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 Para llamar a métodos sobrecargados, debe utilizarse una conversión explícita de tipos.  Considere, por ejemplo, los dos métodos sobrecargados siguientes que utilizan parámetros de tipo `byte` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 Si se utiliza la conversión explícita al tipo `byte`, se garantiza la llamada al tipo correcto; por ejemplo:  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 Para obtener más información sobre expresiones aritméticas con tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre reglas de conversión numéricas implícitas, vea [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.Byte>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)