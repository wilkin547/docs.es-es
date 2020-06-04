---
title: Resumen de los tipos de datos
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
ms.openlocfilehash: 5eb52ef937a677c0b7498d058b5a39a375351ddc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415626"
---
# <a name="data-type-summary-visual-basic"></a>Resumen de tipos de datos (Visual Basic)

En la tabla siguiente se muestran los tipos de datos de Visual Basic, sus tipos de Common Language Runtime de soporte, su asignación de almacenamiento nominal y sus intervalos de valores.  
  
|Tipo de Visual Basic|Estructura de tipos de Common Language Runtime|Asignación de almacenamiento nominal|Intervalo de valores|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](boolean-data-type.md)|<xref:System.Boolean>|Depende de la implementación de la plataforma|`True` o `False`|  
|[Byte](byte-data-type.md)|<xref:System.Byte>|1 byte|de 0 a 255 (sin signo)|  
|[Char](char-data-type.md) (carácter único)|<xref:System.Char>|2 bytes|de 0 a 65535 (sin signo)|  
|[Date](date-data-type.md)|<xref:System.DateTime>|8 bytes|0:00:00 (medianoche) el 1 de enero de 0001 a las 11:59:59 P.M. del 31 de diciembre de 9999|  
|[Decimal](decimal-data-type.md)|<xref:System.Decimal>|16 bytes|0 a +/-79.228.162.514.264.337.593.543.950.335 (+/-7.9...E + 28) <sup>†</sup> sin separador decimal; de 0 a +/-7,9228162514264337593543950335 con 28 posiciones a la derecha del decimal;<br /><br /> el número más pequeño distinto de cero es +/-0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Double](double-data-type.md) (punto flotante de precisión doble)|<xref:System.Double>|8 bytes|-1.79769313486231570 e + 308 a-4.94065645841246544 E-324 <sup>†</sup> para los valores negativos;<br /><br /> 4.94065645841246544 e-324 a 1.79769313486231570 E + 308 <sup>†</sup> para valores positivos|  
|[Entero](integer-data-type.md)|<xref:System.Int32>|4 bytes|de-2.147.483.648 a 2.147.483.647 (con signo)|  
|[Long](long-data-type.md) (entero largo)|<xref:System.Int64>|8 bytes|de-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 (9.2... E + 18 <sup>†</sup>) (con signo)|  
|[Objeto](object-data-type.md)|<xref:System.Object>las|4 bytes en la plataforma de 32 bits<br /><br /> 8 bytes en la plataforma de 64 bits|Cualquier tipo se puede almacenar en una variable de tipo`Object`|  
|[SByte](sbyte-data-type.md)|<xref:System.SByte>|1 byte|de-128 a 127 (con signo)|  
|[Short](short-data-type.md) (entero corto)|<xref:System.Int16>|2 bytes|de-32.768 a 32.767 (con signo)|  
|[Single](single-data-type.md) (punto flotante de precisión sencilla)|<xref:System.Single>|4 bytes|-3.4028235 e + 38 a-401298e E-45 <sup>†</sup> para los valores negativos;<br /><br /> 401298e e-45 a 3.4028235 E + 38 <sup>†</sup> para los valores positivos|  
|[Cadena](string-data-type.md) (longitud variable)|<xref:System.String>las|Depende de la implementación de la plataforma|de 0 a aproximadamente 2 mil millones caracteres Unicode|  
|[UInteger](uinteger-data-type.md)|<xref:System.UInt32>|4 bytes|de 0 a 4.294.967.295 (sin signo)|  
|[ULong](ulong-data-type.md)|<xref:System.UInt64>|8 bytes|de 0 a 18446744073709551615 (1.8... E + 19 <sup>†</sup>) (sin signo)|  
|[Definido por el usuario](user-defined-data-type.md) (estructura)|(se hereda de <xref:System.ValueType> )|Depende de la implementación de la plataforma|Cada miembro de la estructura tiene un intervalo determinado por su tipo de datos e independiente de los intervalos de los demás miembros.|  
|[UShort](ushort-data-type.md)|<xref:System.UInt16>|2 bytes|de 0 a 65.535 (sin signo)|  
  
 <sup>†</sup> En *notación científica*, "E" hace referencia a una potencia de 10. Por tanto, 3.56 E + 2 significa 3,56 x 10<sup>2</sup> o 356 y 3.56 e-2 significa 3,56/10<sup>2</sup> o 0,0356.  
  
> [!NOTE]
> Para las cadenas que contienen texto, use la <xref:Microsoft.VisualBasic.Strings.StrConv%2A> función para convertir de un formato de texto a otro.  
  
 Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación mediante el uso de un carácter de tipo. Vea [caracteres de tipo](../../programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Consumo de memoria  

 Cuando se declara un tipo de datos elemental, no es seguro suponer que el consumo de memoria es el mismo que su asignación de almacenamiento nominal. Esto se debe a las siguientes consideraciones:  
  
- **Asignación de almacenamiento.** El Common Language Runtime puede asignar almacenamiento basado en las características actuales de la plataforma en la que se ejecuta la aplicación. Si la memoria está casi llena, puede empaquetar los elementos declarados lo más juntos posible. En otros casos, puede alinear sus direcciones de memoria con límites de hardware naturales para optimizar el rendimiento.  
  
- **Ancho de la plataforma.** La asignación de almacenamiento en una plataforma de 64 bits es diferente de la asignación en una plataforma de 32 bits.  
  
### <a name="composite-data-types"></a>Tipos de datos compuestos  

 Las mismas consideraciones se aplican a cada miembro de un tipo de datos compuesto, como una estructura o una matriz. No se puede confiar simplemente en sumar las asignaciones de almacenamiento nominal de los miembros del tipo. Además, hay otras consideraciones, como las siguientes:  
  
- **Administrativos.** Algunos tipos compuestos tienen requisitos de memoria adicionales. Por ejemplo, una matriz utiliza memoria adicional para la propia matriz y también para cada dimensión. En una plataforma de 32 bits, esta sobrecarga es actualmente de 12 bytes más 8 bytes para cada dimensión. En una plataforma de 64 bits, se duplica este requisito.  
  
- **Diseño de almacenamiento.** No se puede suponer de forma segura que el orden de almacenamiento en memoria es el mismo que el orden de declaración. No puede incluso hacer suposiciones sobre la alineación de bytes, como un límite de 2 o 4 bytes. Si está definiendo una clase o estructura y necesita controlar el diseño de almacenamiento de sus miembros, puede aplicar el <xref:System.Runtime.InteropServices.StructLayoutAttribute> atributo a la clase o estructura.  
  
### <a name="object-overhead"></a>Sobrecarga de objetos  

 Una `Object` referencia a cualquier tipo de datos elemental o compuesto usa 4 bytes además de los datos contenidos en el tipo de datos.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Strings.StrConv%2A>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Caracteres de tipo](../../programming-guide/language-features/data-types/type-characters.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
