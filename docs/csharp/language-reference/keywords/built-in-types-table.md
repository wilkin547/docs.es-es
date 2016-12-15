---
title: "Tabla de tipos integrados (Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "tipos integrados de C#"
  - "tipos [C#], integrados"
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Tabla de tipos integrados (Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La siguiente tabla muestra las palabras clave para los tipos integrados de C\#, las cuales son alias de tipos predefinidos en el espacio de nombres <xref:System>.  
  
|Tipo de C\#|Tipo de .NET Framework|  
|-----------------|----------------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[Valor int.](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[Objeto.](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## Comentarios  
 Todos los tipos de la tabla, excepto `object` y `string`, se conocen como tipos simples.  
  
 Las palabras clave de tipos de C\# y sus alias son intercambiables.  Por ejemplo, se puede declarar una variable entera de cualquiera de estas dos formas:  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 Para mostrar el tipo real de cualquier tipo de C\#, utilice el método del sistema `GetType()`.  Por ejemplo, la siguiente instrucción muestra el alias de sistema que representa el tipo de `myVariable`:  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 También se puede utilizar el operador [typeof](../../../csharp/language-reference/keywords/typeof.md).  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)   
 [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md)   
 [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)