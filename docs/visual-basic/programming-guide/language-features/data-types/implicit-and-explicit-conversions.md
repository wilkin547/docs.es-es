---
title: Conversiones implícitas y explícitas
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 2858dafd2531bd846ad89672348d103f385c4511
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393836"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Conversiones implícita y explícita (Visual Basic)

Una *conversión implícita* no requiere ninguna sintaxis especial en el código fuente. En el ejemplo siguiente, Visual Basic convierte implícitamente el valor de `k` en un valor de punto flotante de precisión sencilla antes de asignarlo a `q` .

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

Una *conversión explícita* utiliza una palabra clave de conversión de tipos. Visual Basic proporciona varias palabras clave, que convierten una expresión entre paréntesis en el tipo de datos deseado. Estas palabras clave actúan como funciones, pero el compilador genera el código insertado, por lo que la ejecución es ligeramente más rápida que con una llamada de función.

En la siguiente extensión del ejemplo anterior, la `CInt` palabra clave convierte el valor de de `q` nuevo en un entero antes de asignarlo a `k` .

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a>Palabras clave para conversiones

En la tabla siguiente se muestran las palabras clave de conversión disponibles.

|Palabra clave de conversión de tipos|Convierte una expresión al tipo de datos|Tipos de datos permitidos de la expresión que se va a convertir|
|---|---|---|
|`CBool`|[Tipo de datos Boolean](../../../language-reference/data-types/boolean-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `String` ,`Object`|
|`CByte`|[Tipo de datos Byte](../../../language-reference/data-types/byte-data-type.md)|Cualquier tipo numérico (incluidos `SByte` y tipos enumerados), `Boolean` , `String` ,`Object`|
|`CChar`|[Tipo de datos Char](../../../language-reference/data-types/char-data-type.md)|`String`, `Object`|
|`CDate`|[Tipo de datos Date](../../../language-reference/data-types/date-data-type.md)|`String`, `Object`|
|`CDbl`|[Tipo de datos Double](../../../language-reference/data-types/double-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CDec`|[Tipo de datos Decimal](../../../language-reference/data-types/decimal-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CInt`|[Tipo de datos Integer](../../../language-reference/data-types/integer-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CLng`|[Tipo de datos Long](../../../language-reference/data-types/long-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CObj`|[Object Data Type](../../../language-reference/data-types/object-data-type.md)|Cualquier tipo|
|`CSByte`|[Tipo de datos SByte](../../../language-reference/data-types/sbyte-data-type.md)|Cualquier tipo numérico (incluidos `Byte` y tipos enumerados), `Boolean` , `String` ,`Object`|
|`CShort`|[Tipo de datos Short](../../../language-reference/data-types/short-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CSng`|[Tipo de datos Single](../../../language-reference/data-types/single-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CStr`|[String (Tipo de datos)](../../../language-reference/data-types/string-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `Char` , `Char` array, `Date` ,`Object`|
|`CType`|Tipo especificado después de la coma ( `,` )|Al convertir a un *tipo de datos elemental* (incluida una matriz de un tipo elemental), los mismos tipos que se permiten para la palabra clave de conversión correspondiente<br /><br /> Al convertir a un *tipo de datos compuesto*, las interfaces que implementa y las clases de las que hereda<br /><br /> Al convertir a una clase o estructura en la que se ha sobrecargado `CType` , esa clase o estructura|
|`CUInt`|[Tipo de datos UInteger](../../../language-reference/data-types/uinteger-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CULng`|[Tipo de datos ULong](../../../language-reference/data-types/ulong-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|
|`CUShort`|[Tipo de datos UShort](../../../language-reference/data-types/ushort-data-type.md)|Cualquier tipo numérico (incluidos `Byte` los `SByte` tipos enumerados, y), `Boolean` , `String` ,`Object`|

## <a name="the-ctype-function"></a>La función CType

La [función ctype](../../../language-reference/functions/ctype-function.md) funciona con dos argumentos. El primero es la expresión que se va a convertir y el segundo es el tipo de datos de destino o la clase de objeto. Tenga en cuenta que el primer argumento debe ser una expresión, no un tipo.

`CType`es una *función insertada*, lo que significa que el código compilado realiza la conversión, a menudo sin generar una llamada de función. De este modo se aumenta el rendimiento.

Para obtener una comparación de `CType` con las otras palabras clave de conversión de tipos, vea operador [DirectCast](../../../language-reference/operators/directcast-operator.md) y [operador TryCast](../../../language-reference/operators/trycast-operator.md).

### <a name="elementary-types"></a>Tipos elementales

El siguiente ejemplo muestra el uso de `CType`.

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a>Tipos compuestos

Puede usar `CType` para convertir valores en tipos de datos compuestos y en tipos elementales. También se puede utilizar para forzar una clase de objeto al tipo de una de sus interfaces, como en el ejemplo siguiente.

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a>Tipos de matriz

`CType`también puede convertir los tipos de datos de matriz, como en el ejemplo siguiente.

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

Para obtener más información y un ejemplo, vea [conversiones de matrices](array-conversions.md).

### <a name="types-defining-ctype"></a>Tipos que definen CType

Puede definir `CType` en una clase o estructura que haya definido. Esto le permite convertir valores a y desde el tipo de la clase o estructura. Para obtener más información y un ejemplo, vea [Cómo: definir un operador de conversión](../procedures/how-to-define-a-conversion-operator.md).

> [!NOTE]
> Los valores utilizados con una palabra clave de conversión deben ser válidos para el tipo de datos de destino o se produce un error. Por ejemplo, si intenta convertir `Long` en `Integer` , el valor de `Long` debe estar dentro del intervalo válido para el `Integer` tipo de datos.

> [!CAUTION]
> `CType`Si se especifica que se realice la conversión de un tipo de clase a otro, se producirá un error en tiempo de ejecución si el tipo de origen no se deriva del tipo de destino. Este tipo de error produce una <xref:System.InvalidCastException> excepción.

Sin embargo, si uno de los tipos es una estructura o clase definida, y si ha definido `CType` en esa estructura o clase, una conversión puede realizarse correctamente si satisface los requisitos de `CType` . Vea [Cómo: definir un operador de conversión](../procedures/how-to-define-a-conversion-operator.md).

La realización de una conversión explícita también se conoce como *convertir* una expresión en un tipo de datos o clase de objeto determinado.

## <a name="see-also"></a>Consulte también

- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Conversiones entre cadenas y otros tipos](conversions-between-strings-and-other-types.md)
- [Cómo: Convertir un objeto en otro tipo en Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Estructuras](structures.md)
- [Tipos de datos](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
