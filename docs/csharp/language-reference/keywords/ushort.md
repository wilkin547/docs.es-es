---
title: ushort (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
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
ms.openlocfilehash: d27a7b3b44d91b5b52e82b13fb111d865f851297
ms.lasthandoff: 03/13/2017

---
# <a name="ushort-c-reference"></a>ushort (Referencia de C#)
La palabra clave `ushort` indica un tipo de datos entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Tamaño|Tipo de .NET Framework|  
|----------|-----------|----------|-------------------------|  
|`ushort`|De 0 a 65.535|Entero de 16 bits sin signo|<xref:System.UInt16?displayProperty=fullName>|  
  
## <a name="literals"></a>Literales  
 Puede declarar e inicializar una variable `ushort` como en este ejemplo:  
  
```  
  
ushort myShort = 65535;  
```  
  
 En la declaración anterior, el literal entero `65535` se convierte implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a `ushort`. Si el literal entero supera el intervalo de `ushort`, se producirá un error de compilación.  
  
 Debe usarse una conversión al llamar a métodos sobrecargados. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ushort` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
  
 El uso de la conversión `ushort` garantiza que se llama al tipo correcto, por ejemplo:  
  
```  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a>Conversiones  
 Hay una conversión implícita predefinida de `ushort` a [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Hay una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ushort`. De lo contrario, se debe usar una conversión para realizar una conversión explícita. Por ejemplo, considere las dos variables de `ushort` siguientes, `x` y `y`:  
  
```  
  
ushort x = 5, y = 12;  
```  
  
 La instrucción de asignación siguiente producirá un error de compilación porque la expresión aritmética de la derecha del operador de asignación da como resultado `int` de forma predeterminada.  
  
```  
  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 Para corregir este problema, use una conversión:  
  
```  
  
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 Pero es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Además, observe que no hay ninguna conversión implícita de tipos de punto flotante a `ushort`. Por ejemplo, la instrucción siguiente genera un error del compilador a menos que se use una conversión explícita:  
  
```  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre las reglas de conversión numérica implícita, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.UInt16>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md)  (Tabla de tipos enteros)  
 [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md)  (Tabla de tipos integrados)  
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
