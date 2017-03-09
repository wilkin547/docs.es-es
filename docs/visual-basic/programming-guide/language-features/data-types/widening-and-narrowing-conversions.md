---
title: "Conversiones de ampliaci&#243;n y de restricci&#243;n (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "cambiar tipos de datos"
  - "conversiones, tipo de datos"
  - "conversiones, excepciones durante la conversión"
  - "conversiones, de restricción"
  - "conversiones, tipo"
  - "conversiones, de ampliación"
  - "conversión de tipos de datos, excepciones durante la conversión"
  - "conversión de tipos de datos, de restricción"
  - "conversión de tipos de datos, de ampliación"
  - "tipos de datos [Visual Basic], cambiar"
  - "conversiones de restricción"
  - "conversión de tipos, excepciones durante la conversión"
  - "conversión de tipos, de restricción"
  - "conversión de tipos, de ampliación"
  - "variables [Visual Basic], cambiar tipo de datos"
  - "conversiones de ampliación"
ms.assetid: 058c3152-6c28-4268-af44-2209e774f0bd
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Conversiones de ampliaci&#243;n y de restricci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una consideración importante de una conversión de tipos es si el resultado de la conversión está dentro del intervalo del tipo de datos de destino.  
  
 *Una conversión de ampliación* cambia un valor a un tipo de datos que puede tener en cuenta cualquier valor posible de los datos originales.  Las conversiones de ampliación conservan el valor de origen pero pueden cambiar su representación.  Esto ocurre si se convierte un tipo entero en `Decimal`, o de `Char` a `String`.  
  
 Una *conversión de restricción* cambia un valor a un tipo de datos que quizás no pueda contener alguno de los valores posibles.  Por ejemplo, un valor fraccionario se redondea cuando se convierte a un tipo entero, y reducen a un tipo numérico que se convierte a `Boolean` a `True` o a `False`.  
  
## Conversiones de ampliación  
 La tabla siguiente muestra las conversiones de ampliación estándar.  
  
