---
title: Tabla de valores predeterminados (Referencia de C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: f8cf12317f1f0163028db003ff31604480da5d1c
ms.openlocfilehash: 975d416259778e0741347829d8a9c79aaa6cfc8c
ms.contentlocale: es-es
ms.lasthandoff: 08/12/2017

---
# <a name="default-values-table-c-reference"></a>Tabla de valores predeterminados (Referencia de C#)
En la siguiente tabla se muestran los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados. Los constructores predeterminados se invocan mediante el operador `new`, de la manera siguiente:

```csharp
int myInt = new int();
```

La instrucción anterior tiene el mismo efecto que la instrucción siguiente:

```csharp
int myInt = 0;
```

Recuerde que no se permite el uso de variables sin inicializar en C#.

|Tipo de valor|Valor predeterminado|
|----------------|-------------------|
|[bool](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[byte](../../../csharp/language-reference/keywords/byte.md)|0|
|[char](../../../csharp/language-reference/keywords/char.md)|'\0'|
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|0.0M|
|[double](../../../csharp/language-reference/keywords/double.md)|0.0D|
|[enum](../../../csharp/language-reference/keywords/enum.md)|El valor generado por la expresión (E)0, donde E es el identificador de enumeración.|
|[float](../../../csharp/language-reference/keywords/float.md)|0.0F|
|[int](../../../csharp/language-reference/keywords/int.md)|0|
|[long](../../../csharp/language-reference/keywords/long.md)|0L|
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|0|
|[short](../../../csharp/language-reference/keywords/short.md)|0|
|[struct](../../../csharp/language-reference/keywords/struct.md)|El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|[uint](../../../csharp/language-reference/keywords/uint.md)|0|
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|0|
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|0|

## <a name="see-also"></a>Vea también
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Tabla de tipos de valor](../../../csharp/language-reference/keywords/value-types-table.md)   
 [Value Types](../../../csharp/language-reference/keywords/value-types.md)  (Tipos de valor [Referencia de C#])  
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

