---
title: Resumen de tipos de datos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Boolean data type [Visual Basic], supported types in Visual Basic
- storage [Visual Basic], order of storage
- data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], supported types in Visual Basic
- notation [Visual Basic], scientific
- memory requirements, data types
- user-defined data types [Visual Basic], Visual Basic
- Date data type [Visual Basic], Visual Basic
- Visual Basic, data types
- storage [Visual Basic], allocation
- Integer data type [Visual Basic], Visual Basic data types
- storage [Visual Basic], space
- Variant data types [Visual Basic], supported types in Visual Basic
- Char data type [Visual Basic], Visual Basic data types
- intrinsic data types [Visual Basic]
- memory consumption [Visual Basic], data types
- single-precision numbers
- data types [Visual Basic], order of storage
- Long data type [Visual Basic], supported types in Visual Basic
- String data type [Visual Basic], Visual Basic data types
- storage order, data types
- StructLayoutAttribute class, Visual Basic data type storage
- scientific notation
- Double data type [Visual Basic], Visual Basic data types
- Byte data type [Visual Basic], Visual Basic data types
- Object data type [Visual Basic], supported types in Visual Basic
- data types [Visual Basic], storage allocation
- double-precision numbers
- data types [Visual Basic], summary
- dates [Visual Basic], data types
- strings [Visual Basic], data types
- memory consumption
- storage order, controlling in Visual Basic
- data types [Visual Basic], memory requirements
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
ms.openlocfilehash: 14eaacda83576b6c38d4783fba7c898a8c4aaa5d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746795"
---
# <a name="data-type-summary-visual-basic"></a>Resumen de tipos de datos (Visual Basic)
En la tabla siguiente se muestra los tipos de datos de Visual Basic, sus tipos auxiliares de common language runtime, su asignación de almacenamiento nominal y sus intervalos de valores.  
  
|Tipo de Visual Basic|Estructura de tipo de Common language runtime|Asignación de almacenamiento nominal|Intervalo de valores|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Depende de la implementación de plataforma|`True` o `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 byte|0 y 255 (sin signo)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) (un solo carácter)|<xref:System.Char>|2 bytes|0 a 65535 (sin signo)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 bytes|0:00:00 (medianoche) el 1 de enero, 0001 a 11:59:59 P.M. del 31 de diciembre de 9999|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 bytes|0 a +/-79.228.162.514.264.337.593.543.950.335 (+/-7.9 … E + 28) <sup>†</sup> sin ningún separador decimal; de 0 a +/-7,9228162514264337593543950335 con 28 posiciones a la derecha del separador decimal;<br /><br /> número más pequeño distinto de cero es +/-0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) (punto flotante de precisión doble)|<xref:System.Double>|8 bytes|-1, 79769313486231570E + 308 a - 4, 94065645841246544E-324 <sup>†</sup> para los valores negativos;<br /><br /> 4, 94065645841246544E-324 a 1, 79769313486231570E + 308 <sup>†</sup> para los valores positivos|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 bytes|-2.147.483.648 y 2.147.483.647 (con signo)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) (entero largo)|<xref:System.Int64>|8 bytes|-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807 (9.2 … E + 18 <sup>†</sup>) (con signo)|  
|[Objeto](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> (clase)|4 bytes en plataformas de 32 bits<br /><br /> 8 bytes en plataformas de 64 bits|Cualquier tipo puede almacenarse en una variable de tipo `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 byte|-128 a 127 (con signo)|  
|[Short](../../../visual-basic/language-reference/data-types/short-data-type.md) (entero corto)|<xref:System.Int16>|2 bytes|-32.768 a 32.767 (con signo)|  
|[Solo](../../../visual-basic/language-reference/data-types/single-data-type.md) (punto flotante de precisión simple)|<xref:System.Single>|4 bytes|-3, 4028235E + 38 a - 1, 401298E-45 <sup>†</sup> para los valores negativos;<br /><br /> 1, 401298E-45 a 3, 4028235E + 38 <sup>†</sup> para los valores positivos|  
|[Cadena](../../../visual-basic/language-reference/data-types/string-data-type.md) (de longitud variable)|<xref:System.String> (clase)|Depende de la implementación de plataforma|0 a aproximadamente 2 mil millones de caracteres Unicode|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 bytes|0 y 4.294.967.295 (sin signo)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 bytes|de 0 a 18,446,744,073,709,551,615 (1,8 … E + 19 <sup>†</sup>) (sin signo)|  
|[Definido por el usuario](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) (estructura)|(se hereda de <xref:System.ValueType>)|Depende de la implementación de plataforma|Cada miembro de la estructura tiene un intervalo determinado por su tipo de datos e independiente de los intervalos de los otros miembros|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 bytes|entre 0 y 65.535 (sin signo)|  
  
 <sup>†</sup> En *notación científica*, "E" hace referencia a una potencia de 10. Por lo que 3.56E + 2 significa 3.56 x 10<sup>2</sup> o 356 y 3.56E-2 significa 3.56 / 10<sup>2</sup> o 0.0356.  
  
> [!NOTE]
>  Para las cadenas que contiene texto, use la <xref:Microsoft.VisualBasic.Strings.StrConv%2A> función para convertir de un formato de texto a otro.  
  
 Además de especificar un tipo de datos en una instrucción de declaración, puede forzar al tipo de datos de algunos elementos de programación mediante el uso de un carácter de tipo. Consulte [escribir caracteres](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Consumo de memoria  
 Cuando se declara un tipo de datos básico, no es seguro suponer que su consumo de memoria es el mismo que su asignación de almacenamiento nominal. Esto es debido a las siguientes consideraciones:  
  
-   **Asignación de almacenamiento.** Common language runtime puede asignar el almacenamiento en función de las características actuales de la plataforma en que se ejecuta la aplicación. Si la memoria está casi lleno, se pueden empaquetar los elementos declarados como estrechamente juntos como sea posible. En otros casos puede alinear sus direcciones de memoria a los límites naturales del hardware para optimizar el rendimiento.  
  
-   **Ancho de la plataforma.** Asignación de almacenamiento en una plataforma de 64 bits es diferente a la asignación en una plataforma de 32 bits.  
  
### <a name="composite-data-types"></a>Tipos de datos compuestos  
 Las mismas consideraciones se aplican a cada miembro de un tipo de datos compuestos, como una estructura o una matriz. No puede depender sumar simplemente las asignaciones de almacenamiento nominal de los miembros del tipo. Además, existen otras consideraciones, como las siguientes:  
  
-   **Carga de trabajo.** Algunos tipos compuestos tienen requisitos adicionales de memoria. Por ejemplo, una matriz utiliza memoria adicional para la propia matriz y también para cada dimensión. En una plataforma de 32 bits, esta sobrecarga actualmente es de 12 bytes y 8 bytes para cada dimensión. En una plataforma de 64 bits se duplica este requisito.  
  
-   **Diseño de almacenamiento.** No puede suponerse que el orden de almacenamiento en memoria es el mismo que el orden de declaración. Incluso no puede realizar suposiciones sobre la alineación de bytes, como un límite de 2 o 4 bytes. Si está definiendo una clase o estructura y necesite controlar el diseño de almacenamiento de sus miembros, puede aplicar el <xref:System.Runtime.InteropServices.StructLayoutAttribute> atributo a la clase o estructura.  
  
### <a name="object-overhead"></a>Sobrecarga de objetos  
 Un `Object` que hace referencia a ningún dato básico o compuesto tipo usa 4 bytes además de los datos contenidos en el tipo de datos.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Strings.StrConv%2A>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
