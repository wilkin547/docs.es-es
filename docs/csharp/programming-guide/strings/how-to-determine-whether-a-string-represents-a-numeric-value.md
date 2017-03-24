---
title: "C&#243;mo: Determinar si una cadena representa un valor num&#233;rico (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "cadenas numéricas [C#]"
  - "cadenas [C#], numéricas"
  - "validar los datos numéricos proporcionados por el usuario [C#]"
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# C&#243;mo: Determinar si una cadena representa un valor num&#233;rico (Gu&#237;a de programaci&#243;n de C#)
Para determinar si una cadena es una representación válida de un tipo numérico especificado, utilice el método estático `TryParse` implementado por todos los tipos numéricos primitivos y también por tipos como <xref:System.DateTime> y <xref:System.Net.IPAddress>.  En el ejemplo siguiente se muestra cómo determinar si "108" es un valor [int](../../../csharp/language-reference/keywords/int.md) válido.  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Si la cadena contiene caracteres no numéricos o el valor numérico es demasiado grande o demasiado pequeño para el tipo determinado que ha especificado, `TryParse` devuelve el valor false y establece el parámetro out en cero.  De lo contrario, devuelve el valor true y establece el parámetro out en el valor numérico de la cadena.  
  
> [!NOTE]
>  Una cadena puede contener solamente caracteres numéricos pero no ser válida para el tipo cuyo método `TryParse` se está utilizando.  Por ejemplo, "256" no es un valor válido para `byte` pero sí para `int`. "  98,6" no es un valor válido para `int` pero sí para `decimal`.  
  
## Ejemplo  
 En los ejemplos siguientes se muestra cómo utilizar `TryParse` con representaciones de cadena de los valores `long`, `byte` y `decimal`.  
  
 [!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]  
  
## Programación eficaz  
 Los tipos numéricos primitivos también implementan el método estático `Parse`, que produce una excepción si la cadena no es un número válido.  `TryParse` es, en general, más eficaz porque simplemente devuelve "false" si el número es no válido.  
  
## Seguridad de .NET Framework  
 Utilice siempre los métodos `TryParse` o `Parse` para validar los datos proporcionados por el usuario en controles como cuadros de texto y cuadros combinados.  
  
## Vea también  
 [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)   
 [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)   
 [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)   
 [Analizar cadenas numéricas](../Topic/Parsing%20Numeric%20Strings%20in%20the%20.NET%20Framework.md)   
 [Aplicar formato a tipos](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)