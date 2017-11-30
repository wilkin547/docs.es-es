---
title: Tabla de tipos integrados (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9d1e4945526a862074e73e608185696328946be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="built-in-types-table-c-reference"></a>Tabla de tipos integrados (Referencia de C#)
En la siguiente tabla se muestran las palabras clave para los tipos de C# integrados, que son alias de los tipos predefinidos en el espacio de nombres <xref:System>.  
  
|Tipo de C#|Tipo de .NET Framework|  
|--------------|-------------------------|  
|[bool](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[object](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[string](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a>Comentarios  
 A todos los tipos de la tabla, excepto `object` y `string`, se les hace referencia como tipos simples.  
  
 Las palabras clave de tipo de C# y sus alias son intercambiables. Por ejemplo, puede declarar una variable de entero con cualquiera de las siguientes declaraciones:  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 Para mostrar el tipo actual de cualquier tipo de C#, use el método del sistema `GetType()`. Por ejemplo, la instrucción siguiente muestra el alias de sistema que representa el tipo de `myVariable`:  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 También puede usar el operador [typeof](../../../csharp/language-reference/keywords/typeof.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)  
 [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
 [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
