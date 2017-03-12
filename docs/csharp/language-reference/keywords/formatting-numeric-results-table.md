---
title: "Tabla de formatos de presentaci&#243;n para valores num&#233;ricos (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "aplicar formato [C#]"
  - "formato numérico [C#]"
  - "String.Format (método)"
  - "Console.Write (método)"
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# Tabla de formatos de presentaci&#243;n para valores num&#233;ricos (Referencia de C#)
Se puede dar formato a los resultados numéricos mediante el método <xref:System.String.Format%2A?displayProperty=fullName>, o bien, mediante el método <xref:System.Console.Write%2A?displayProperty=fullName> o <xref:System.Console.WriteLine%2A?displayProperty=fullName>, que llama a `String.Format`.  El formato se determina mediante las cadenas de formato.  La tabla siguiente contiene las cadenas de formato estándar admitidas.  La cadena de formato tiene el formato siguiente: `Axx`, donde `A` es el especificador de formato y `xx` es el especificador de precisión.  El primero controla el tipo de formato aplicado al valor numérico, mientras que el segundo, el número de dígitos significativos o posiciones decimales del resultado.  El valor del especificador de precisión va de 0 a 99.  
  
 Para obtener más información sobre cadenas de formato estándar y personalizadas, vea [Aplicar formato a tipos](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  Para obtener más información sobre el método `String.Format`, vea <xref:System.String.Format%2A?displayProperty=fullName>.  
  
|Especificador de formato|Descripción|Ejemplos|Output|  
|------------------------------|-----------------|--------------|------------|  
|C o c|Moneda|Console.Write\("{0:C}", 2,5\);<br /><br /> Console.Write\("{0:C}", \-2,5\);|$2.50<br /><br /> \($2.50\)|  
|D o d|Decimal|Console.Write\("{0:D5}", 25\);|00025|  
|E o e|Científico|Console.Write\("{0:E}", 250000\);|2,500000E\+005|  
|F o f|Punto fijo|Console.Write\("{0:F2}", 25\);<br /><br /> Console.Write\("{0:F0}", 25\);|25.00<br /><br /> 25|  
|G o g|General|Console.Write\("{0:G}", 2,5\);|2.5|  
|N o n|Número|Console.Write\("{0:N}", 2500000\);|2,500,000.00|  
|X o x|Hexadecimal|Console.Write\("{0:X}", 250\);<br /><br /> Console.Write\("{0:X}", 0xffff\);|FA<br /><br /> FFFF|  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Cadenas con formato numérico estándar](../Topic/Standard%20Numeric%20Format%20Strings.md)   
 [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [string](../../../csharp/language-reference/keywords/string.md)