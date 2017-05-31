---
title: byte (Referencia de C#) | Microsoft Docs
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 57c4b1c7ead9386ff4067da5915a55a79f5e562e
ms.openlocfilehash: fce94687cbf055219913758d49642c8e4a999db3
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="byte-c-reference"></a>byte (Referencia de C#)

`byte` denota un tipo entero que almacena valores como se indica en la tabla siguiente.  
  
|Tipo|Intervalo|Tamaño|Tipo de .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`byte`|De 0 a 255|Entero de 8 bits sin signo|<xref:System.Byte?displayProperty=fullName>|  
  
## <a name="literals"></a>Literales  

 Puede declarar e inicializar una variable `byte` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario. Si el literal entero está fuera del intervalo de `byte` (es decir, si es menor que <xref:System.Byte.MinValue?displayProperty=fullName> o mayor que <xref:System.Byte.MaxValue?displayProperty=fullName>, se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 201 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a valores `byte`.    
  
[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario. Los literales decimales no tienen prefijo.

A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-cs[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a>Conversiones  
 Hay una conversión implícita predefinida de `byte` a [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 No se pueden convertir implícitamente los tipos numéricos no literales de mayor tamaño de almacenamiento a `byte`. Para más información sobre los tamaños de almacenamiento de los tipos enteros, vea la [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md). Considere, por ejemplo, las dos siguientes variables de `byte` `x` y `y`:  
  
```  
  
byte x = 10, y = 20;  
```  
  
 La instrucción de asignación siguiente producirá un error de compilación porque la expresión aritmética del lado derecho del operador de asignación da como resultado `int` de forma predeterminada.  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 Para corregir este problema, use una conversión:  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 Pero es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 Además, no hay ninguna conversión implícita de tipos de punto flotante a `byte`. Por ejemplo, la instrucción siguiente genera un error del compilador a menos que se use una conversión explícita:  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 Al llamar a métodos sobrecargados, debe usarse una conversión. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `byte` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 El uso de la conversión `byte` garantiza que se llama al tipo correcto, por ejemplo:  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Byte>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
