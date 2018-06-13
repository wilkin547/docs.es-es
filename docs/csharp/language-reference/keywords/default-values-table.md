---
title: Tabla de valores predeterminados (Referencia de C#)
description: Sepa cuáles son los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218795"
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
|[bool](bool.md)|`false`|
|[byte](byte.md)|0|
|[char](char.md)|'\0'|
|[decimal](decimal.md)|0M|
|[double](double.md)|0.0D|
|[enum](enum.md)|El valor generado por la expresión (E)0, donde E es el identificador de enumeración.|
|[float](float.md)|0.0F|
|[int](int.md)|0|
|[long](long.md)|0L|
|[sbyte](sbyte.md)|0|
|[short](short.md)|0|
|[struct](struct.md)|El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|[uint](uint.md)|0|
|[ulong](ulong.md)|0|
|[ushort](ushort.md)|0|

## <a name="see-also"></a>Vea también
 [Referencia de C#](../index.md)  
 [Guía de programación de C#](../../programming-guide/index.md)  
 [Tabla de tipos de valor](value-types-table.md)  
 [Tipos de valor](value-types.md)  
 [Tabla de tipos integrados](built-in-types-table.md)  
 [Tablas de referencia para tipos](reference-tables-for-types.md)
