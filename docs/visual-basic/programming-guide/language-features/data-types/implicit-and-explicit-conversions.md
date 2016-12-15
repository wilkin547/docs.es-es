---
title: "Conversiones impl&#237;cita y expl&#237;cita (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "convertir"
  - "convertir, tipos de datos"
  - "cambiar tipos de datos"
  - "conversiones"
  - "conversiones, tipo de datos"
  - "conversiones, explícita"
  - "conversiones, implícita"
  - "conversiones, tipo"
  - "CType (función), conversiones"
  - "conversión de tipos de datos, explícita"
  - "conversión de tipos de datos, implícita"
  - "tipos de datos [Visual Basic], convertir"
  - "conversiones explícitas de tipos de datos"
  - "conversiones implícitas de tipos de datos"
  - "conversión de tipos, conversiones explícitas"
  - "conversión de tipos, conversiones implícitas"
  - "variables [Visual Basic], cambiar tipo de datos"
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Conversiones impl&#237;cita y expl&#237;cita (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una *conversión implícita* no requiere ninguna sintaxis especial en el código fuente.  En el ejemplo siguiente, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convierte el valor de `k` implícitamente en un valor de punto flotante de precisión sencilla antes de asignarlo a `q`.  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 Una *conversión explícita* usa una palabra clave de conversión de tipos.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona varias palabras clave de este tipo, que convierten una expresión entre paréntesis en el tipo de datos deseado.  Estas palabras clave actúan como funciones, pero el compilador genera el código en la misma línea, de modo que la ejecución es un poco más rápida que con una llamada de función.  
  
 En esta extensión del ejemplo anterior, la palabra clave `CInt` convierte el valor de `q` de nuevo en un entero antes de asignarlo a `k`.  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## Palabras clave para conversiones  
 La tabla siguiente muestra las palabras clave de conversión disponibles.  
  
||||  
|-|-|-|  
|Palabra clave de conversión de tipos|Convierte una expresión en el siguiente tipo de datos|Tipos de datos permitidos para la expresión que se va a convertir|  
|`CBool`|[Boolean \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `String`, `Object`|  
|`CByte`|[Byte \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|Cualquier tipo numérico \(incluidos `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CChar`|[Char \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`String`, `Object`|  
|`CDate`|[Date \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/date-data-type.md)|`String`, `Object`|  
|`CDbl`|[Double \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/double-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CDec`|[Decimal \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CInt`|[Integer \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CLng`|[Long \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/long-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CObj`|[Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)|Cualquier tipo|  
|`CSByte`|[SByte \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|Cualquier tipo numérico \(incluido `Byte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CShort`|[Short \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/short-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CSng`|[Single \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/single-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CStr`|[String \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/string-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `Char`, matriz `Char`, `Date`, `Object`|  
|`CType`|Tipo especificado después de la coma \(`,`\)|Al convertir a un *tipo de datos básico* \(incluida una matriz de un tipo básico\), se permiten los mismos tipos para la palabra clave de conversión correspondiente<br /><br /> Al convertir a un *tipo de datos compuesto*, las interfaces que implementa y las clases de las que hereda<br /><br /> Al convertir a una clase o estructura en que ha sobrecargado `CType`, esta clase o estructura|  
|`CUInt`|[UInteger \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CULng`|[ULong \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
|`CUShort`|[UShort \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|Cualquier tipo numérico \(incluidos `Byte`, `SByte` y los tipos enumerados\), `Boolean`, `String`, `Object`|  
  
## La función CType  
 [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md) actúa sobre dos argumentos.  El primero es la expresión que va a convertirse y el segundo es la clase de objeto o el tipo de datos de destino.  Observe que el primer argumento debe ser una expresión, no un tipo.  
  
 `CType` es una *función en línea*, lo que significa que el código compilado realiza la conversión, a menudo sin generar una llamada a la función.  Esto mejora el rendimiento.  
  
 Para una comparación de `CType` con las otras palabras clave de conversión de tipos, vea [DirectCast \(Operador\)](../../../../visual-basic/language-reference/operators/directcast-operator.md) y [TryCast \(Operador\)](../../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
### Tipos básicos  
 El siguiente ejemplo muestra el uso de `CType`.  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### Tipos compuestos  
 Puede utilizar `CType` para convertir valores en tipos de datos compuestos así como en tipos básicos.  También puede utilizarlo para convertir una clase de objeto en el tipo de una de sus interfaces, como en el ejemplo siguiente.  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### Tipos de matriz  
 `CType` también puede convertir tipos de datos de matrices, como en el ejemplo siguiente.  
  
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
  
 Para obtener más información y un ejemplo, vea [Conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).  
  
### Tipos que define CType  
 Puede definir `CType` en una clase o estructura que haya definido.  Esto le permite convertir los valores al tipo de su clase o estructura y desde él.  Para obtener más información y un ejemplo, vea [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
> [!NOTE]
>  Los valores utilizados con una palabra clave de conversión deben ser válidos para el tipo de datos de destino; de lo contrario, se produce un error.  Por ejemplo, si intenta convertir un tipo `Long` en `Integer`, el valor de `Long` debe estar dentro del intervalo válido para el tipo de datos `Integer`.  
  
> [!CAUTION]
>  Especificar `CType` para convertir de un tipo de clase a otro produce un error en tiempo de ejecución si el tipo de origen no deriva del tipo de destino.  Este tipo de error produce una excepción <xref:System.InvalidCastException>.  
  
 Sin embargo, si uno de los tipos es una estructura o clase que ha definido y si ha definido `CType` en esa estructura o clase, una conversión puede tener éxito si satisface los requisitos de `CType`.  Vea [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
 La acción de realizar una conversión explícita se denomina también *convertir* una expresión en un determinado tipo de datos o clase de objeto.  
  
## Vea también  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Cómo: Convertir un objeto en otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)