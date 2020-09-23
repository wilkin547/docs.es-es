---
title: Widening and Narrowing Conversions
ms.date: 07/20/2015
helpviewer_keywords:
- widening conversions [Visual Basic]
- narrowing conversions [Visual Basic]
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- conversions [Visual Basic], exceptions during conversion
- type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], data type
- conversions [Visual Basic], narrowing
- type conversion [Visual Basic], narrowing
- data type conversion [Visual Basic], widening
- data type conversion [Visual Basic], narrowing
- changing data types [Visual Basic]
- type conversion [Visual Basic], widening
- data type conversion [Visual Basic], exceptions during conversion
- conversions [Visual Basic], widening
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
ms.openlocfilehash: c0e10f5593ce5c81002233516444e415571541f3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058539"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Conversiones de ampliación y de restricción (Visual Basic)

Una consideración importante con la conversión de tipos es si el resultado de la conversión está dentro del intervalo del tipo de datos de destino.  
  
 Una *conversión de ampliación* cambia un valor a un tipo de datos que puede permitir cualquier valor posible de los datos originales.  Las conversiones de ampliación conservan el valor de origen, pero pueden cambiar su representación. Esto sucede si se convierte de un tipo entero a `Decimal` , o de `Char` a `String` .  
  
 Una *conversión de restricción* cambia un valor a un tipo de datos que no pueda mantener algunos de los valores posibles. Por ejemplo, un valor fraccionario se redondea cuando se convierte en un tipo entero y un tipo numérico al que se convierte `Boolean` se reduce a `True` o `False` .  
  
## <a name="widening-conversions"></a>conversiones de ampliación  

 En la tabla siguiente se muestran las conversiones de ampliación estándar.  
  
|Tipo de datos|Se amplía a los tipos de datos <sup>1</sup>|  
|---|---|  
|[SByte](../../../language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Entero](../../../language-reference/data-types/integer-data-type.md)|`Integer`, `Long` , `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[UInteger](../../../language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long` , `ULong` , `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[Long](../../../language-reference/data-types/long-data-type.md)|`Long`, `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[ULong](../../../language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal` , `Single` , `Double` <sup>2</sup>|  
|[Decimal](../../../language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single` , `Double` <sup>2</sup>|  
|[Single](../../../language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../language-reference/data-types/double-data-type.md)|`Double`|  
|Cualquier tipo enumerado ([enumeración](../../../language-reference/statements/enum-statement.md))|Su tipo entero subyacente y cualquier tipo al que se amplíe el tipo subyacente.|  
|[Char](../../../language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Matriz `Char`|`Char` matriz `String`|  
|Cualquier tipo|[Object](../../../language-reference/data-types/object-data-type.md)|  
|Cualquier tipo derivado|Cualquier tipo base del que se derive <sup>3</sup>.|  
|Cualquier tipo|Cualquier interfaz que implemente.|  
|[Nothing](../../../language-reference/nothing.md)|Cualquier tipo de datos o tipo de objeto.|  
  
 <sup>1</sup> por definición, cada tipo de datos se amplía a sí mismo.  
  
 <sup>2</sup> las conversiones de `Integer` , `UInteger` , `Long` , `ULong` o `Decimal` a `Single` o `Double` pueden dar lugar a una pérdida de precisión, pero nunca en pérdida de magnitud. En este sentido, no incurre en la pérdida de información.  
  
 <sup>3</sup> podría parecer sorprendente que una conversión de un tipo derivado a uno de sus tipos base sea de ampliación. La justificación es que el tipo derivado contiene todos los miembros del tipo base, por lo que se califica como una instancia del tipo base. En la dirección opuesta, el tipo base no contiene ningún miembro nuevo definido por el tipo derivado.  
  
 Las conversiones de ampliación siempre se realizan correctamente en tiempo de ejecución y nunca provocan pérdida de datos. Siempre se pueden realizar de forma implícita, ya sea que la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md) establezca el modificador de comprobación de tipos en `On` o en `Off` .  
  
## <a name="narrowing-conversions"></a>conversiones de restricción  

 Entre las conversiones de restricción estándar se incluyen las siguientes:  
  
- Las direcciones inversas de las conversiones de ampliación en la tabla anterior (excepto en que cada tipo se amplía a sí mismo)  
  
- Conversiones en cualquier dirección entre [Boolean](../../../language-reference/data-types/boolean-data-type.md) y cualquier tipo numérico  
  
- Conversiones de cualquier tipo numérico a cualquier tipo enumerado ( `Enum` )  
  
- Conversiones en cualquier dirección entre la [cadena](../../../language-reference/data-types/string-data-type.md) y cualquier tipo numérico, `Boolean` o [fecha](../../../language-reference/data-types/date-data-type.md)  
  
- Conversiones de un tipo de datos o de un tipo de objeto a un tipo derivado de él  
  
 Las conversiones de restricción no siempre se realizan correctamente en tiempo de ejecución y pueden producir un error o provocar la pérdida de datos. Se produce un error si el tipo de datos de destino no puede recibir el valor que se está convirtiendo. Por ejemplo, una conversión numérica puede producir un desbordamiento. El compilador no permite realizar conversiones de restricción implícitamente a menos que la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md) establezca el modificador de comprobación de tipos en `Off` .  
  
> [!NOTE]
> Se suprime el error de conversión de restricción para las conversiones de los elementos de una `For Each…Next` colección a la variable de control de bucle. Para obtener más información y ejemplos, vea la sección acerca de las conversiones de restricción en [for each... Instrucción siguiente](../../../language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Cuándo usar las conversiones de restricción  

 Se usa una conversión de restricción cuando se sabe que el valor de origen se puede convertir al tipo de datos de destino sin errores o pérdidas de datos. Por ejemplo, si tiene un `String` que sabe que contiene "true" o "false", puede utilizar la `CBool` palabra clave para convertirlo en `Boolean` .  
  
## <a name="exceptions-during-conversion"></a>Excepciones durante la conversión  

 Dado que las conversiones de ampliación siempre se realizan correctamente, no inician excepciones. Cuando se producen errores en las conversiones de restricción, normalmente se producen las excepciones siguientes:  
  
- <xref:System.InvalidCastException> : Si no se define ninguna conversión entre los dos tipos  
  
- <xref:System.OverflowException> : (solo tipos enteros) si el valor convertido es demasiado grande para el tipo de destino  
  
 Si una clase o estructura define una [función ctype](../../../language-reference/functions/ctype-function.md) para actuar como un operador de conversión hacia o desde esa clase o estructura, que `CType` puede producir cualquier excepción que considere adecuada. Además, esto `CType` podría llamar a Visual Basic funciones o métodos de .NET Framework, que a su vez podrían producir una variedad de excepciones.  
  
## <a name="changes-during-reference-type-conversions"></a>Cambios durante las conversiones de tipos de referencia  

 Una conversión de un *tipo de referencia* solo copia el puntero en el valor. El propio valor no se copia ni se modifica de ninguna manera. Lo único que puede cambiar es el tipo de datos de la variable que contiene el puntero. En el ejemplo siguiente, el tipo de datos se convierte de la clase derivada a su clase base, pero el objeto al que apuntan ambas variables ahora no cambia.  
  
```vb  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>Vea también

- [Tipo de datos](index.md)
- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Conversiones implícitas y explícitas](implicit-and-explicit-conversions.md)
- [Conversiones entre cadenas y otros tipos](conversions-between-strings-and-other-types.md)
- [Cómo: Convertir un objeto en otro tipo en Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Conversiones de matriz](array-conversions.md)
- [Tipo de datos](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
