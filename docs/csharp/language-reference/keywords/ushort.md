---
title: ushort (Referencia de C#)
ms.date: 03/14/2017
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
ms.openlocfilehash: 03638893978779fcfd34544363d935fa5e609481
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288829"
---
# <a name="ushort-c-reference"></a>ushort (Referencia de C#)

La palabra clave `ushort` indica un tipo de datos entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Tamaño|Tipo de .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`ushort`|De 0 a 65.535|Entero de 16 bits sin signo|<xref:System.UInt16?displayProperty=nameWithType>|  
  
## <a name="literals"></a>Literales  

Puede declarar e inicializar una variable `ushort` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario. Si el literal entero está fuera del intervalo de `ushort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 65 034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a valores `ushort`.    
  
[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario. Los literales decimales no tienen prefijo.

A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad. 
 - C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.
 - C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo. Un literal decimal no puede tener un carácter de subrayado inicial.

A continuación se muestran algunos ejemplos.

[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a>Resolución de sobrecarga del compilador
  
 Debe usarse una conversión al llamar a métodos sobrecargados. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ushort` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 El uso de la conversión `ushort` garantiza que se llama al tipo correcto, por ejemplo:  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a>Conversiones  
 Hay una conversión implícita predefinida de `ushort` a [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Hay una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ushort`. De lo contrario, se debe usar una conversión para realizar una conversión explícita. Por ejemplo, considere las dos variables de `ushort` siguientes, `x` y `y`:  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 La instrucción de asignación siguiente producirá un error de compilación porque la expresión aritmética de la derecha del operador de asignación da como resultado `int` de forma predeterminada.  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 Para corregir este problema, use una conversión:  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 Pero es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `ushort`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.UInt16>  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
