---
title: "long (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "long_CSharpKeyword"
  - "long"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "long (palabra clave) [C#]"
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# long (Referencia de C#)
La palabra clave `long` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.  
  
|Tipo|Intervalo|Size|Tipo de .NET Framework|  
|----------|---------------|----------|----------------------------|  
|`long`|–9.223.372.036.854.775.808 a 9.223.372.036.854.775.807|Entero de 64 bits con signo|<xref:System.Int64?displayProperty=fullName>|  
  
## Literales  
 Las variables de tipo `long` se pueden declarar e inicializar como en el siguiente ejemplo:  
  
```  
  
long long1 = 4294967296;  
```  
  
 Cuando un literal entero no tiene sufijo, su tipo es el primero de estos tipos en el que se puede representar su valor: [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), `long`, [ulong](../../../csharp/language-reference/keywords/ulong.md).  En el ejemplo anterior, es del tipo `long`, ya que supera el intervalo de [uint](../../../csharp/language-reference/keywords/uint.md) \(vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros\).  
  
 También se puede utilizar el sufijo L con el tipo `long` de este modo:  
  
```  
  
long long2 = 4294967296L;  
```  
  
 Cuando se utiliza el sufijo L, el tipo del entero literal será `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md), según su tamaño.  En este caso, es `long`, ya que es menor que el intervalo de [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 El sufijo se utiliza habitualmente en las llamadas a métodos sobrecargados.  Considere, por ejemplo, los dos métodos sobrecargados siguientes que utilizan parámetros de tipo `long` e [int](../../../csharp/language-reference/keywords/int.md):  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 Si se utiliza el sufijo L, se garantiza la llamada al tipo correcto; por ejemplo:  
  
```  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5L);   // Calling the method with the long parameter  
```  
  
 El tipo `long` se puede utilizar con otros tipos enteros numéricos en la misma expresión, en cuyo caso la expresión se evalúa como `long` \(o [bool](../../../csharp/language-reference/keywords/bool.md) en el caso de expresiones relacionales o booleanas\).  Por ejemplo, la siguiente expresión se evalúa como `long`:  
  
```  
898L + 88  
```  
  
> [!NOTE]
>  También se puede utilizar la letra minúscula "l" como sufijo.  No obstante, el compilador generará una advertencia, ya que la letra "l" se confunde fácilmente con el dígito "1". Utilice "L" por motivos de claridad.  
  
 Para obtener más información sobre expresiones aritméticas con tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).  
  
## Conversiones  
 Existe una conversión implícita predefinida de `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).  En los demás casos, se debe utilizar una conversión explícita.  Por ejemplo, la instrucción siguiente genera un error de compilación si no se emplea una conversión explícita:  
  
```  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 Existe una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `long`.  
  
 Observe que no existe conversión implícita de tipos de punto flotante a `long`.  Por ejemplo, la instrucción siguiente generará un error de compilación, a menos que se utilice una conversión explícita:  
  
```  
  
        long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.Int64>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)