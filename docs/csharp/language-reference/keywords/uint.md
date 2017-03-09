---
title: "uint (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "uint"
  - "uint_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "uint (palabra clave) [C#]"
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# uint (Referencia de C#)
La palabra clave `uint` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`uint`|De 0 a 4.294.967.295|Entero de 32 bits sin signo|<xref:System.UInt32?displayProperty=fullName>|  
  
 **Nota** El tipo `uint` no es conforme a CLS.  Siempre que sea posible, utilice `int`.  
  
## Literales  
 Las variables de tipo `uint` se pueden declarar e inicializar como en el siguiente ejemplo:  
  
```  
  
uint myUint = 4294967290;  
```  
  
 Cuando un literal entero no tiene sufijo, su tipo es el primero de estos tipos en el que se puede representar su valor: [int](../../../csharp/language-reference/keywords/int.md), `uint`, [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md).  En este ejemplo, es `uint`:  
  
```  
  
uint uInt1 = 123;  
```  
  
 También se puede utilizar el sufijo u o U:  
  
```  
  
uint uInt2 = 123U;  
```  
  
 Cuando se utiliza el sufijo `U` o `u`, el tipo del literal puede ser `uint` o `ulong` según el valor numérico del literal.  Por ejemplo:  
  
```  
Console.WriteLine(44U.GetType());  
Console.WriteLine(323442434344U.GetType());  
```  
  
 Este código muestra `System.UInt32`, seguido de `System.UInt64` \(los tipos subyacentes de `uint` y `ulong`, respectivamente\), porque el segundo literal es demasiado grande para que lo almacene el tipo `uint`.  
  
## Conversiones  
 Existe una conversión implícita predefinida de `uint` a [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  Por ejemplo:  
  
```  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 Existe una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `uint`.  En cualquier otro caso, se debe utilizar una conversión explícita.  Por ejemplo, la instrucción de asignación siguiente genera un error de compilación si no se emplea una conversión explícita:  
  
```  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 Observe que no existe conversión implícita de tipos de punto flotante a `uint`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 Para obtener información acerca de las expresiones aritméticas con tipos de punto flotante y tipos enteros, consulte [float \(Referencia de C\#\)](../../../csharp/language-reference/keywords/float.md) y [double \(Referencia de C\#\)](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información acerca de reglas de conversión numéricas implícitas, consulte [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.UInt32>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)