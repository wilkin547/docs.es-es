---
title: "Resumen de tipos de datos (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean (tipo de datos), tipos admitidos en Visual Basic"
  - "Byte (tipo de datos), tipos de datos de Visual Basic"
  - "Char (tipo de datos), tipos de datos de Visual Basic"
  - "tipos de datos [Visual Basic], requisitos de memoria"
  - "tipos de datos [Visual Basic], orden de almacenamiento"
  - "tipos de datos [Visual Basic], asignación de almacenamiento"
  - "tipos de datos [Visual Basic], resumen"
  - "tipos de datos [Visual Basic], Visual Basic"
  - "Date (tipo de datos), Visual Basic"
  - "fechas [Visual Basic], tipos de datos"
  - "Double (tipo de datos), tipos de datos de Visual Basic"
  - "números de precisión doble"
  - "Integer (tipo de datos), tipos de datos de Visual Basic"
  - "tipos de datos intrínsecos"
  - "Long (tipo de datos), tipos admitidos en Visual Basic"
  - "consumo de memoria"
  - "consumo de memoria, tipos de datos"
  - "requisitos de memoria, tipos de datos"
  - "notación, científica"
  - "Object (tipo de datos), tipos admitidos en Visual Basic"
  - "notación científica"
  - "Single (tipo de datos), tipos admitidos en Visual Basic"
  - "números de precisión sencilla"
  - "orden de almacenamiento, controlar en Visual Basic"
  - "orden de almacenamiento, tipos de datos"
  - "almacenamiento, asignación"
  - "almacenamiento, orden de almacenamiento"
  - "almacenamiento, espacio"
  - "String (tipo de datos), tipos de datos de Visual Basic"
  - "cadenas [Visual Basic], tipos de datos"
  - "StructLayoutAttribute (clase), almacenamiento de tipos de datos de Visual Basic"
  - "tipos de datos definidos por el usuario, Visual Basic"
  - "Variant (tipos de datos), tipos admitidos en Visual Basic"
  - "Visual Basic, tipos de datos"
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Resumen de tipos de datos (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En la tabla siguiente se muestran los tipos de datos de Visual Basic .NET, los tipos compatibles con Common Language Runtime, su asignación de almacenamiento nominal y sus intervalos de valores.  
  
|Tipo de Visual Basic|Estructura de tipo Common Language Runtime|Asignación de almacenamiento nominal|Intervalo de valores|  
|--------------------------|------------------------------------------------|------------------------------------------|--------------------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|En función de la plataforma de implementación|`True` o `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 byte|0 a 255 \(sin signo\)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) \(carácter individual\)|<xref:System.Char>|2 bytes|0 a 65535 \(sin signo\)|  
|[Fecha](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 bytes|0:00:00 \(medianoche\) del 1 de enero de 0001 a 11:59:59 p.m. del 31 de diciembre de 9999.|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 bytes|0 a \+\/\-79.228.162.514.264.337.593.543.950.335 \(\+\/\-7,9... E\+28\) <sup>†</sup> sin separador decimal; 0 a \+\/\-7,9228162514264337593543950335 con 28 posiciones a la derecha del decimal;<br /><br /> el número distinto de cero más pequeño es \+\/\-0,0000000000000000000000000001 \(\+\/\-1E\-28\) <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) \(punto flotante de precisión doble\)|<xref:System.Double>|8 bytes|\-1,79769313486231570E\+308 a \-4,94065645841246544E\-324 <sup>†</sup> para los valores negativos;<br /><br /> 4,94065645841246544E\-324 a 1,79769313486231570E\+308 <sup>†</sup> para los valores positivos|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 bytes|\-2.147.483.648 a 2.147.483.647 \(con signo\)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) \(entero largo\)|<xref:System.Int64>|8 bytes|\-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 \(9,2...E\+18 <sup>†</sup>\) \(con signo\)|  
|[Objeto.](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> \(clase\)|4 bytes en plataforma de 32 bits<br /><br /> 8 bytes en plataforma de 64 bits|Cualquier tipo puede almacenarse en una variable de tipo `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 byte|\-128 a 127 \(con signo\)|  
|[Short](../../../visual-basic/language-reference/data-types/short-data-type.md) \(entero corto\)|<xref:System.Int16>|2 bytes|\-32.768 a 32.767 \(con signo\)|  
|[Single](../../../visual-basic/language-reference/data-types/single-data-type.md) \(punto flotante de precisión sencilla\)|<xref:System.Single>|4 bytes|\-3,4028235E\+38 a \-1,401298E\-45 <sup>†</sup> para los valores negativos;<br /><br /> 1,401298E\-45 a 3,4028235E\+38 <sup>†</sup> para los valores positivos|  
|[String](../../../visual-basic/language-reference/data-types/string-data-type.md) \(longitud variable\)|<xref:System.String> \(clase\)|En función de la plataforma de implementación|0 a 2.000 millones de caracteres Unicode aprox.|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 bytes|0 a 4.294.967.295 \(sin signo\)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 bytes|0 a 18.446.744.073.709.551.615 \(1,8...E\+19 <sup>†</sup>\) \(sin signo\)|  
|[User\-Defined](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) \(estructura\)|\(hereda de <xref:System.ValueType>\)|En función de la plataforma de implementación|Cada miembro de la estructura tiene un intervalo de valores determinado por su tipo de datos y es independiente de los intervalos de valores correspondientes a los demás miembros.|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 bytes|0 a 65.535 \(sin signo\)|  
  
 <sup>†</sup> En *notación científica*, E hace referencia a una potencia de 10.  Por consiguiente, 3,56E\+2 significa 3.56 x 10<sup>2</sup> ó 356 y 3,56E\-2 significa 3.56 \/ 10<sup>2</sup> ó 0,0356.  
  
> [!NOTE]
>  En las cadenas que contienen texto, utilice la función <xref:Microsoft.VisualBasic.Strings.StrConv%2A> para pasar de un formato de texto a otro.  
  
 Además de especificar un tipo de datos en una instrucción de declaración, puede forzar el tipo de datos de algunos elementos de programación mediante el carácter de tipo.  Vea [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## Consumo de memoria  
 Al declarar un tipo de datos básico, no debe suponerse que su consumo de memoria es igual a su asignación de almacenamiento nominal.  Esto se debe a las consideraciones siguientes:  
  
-   **Asignación de almacenamiento.** Common Language Runtime puede asignar el almacenamiento en función de las características actuales de la plataforma en la que se ejecuta la aplicación.  Si la memoria está casi completa, se pueden empaquetar los elementos declarados de la forma más estrecha posible.  En otros casos, se podrían alinear las direcciones de memoria a los límites del hardware naturales para optimizar el rendimiento.  
  
-   **Ancho de plataforma.** La asignación de almacenamiento en una plataforma de 64 bits es diferente a la asignación en una plataforma de 32 bits.  
  
### Tipos de datos compuestos  
 Las mismas consideraciones se aplican a cada miembro de un tipo de datos compuesto, como una estructura o una matriz.  No se pueden sumar simplemente todas las asignaciones de almacenamiento nominales de los miembros de tipo.  Además, existen otras consideraciones, como las siguientes:  
  
-   **Sobrecarga.** Algunos tipos compuestos tienen requisitos adicionales de memoria.  Por ejemplo, una matriz utiliza memoria adicional para la matriz en sí y para cada dimensión.  En una plataforma de 32 bits, esta sobrecarga corresponde a 12 bytes y 8 bytes por cada dimensión.  En una plataforma de 64 bits, los requisitos se duplican.  
  
-   **Diseño de almacenamiento.** No debe suponerse que el orden de almacenamiento en la memoria es igual al orden de declaración.  Ni siquiera pueden hacerse predicciones sobre la alineación de bytes, como un límite de 2 bytes o de 4 bytes.  Si define una clase o estructura y necesita controlar el diseño de almacenamiento de sus miembros, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la clase o estructura.  
  
### Sobrecarga de objetos  
 Una variable `Object` que haga referencia a un tipo de datos básico o compuesto, utiliza 4 bytes además de los datos contenidos en el tipo de datos.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)