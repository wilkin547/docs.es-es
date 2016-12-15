---
title: "short (Referencia de C#) | Microsoft Docs"
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
  - "short"
  - "short_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "short (palabra clave) [C#]"
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# short (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La palabra clave `short` denota un tipo de datos integral que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`short`|De \-32.768 a 32.767|Entero de 16 bits con signo|<xref:System.Int16?displayProperty=fullName>|  
  
## Literales  
 Las variables de tipo `short` se pueden declarar e inicializar como en el siguiente ejemplo:  
  
```  
  
short x = 32767;  
```  
  
 En la declaración anterior, el literal entero `32767` se convierte implícitamente del tipo [int](../../../csharp/language-reference/keywords/int.md) al tipo `short`.  Si el literal entero no cabe en el espacio de almacenamiento reservado para un tipo `short`, se produce un error de compilación.  
  
 Debe utilizarse una conversión de tipos al llamar a métodos sobrecargados.  Considere, por ejemplo, los dos métodos sobrecargados siguientes que utilizan parámetros de tipo `short` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 Si se utiliza la conversión explícita al tipo `short`, se garantiza la llamada al tipo correcto; por ejemplo:  
  
```  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## Conversiones  
 Existe una conversión implícita predefinida de `short` a [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 No se pueden convertir implícitamente tipos numéricos no literales cuyo tamaño de almacenamiento sea superior a `short` \(vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros\).  Considere, por ejemplo, las dos variables siguientes de tipo `short`, `x` e `y`:  
  
```  
  
short x = 5, y = 12;  
```  
  
 La instrucción de asignación siguiente producirá un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa como [int](../../../csharp/language-reference/keywords/int.md) de forma predeterminada.  
  
 `short`   `z = x + y;   // Error: no conversion from int to short`  
  
 Para solucionar este problema, utilice una conversión explícita:  
  
 `short`   `z = (`  `short`  `)(x + y);   // OK: explicit conversion`  
  
 Sin embargo, es posible utilizar las instrucciones siguientes, donde la variable de destino tiene un tamaño de almacenamiento igual o superior:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 No existe conversión implícita de tipos de punto flotante a tipo `short`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
  
        short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Para obtener más información sobre expresiones aritméticas con tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
 Para obtener más información sobre reglas de conversión numéricas implícitas, vea [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 <xref:System.Int16>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)