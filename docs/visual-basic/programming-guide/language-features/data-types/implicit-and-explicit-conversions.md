---
title: Conversiones implícita y explícita (Visual Basic)
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
ms.openlocfilehash: 8a0909641b653a1800bdf3f50ec1dfe993411824
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a>Conversiones implícita y explícita (Visual Basic)
Un *conversión implícita* no requiere ninguna sintaxis especial en el código fuente. En el ejemplo siguiente, Visual Basic convierte implícitamente el valor de `k` a un valor de punto flotante de precisión simple antes de asignarlo a `q`.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 Un *conversión explícita* utiliza una palabra clave de conversión de tipos. Visual Basic proporciona varias palabras clave que convierten una expresión entre paréntesis en el tipo de datos que desee. Estas palabras clave actúan como funciones, pero el compilador genera el código en línea, por lo que la ejecución es ligeramente más rápida que con una llamada de función.  
  
 En la siguiente extensión del ejemplo anterior, el `CInt` palabra clave convierte el valor de `q` a un entero antes de asignarlo a `k`.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a>Palabras clave para conversiones  
 La siguiente tabla muestra las palabras clave de conversión disponibles.  
  
|Palabra clave de conversión de tipo|Convierte una expresión al tipo de datos|Tipos de datos permitidos de expresión que se va a convertir|  
|---|---|---|  
|`CBool`|[Boolean (tipo de datos)](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `String`, `Object`|  
|`CByte`|[Byte (tipo de datos)](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Cualquier tipo numérico (incluidos `SByte` y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CChar`|[Char (tipo de datos)](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Date (tipo de datos)](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Double (tipos de datos)](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CDec`|[Decimal (tipo de datos)](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CInt`|[Integer (tipo de datos)](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CLng`|[Long (tipo de datos)](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CObj`|[Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Cualquier tipo|  
|`CSByte`|[SByte (tipo de datos)](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Cualquier tipo numérico (incluidos `Byte` y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CShort`|[Short (tipo de datos)](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CSng`|[Single (tipo de datos)](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CStr`|[String (tipo de datos)](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `Char`, `Char` matriz, `Date`, `Object`|  
|`CType`|Tipo especificado después de la coma (`,`)|Al convertir a un *tipo de datos básico* (incluida una matriz de un tipo elemental), los mismos tipos que permitan la palabra clave de conversión correspondiente<br /><br /> Al convertir a un *tipo de datos compuesto*, las interfaces que implementa y las clases de la que hereda<br /><br /> Al convertir a una clase o estructura en la que ha sobrecargado `CType`, esa clase o estructura|  
|`CUInt`|[UInteger (tipo de datos)](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CULng`|[ULong (tipo de datos)](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
|`CUShort`|[UShort (tipo de datos)](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Cualquier tipo numérico (incluidos `Byte`, `SByte`y los tipos enumerados), `Boolean`, `String`, `Object`|  
  
## <a name="the-ctype-function"></a>CType (función)  
 El [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md) funciona en los dos argumentos. La primera es la expresión que se va a convertir y el segundo es la clase de objeto o tipo de datos de destino. Tenga en cuenta que el primer argumento debe ser una expresión, no es un tipo.  
  
 `CType` es un *función inline*, lo que significa que el código compilado realiza la conversión, a menudo llaman a sin generar una función. Esto mejora el rendimiento.  
  
 Para obtener una comparación de `CType` con el otro tipo palabras clave para conversiones, vea [DirectCast (operador)](../../../../visual-basic/language-reference/operators/directcast-operator.md) y [TryCast (operador)](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### <a name="elementary-types"></a>Tipos elementales  
 El siguiente ejemplo muestra el uso de `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a>Tipos compuestos  
 Puede usar `CType` para convertir los valores a tipos de datos compuestos así como en tipos elementales. También puede utilizar para convertir una clase de objeto para el tipo de uno de sus interfaces, como en el ejemplo siguiente.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a>Tipos de matriz  
 `CType` También se puede convertir a tipos de datos de matriz, como en el ejemplo siguiente.  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 Para obtener más información y un ejemplo, vea [conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).  
  
### <a name="types-defining-ctype"></a>Tipos que define CType  
 Puede definir `CType` en una clase o estructura que ha definido. Esto le permite convertir valores a y desde el tipo de la clase o estructura. Para obtener más información y un ejemplo, vea [Cómo: definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Valores que se utilizan con una palabra clave de conversión deben ser válidos para el tipo de datos de destino, o se produce un error. Por ejemplo, si intenta convertir un `Long` a una `Integer`, el valor de la `Long` debe estar dentro del intervalo válido para el `Integer` tipo de datos.  
  
> [!CAUTION]
>  Especificar `CType` para convertir de un tipo de clase a otro produce un error en tiempo de ejecución si el tipo de origen no se deriva el tipo de destino. Este error se produce un <xref:System.InvalidCastException> excepción.  
  
 Sin embargo, si uno de los tipos es una estructura o clase que ha definido, y si ha definido `CType` en esa estructura o clase, una conversión puede tener éxito si satisface los requisitos de su `CType`. Vea [Cómo: definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 Realizar una conversión explícita es también se denomina *conversión* una expresión a una clase de objeto o tipo de datos determinado.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Cómo: convertir un objeto a otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
