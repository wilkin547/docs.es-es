---
title: short (Referencia de C#) | Microsoft Docs
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
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
ms.openlocfilehash: 14f9c66bb620e2ad35513abeeba77372904cc1f3
ms.contentlocale: es-es
ms.lasthandoff: 03/24/2017

---
# <a name="short-c-reference"></a>short (Referencia de C#)

`short` denota un tipo de datos integral que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Tamaño|Tipo de .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`short`|De -32 768 a 32 767|Entero de 16 bits con signo|<xref:System.Int16?displayProperty=fullName>|  
  
## <a name="literals"></a>Literales  

Puede declarar e inicializar una variable `short` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.  Si el literal entero está fuera del intervalo de `short` (es decir, si es menor que <xref:System.Int16.MinValue?displayProperty=fullName> o mayor que <xref:System.Int16.MaxValue?displayProperty=fullName>, se produce un error de compilación. 

En el ejemplo siguiente, los enteros que equivalen a 1034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a valores `short`.  
  
[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario. Los literales decimales no tienen prefijo.

A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.

[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a>Resolución de sobrecarga del compilador

 Debe usarse una conversión de tipos al llamar a métodos sobrecargados. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `short` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 El uso de la conversión `short` garantiza que se llama al tipo correcto, por ejemplo:  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a>Conversiones  

 Existe una conversión implícita predefinida de `short` a [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 No se pueden convertir implícitamente tipos numéricos no literales cuyo tamaño de almacenamiento sea superior a `short` (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros). Considere, por ejemplo, las dos siguientes variables de `short`, `x` e `y`:  
  
```csharp  
short x = 5, y = 12;  
```  
  
 La instrucción de asignación siguiente produce un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa como [int](../../../csharp/language-reference/keywords/int.md) de manera predeterminada.  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 Para corregir este problema, use una conversión:  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 También es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 No existe conversión implícita de tipos de punto flotante a `short`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Int16>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
