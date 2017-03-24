---
title: "Tabla de valores predeterminados (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "constructores [C#], valores devueltos"
  - "palabras clave [C], nuevas"
  - "constructor predeterminado [C#]"
  - "valores predeterminados [C#]"
  - "tipos de valor [C#], inicialización"
  - "variables [C#], tipos de valor"
  - "constructores [C#], constructor predeterminado"
  - "tipos [C#], valores devueltos por el constructor predeterminado"
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Tabla de valores predeterminados (Referencia de C#)
La siguiente tabla muestra los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados.  Los constructores predeterminados se invocan mediante el operador `new`, de la manera siguiente:  
  
```  
int myInt = new int();  
```  
  
 La instrucción anterior tiene el mismo efecto que la instrucción siguiente:  
  
```  
int myInt = 0;  
```  
  
 Recuerde que el uso de variables no inicializadas no está permitido en C\#.  
  
|Tipo de valor|Valor predeterminado|  
|-------------------|--------------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`false`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|0|  
|[char](../../../csharp/language-reference/keywords/char.md)|'\\0'|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|0,0M|  
|[double](../../../csharp/language-reference/keywords/double.md)|0,0D|  
|[enum](../../../csharp/language-reference/keywords/enum.md)|El valor producido por la expresión \(E\)0, donde E es el identificador de la enumeración.|  
|[float](../../../csharp/language-reference/keywords/float.md)|0,0F|  
|[Valor int.](../../../csharp/language-reference/keywords/int.md)|0|  
|[long](../../../csharp/language-reference/keywords/long.md)|0L|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|0|  
|[short](../../../csharp/language-reference/keywords/short.md)|0|  
|[struct](../../../csharp/language-reference/keywords/struct.md)|El valor obtenido al asignar los valores predeterminados a los campos de tipo de valor y el valor `null` a los campos de tipo de referencia.|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|0|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|0|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|0|  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tabla de tipos de valor](../../../csharp/language-reference/keywords/value-types-table.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)