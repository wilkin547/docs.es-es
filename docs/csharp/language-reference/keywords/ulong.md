---
title: "ulong (Referencia de C#) | Microsoft Docs"
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
  - "ulong_CSharpKeyword"
  - "ulong"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ulong (palabra clave) [C#]"
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ulong (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `ulong` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`ulong`|De 0 a 18,446,744,073,709,551,615|Entero de 64 bits sin signo|<xref:System.UInt64?displayProperty=fullName>|  
  
## Literales  
 Las variables de tipo `ulong` se pueden declarar e inicializar como en el siguiente ejemplo:  
  
```  
  
ulong uLong = 9223372036854775808;  
```  
  
 Cuando un literal entero no tiene sufijo, su tipo es el primero de estos tipos en el que se puede representar su valor: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), `ulong`.  En el ejemplo anterior, es del tipo `ulong`.  
  
 También se pueden utilizar sufijos para especificar el tipo del literal, de acuerdo con las siguientes reglas:  
  
-   Cuando se utiliza el sufijo L o l, el tipo del entero literal será [long](../../../csharp/language-reference/keywords/long.md) o `ulong`, según su tamaño.  
  
    > [!NOTE]
    >  Se puede utilizar la letra minúscula "l" como sufijo.  No obstante, el compilador generará una advertencia, ya que la letra "l" se confunde fácilmente con el dígito "1". Utilice "L" por motivos de claridad.  
  
-   Cuando se utiliza el sufijo `U` o `u`, el tipo del entero literal será [uint](../../../csharp/language-reference/keywords/uint.md) o `ulong`, según su tamaño.  
  
-   Si se utiliza UL, ul, Ul, uL, LU, lu, Lu o lU, el tipo del entero literal será `ulong`.  
  
     Por ejemplo, el resultado de las tres instrucciones siguientes será el tipo `UInt64`, que corresponde al alias `ulong`:  
  
    ```  
    Console.WriteLine(9223372036854775808L.GetType());  
    Console.WriteLine(123UL.GetType());  
    Console.WriteLine((123UL + 456).GetType());  
    ```  
  
 El sufijo se utiliza habitualmente en las llamadas a métodos sobrecargados.  Considere, por ejemplo, los dos métodos sobrecargados siguientes que utilizan parámetros de tipo `ulong` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 Si se utiliza un sufijo con el parámetro `ulong`, se garantiza la llamada al tipo correcto; por ejemplo:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## Conversiones  
 Existe una conversión implícita predefinida de `ulong` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Sin embargo, no existe conversión implícita de `ulong` a cualquier tipo entero.  Por ejemplo, la instrucción siguiente genera un error de compilación si no se emplea una conversión explícita:  
  
```  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 Existe una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ulong`.  
  
 Sin embargo, no existe conversión implícita de tipos de punto flotante a tipo `ulong`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 Para obtener más información sobre expresiones aritméticas con tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre reglas de conversión numéricas implícitas, vea [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.UInt64>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)