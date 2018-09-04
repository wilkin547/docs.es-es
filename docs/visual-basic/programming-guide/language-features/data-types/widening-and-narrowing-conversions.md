---
title: Conversiones de ampliación y de restricción (Visual Basic)
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
ms.openlocfilehash: ad49e5443016dc4fed57be4a991df9f6d6095b55
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519282"
---
# <a name="widening-and-narrowing-conversions-visual-basic"></a>Conversiones de ampliación y de restricción (Visual Basic)
Una consideración importante con una conversión de tipos es si el resultado de la conversión está dentro del intervalo del tipo de datos de destino.  
  
 Un *una conversión de ampliación* cambia un valor a un tipo de datos que puede permitir que para cualquier valor posible de los datos originales.  Conversiones de ampliación conservan el valor de origen, pero pueden cambiar su representación. Esto sucede si convierte de un tipo integral a `Decimal`, o desde `Char` a `String`.  
  
 Una *conversión de restricción* cambia un valor a un tipo de datos que no pueda mantener algunos de los valores posibles. Por ejemplo, un valor fraccionario se redondea al convertirla a un tipo entero y un tipo numérico que se va a convertir en `Boolean` se reduce a cualquiera `True` o `False`.  
  
## <a name="widening-conversions"></a>conversiones de ampliación  
 En la tabla siguiente se muestra las conversiones de ampliación estándar.  
  
|Tipo de datos|Se amplía a tipos de datos <sup>1</sup>|  
|---|---|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double`<sup>2</sup>|  
|[Single](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Cualquier tipo enumerado ([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md))|Su tipo entero subyacente y cualquier tipo al que se amplía el tipo subyacente.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Matriz `Char`|`Char` matriz, `String`|  
|Cualquier tipo|[Objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Cualquier tipo derivado|Cualquier base de la que se deriva del tipo <sup>3</sup>.|  
|Cualquier tipo|Cualquier interfaz que implementa.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|Cualquier tipo de datos o el tipo de objeto.|  
  
 <sup>1</sup> por definición, todos los tipos de datos se amplía a sí mismo.  
  
 <sup>2</sup> conversiones de `Integer`, `UInteger`, `Long`, `ULong`, o `Decimal` a `Single` o `Double` puede dar lugar a pérdida de precisión, pero nunca una pérdida de magnitud. En este sentido, no provocan pérdida de información.  
  
 <sup>3</sup> , puede resultar sorprendente que sea una ampliación una conversión de un tipo derivado a uno de sus tipos bases. La justificación es que el tipo derivado contiene a todos los miembros del tipo base, por lo que se califica como una instancia del tipo base. En la dirección opuesta, el tipo base no contiene a nuevos miembros definidos por el tipo derivado.  
  
 Conversiones de ampliación siempre se realizan correctamente en tiempo de ejecución y nunca incurrir en pérdida de datos. Siempre puede realizarlas implícitamente, ya sea el [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) establece el tipo de conmutador para la comprobación `On` o a `Off`.  
  
## <a name="narrowing-conversions"></a>conversiones de restricción  
 Las conversiones de restricción estándares incluyen lo siguiente:  
  
-   Las direcciones inversas de las conversiones de ampliación en la anterior tabla (excepto en que cada tipo se amplía a sí mismo)  
  
-   Conversiones en ambas direcciones entre [booleano](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) y cualquier tipo numérico  
  
-   Conversiones de cualquier tipo numérico a cualquier tipo enumeran (`Enum`)  
  
-   Conversiones en ambas direcciones entre [cadena](../../../../visual-basic/language-reference/data-types/string-data-type.md) y cualquier tipo numérico, `Boolean`, o [fecha](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Conversiones de un tipo de datos o un objeto de tipo a un tipo derivado de este  
  
 Las conversiones de restricción no siempre se realizan correctamente en tiempo de ejecución y pueden producir errores o provocar pérdida de datos. Se produce un error si el tipo de datos de destino no puede recibir el valor que se va a convertir. Por ejemplo, una conversión numérica puede provocar un desbordamiento. El compilador no permite realizar conversiones de restricción implícitamente a menos que el [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) establece el tipo de conmutador para la comprobación `Off`.  
  
> [!NOTE]
>  Se suprime el error de conversión de restricción en las conversiones de los elementos de un `For Each…Next` colección a la variable de control de bucle. Para obtener más información y ejemplos, vea la sección "Narrowing Conversions" en [For Each... Instrucción Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="when-to-use-narrowing-conversions"></a>Cuándo utilizar las conversiones de restricción  
 Use una conversión de restricción cuando se sabe que el valor de origen se puede convertir al tipo de datos de destino sin error o pérdida de datos. Por ejemplo, si tiene un `String` que sabe que contiene "True" o "False", puede usar el `CBool` palabra clave para convertirlo en `Boolean`.  
  
## <a name="exceptions-during-conversion"></a>Excepciones durante la conversión  
 Dado que las conversiones de ampliación siempre se realice correctamente, no producen excepciones. Conversiones de restricción, cuando fallan, suelen producen las excepciones siguientes:  
  
-   <xref:System.InvalidCastException> : si no se define ninguna conversión entre los dos tipos  
  
-   <xref:System.OverflowException> : (solo tipos enteros) si el valor convertido es demasiado grande para el tipo de destino  
  
 Si define una clase o estructura un [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) para que actúe como un operador de conversión a o desde esa clase o estructura, que `CType` puede producir cualquier excepción que considere adecuada. Además, que `CType` podría llamar a funciones de Visual Basic o [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] métodos, que a su vez pueden producir una variedad de excepciones.  
  
## <a name="changes-during-reference-type-conversions"></a>Cambios durante las conversiones de tipos de referencia  
 Una conversión de un *tipo de referencia* sólo copia el puntero al valor. El valor en sí no se copia ni modificarse de ninguna manera. Lo único que puede cambiar es el tipo de datos de la variable que contiene el puntero. En el ejemplo siguiente, se convierte el tipo de datos de la clase derivada a su clase base, pero no se modifica el objeto que ambas variables apuntan ahora a.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Cómo: convertir un objeto a otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Conversiones de matriz](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)  
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
