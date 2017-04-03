---
title: ulong (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
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
ms.openlocfilehash: 36de0add1d7fdf58745c65d231f3789c532ab69f
ms.lasthandoff: 03/13/2017

---
# <a name="ulong-c-reference"></a>ulong (Referencia de C#)
La palabra clave `ulong` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Tamaño|Tipo de .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`ulong`|De 0 a 18.446.744.073.709.551.615|Entero de 64 bits sin signo|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a>Literales  
 Puede declarar e inicializar una variable `ulong` como en este ejemplo:  
  
```  
  
ulong uLong = 9223372036854775808;  
```  
  
 Cuando un literal entero no tiene sufijo, su tipo es el primero de estos tipos en el que se puede representar su valor: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), `ulong`. En el ejemplo anterior, es del tipo `ulong`.  
  
 También se pueden usar sufijos para especificar el tipo del literal, de acuerdo con las siguientes reglas:  
  
-   Cuando se usa el sufijo L o l, el tipo del entero literal será [long](../../../csharp/language-reference/keywords/long.md) o `ulong`, según su tamaño.  
  
    > [!NOTE]
    >  Puede usar la letra minúscula "l" como sufijo, aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1". Use "L" para mayor claridad.  
  
-   Cuando se usa el sufijo `U` o `u`, el tipo del entero literal será [uint](../../../csharp/language-reference/keywords/uint.md) o `ulong`, según su tamaño.  
  
-   Si se usa UL, ul, Ul, uL, LU, lu, Lu o lU, el tipo del entero literal será `ulong`.  
  
     Por ejemplo, el resultado de las tres instrucciones siguientes será el tipo de sistema `UInt64`, que corresponde al alias `ulong`:  
  
    ```  
    Console.WriteLine(9223372036854775808L.GetType());  
    Console.WriteLine(123UL.GetType());  
    Console.WriteLine((123UL + 456).GetType());  
    ```  
  
 El sufijo se usa habitualmente en las llamadas a métodos sobrecargados. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ulong` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 Si se usa un sufijo con el parámetro `ulong`, se garantiza la llamada al tipo correcto, por ejemplo:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a>Conversiones  
 Existe una conversión implícita predefinida de `ulong` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 No existe conversión implícita de `ulong` a cualquier tipo entero. Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:  
  
```  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 Existe una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ulong`.  
  
 Además, no hay ninguna conversión implícita de tipos de punto flotante a `ulong`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:  
  
```  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.UInt64>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
