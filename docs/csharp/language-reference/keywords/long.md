---
title: long (Referencia de C#) | Microsoft Docs
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
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
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 0ea7f109ab934660418aab1a88bff7206ef23a37
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017

---
# <a name="long-c-reference"></a>long (Referencia de C#)

`long` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Tamaño|Tipo de .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`long`|De –9.223.372.036.854.775.808 a 9.223.372.036.854.775.807|Entero de 64 bits con signo|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a>Literales 

Puede declarar e inicializar una variable `long` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario. 

En el ejemplo siguiente, los enteros que equivalen a 4 294 967 296 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `long`.  
  
[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario. Los literales decimales no tienen prefijo. 

A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 Los literales enteros también pueden incluir un sufijo que denote el tipo. El sufijo `L` denota un `long`. En el ejemplo siguiente se usa el sufijo `L` para denotar un entero largo:
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  También puede usar la letra minúscula "l" como sufijo, aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1". Use "L" para mayor claridad.  
  
 Cuando se usa el sufijo `L`, se determina que el tipo del entero literal es `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md), según su tamaño. En este caso, es `long` porque es menor que el intervalo de [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 El sufijo se usa habitualmente para llamar a métodos sobrecargados. Por ejemplo, los siguientes métodos sobrecargados tienen parámetros de tipo `long` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 El sufijo `L` garantiza que se llame a la sobrecarga correcta:  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor: 

1. [int](int.md)
2. [uint](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [ulong](../../../csharp/language-reference/keywords/ulong.md) 

El literal 4294967296 de los ejemplos anteriores es de tipo `long` porque supera el intervalo de [uint](../../../csharp/language-reference/keywords/uint.md) (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros).  
  
 Si usa el tipo `long` con otros tipos enteros en la misma expresión, la expresión se evalúa como `long` (o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas). Por ejemplo, la siguiente expresión se evalúa como `long`:  
  
```csharp  
898L + 88  
```  
  
 Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
## <a name="conversions"></a>Conversiones  
 Existe una conversión implícita predefinida de `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md). De lo contrario, se debe usar una conversión. Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `long`.  
  
 Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `long`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Int64>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
