---
title: long (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c28c8308d7ed32f7240f56113a77a0794cb1ba62
ms.lasthandoff: 03/13/2017

---
# <a name="long-c-reference"></a>long (Referencia de C#)
La palabra clave `long` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Tamaño|Tipo de .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`long`|De –9.223.372.036.854.775.808 a 9.223.372.036.854.775.807|Entero de 64 bits con signo|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a>Literales  
 Puede declarar e inicializar una variable `long` como en este ejemplo:  
  
```  
  
long long1 = 4294967296;  
```  
  
 Cuando un literal entero no tiene sufijo, su tipo es el primero de estos tipos en el que se puede representar su valor: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), `long`, [ulong](../../../csharp/language-reference/keywords/ulong.md). En el ejemplo anterior es de tipo `long` porque supera el intervalo de [uint](../../../csharp/language-reference/keywords/uint.md) (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros).  
  
 También puede usar el sufijo L con el tipo `long` de esta forma:  
  
```  
  
long long2 = 4294967296L;  
```  
  
 Cuando se usa el sufijo L, se determina que el tipo del entero literal es `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md) según su tamaño. En este caso es `long` porque es menor que el intervalo de [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 El sufijo se usa habitualmente en las llamadas a métodos sobrecargados. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `long` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 El uso del sufijo L garantiza que se llame al tipo correcto, por ejemplo:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5L);   // Calling the method with the long parameter  
```  
  
 Puede usar el tipo `long` con otros tipos enteros numéricos en la misma expresión, en cuyo caso la expresión se evalúa como `long` (o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas). Por ejemplo, la siguiente expresión se evalúa como `long`:  
  
```  
898L + 88  
```  
  
> [!NOTE]
>  También puede usar la letra minúscula "l" como sufijo, aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1". Use "L" para mayor claridad.  
  
 Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
## <a name="conversions"></a>Conversiones  
 Existe una conversión implícita predefinida de `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md). De lo contrario, se debe usar una conversión. Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:  
  
```  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `long`.  
  
 Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `long`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:  
  
```  
  
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