|||  
|-|-|  
|Tipo de datos|Se amplía a los siguientes tipos de datos <sup>1</sup>|  
|[SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|`SByte`, `Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|`Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Short](../../../../visual-basic/language-reference/data-types/short-data-type.md)|`Short`, `Integer`, `Long`, `Decimal`, `Single`, `Double`|  
|[UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|`UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double`|  
|[Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|`Integer`, `Long`, `Decimal`, `Single`, `Double`<sup>2</sup>|  
|[UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|`UInteger`, `Long`, `ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Long](../../../../visual-basic/language-reference/data-types/long-data-type.md)|`Long`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|`ULong`, `Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`, `Single`, `Double` <sup>2</sup>|  
|[Simple](../../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`, `Double`|  
|[Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
|Cualquier tipo enumerado \([Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)\)|El tipo entero subyacente y cualquier tipo al que se amplía el tipo subyacente.|  
|[Char](../../../../visual-basic/language-reference/data-types/char-data-type.md)|`Char`, `String`|  
|Matriz `Char`|Matriz de tipo `Char`, `String`|  
|Cualquier tipo|[Objeto.](../../../../visual-basic/language-reference/data-types/object-data-type.md)|  
|Cualquier tipo derivado|Cualquier tipo base del que sea derivado <sup>3</sup>.|  
|Cualquier tipo|Las interfaces que implementa.|  
|[Nothing](../../../../visual-basic/language-reference/nothing.md)|cualquier tipo de datos o tipo de objeto.|  
  
 <sup>1</sup> Por definición, cada tipo de datos se amplia a sí mismo.  
  
 <sup>2</sup> Las conversiones de `Integer`, `UInteger`, `Long`, `ULong` o `Decimal` a `Single` o `Double` podrían generar una pérdida de precisión pero nunca una pérdida de magnitud.  En este sentido, no provocan pérdida de información.  
  
 <sup>3</sup> Puede parecer sorprendente que una conversión de un tipo derivado en uno de sus tipos base sea una ampliación.  La justificación está en el hecho de que el tipo derivado contiene todos lo\<s miembros del tipo base, por lo que se califica como una instancia del tipo base.  A la inversa, el tipo base no contiene nuevos miembros definidos por el tipo derivado.  
  
 Las conversiones de ampliación son siempre satisfactorias en tiempo de ejecución y no provocan nunca pérdida de datos.  Siempre puede realizarlas implícitamente, independientemente de si [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) establece el modificador de comprobación de tipos en `On` o en `Off`.  
  
## Conversiones de restricción  
 Las conversiones de restricción estándar incluyen:  
  
-   Las direcciones inversas de las conversiones de ampliación en la tabla anterior \(sólo que cada tipo se amplía a sí mismo\)  
  
-   Conversiones en ambas direcciones entre [Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) y cualquier tipo numérico  
  
-   Conversiones de cualquier tipo numérico a cualquier tipo enumerado \(`Enum`\)  
  
-   Conversiones en ambas direcciones entre [String](../../../../visual-basic/language-reference/data-types/string-data-type.md) y cualquier tipo numérico, `Boolean` o [Date](../../../../visual-basic/language-reference/data-types/date-data-type.md)  
  
-   Conversiones de un tipo de datos o tipo de objeto en un tipo derivado del mismo  
  
 Las conversiones de restricción no son siempre satisfactorias en tiempo de ejecución y pueden generar errores o provocar pérdida de datos.  Se produce un error si el tipo de datos de destino no puede recibir el valor que se está convirtiendo.  Por ejemplo, una conversión numérica puede provocar un desbordamiento.  El compilador no le permite realizar las conversiones de restricción implícitamente a menos que [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) establezca el modificador de comprobación de tipos en `Off`.  
  
> [!NOTE]
>  El error de la conversión de restricción se suprime en las conversiones de los elementos de una colección `For Each…Next` a la variable de control del bucle.  Para obtener más información y ejemplos, consulte la sección "Conversiones de restricción" en [For Each...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### Cuándo se utilizan las conversiones de restricción  
 Se utiliza una conversión de restricción cuando se sabe que el valor de origen se puede convertir en el tipo de datos de destino sin error o pérdida de datos.  Por ejemplo, si tiene `String` sabe que contiene “True” o “False”, puede utilizar la palabra clave de `CBool` para convertirla en `Boolean`.  
  
## Excepciones durante la conversión  
 Como las conversiones de ampliación siempre son satisfactorias, no producen excepciones.  Las conversiones de restricción, cuando se produce un error, suelen producir las excepciones siguientes:  
  
-   <xref:System.InvalidCastException>: si no hay definida ninguna conversión entre los dos tipos  
  
-   <xref:System.OverflowException>: \(tipos enteros solo\) si el valor convertido es demasiado grande para el tipo de destino  
  
 Si una clase o estructura define [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md) para que actúe como un operador de conversión a esa clase o estructura o desde ellas, `CType` puede producir cualquier excepción que considere apropiada.  Además, `CType` puede llamar a las funciones de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] o a los métodos de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] que, a su vez, pueden producir una variedad de excepciones.  
  
## Cambios durante las conversiones de tipos de referencia  
 Una conversión de un *tipo de referencia* sólo copia el puntero al valor.  El valor en sí mismo no se copia ni se cambia en modo alguno.  Lo único que puede cambiar es el tipo de datos de la variable que contiene el puntero.  En el ejemplo siguiente, el tipo de datos cambia de la clase derivada a su clase base, pero el objeto al que apuntan ahora ambas variables no se modifica.  
  
```  
' Assume class cSquare inherits from class cShape.  
Dim shape As cShape  
Dim square As cSquare = New cSquare  
' The following statement performs a widening  
' conversion from a derived class to its base class.  
shape = square  
```  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Cómo: Convertir un objeto en otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)