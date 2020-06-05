---
title: Conversiones entre cadenas y otros tipos
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: ae8f7c2159191536013fafd8bfd10fb9a93fb785
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394226"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Conversiones entre cadenas y otros tipos (Visual Basic)
Puede convertir un valor numérico, `Boolean` o de fecha y hora en un `String` . También puede convertir en la dirección inversa, de un valor de cadena a numérico, `Boolean` o, `Date` siempre que el contenido de la cadena pueda interpretarse como un valor válido del tipo de datos de destino. Si no es así, se produce un error en tiempo de ejecución.  
  
 Las conversiones de todas estas asignaciones, en cualquier dirección, son conversiones de restricción. Debe utilizar las palabras clave de conversión de tipos ( `CBool` , `CByte` , `CDate` , `CDbl` , `CDec` , `CInt` , `CLng` , `CSByte` , `CShort` , `CSng` , `CStr` , `CUInt` ,, `CULng` `CUShort` y `CType` ). Las <xref:Microsoft.VisualBasic.Strings.Format%2A> <xref:Microsoft.VisualBasic.Conversion.Val%2A> funciones y proporcionan un control adicional sobre las conversiones entre cadenas y números.  
  
 Si ha definido una clase o estructura, puede definir operadores de conversión de tipos entre `String` y el tipo de la clase o estructura. Para obtener más información, consulta [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Conversión de números en cadenas  
 Puede usar la `Format` función para convertir un número en una cadena con formato, que puede incluir no solo los dígitos adecuados, sino también símbolos de formato como un signo de moneda (como `$` ), separadores de miles o *símbolos de agrupación de dígitos* (como `,` ) y un separador decimal (como `.` ). `Format`usa automáticamente los símbolos apropiados según la configuración **regional** especificada en el **Panel de control**de Windows.  
  
 Tenga en cuenta que el operador de concatenación ( `&` ) puede convertir un número en una cadena implícitamente, como se muestra en el ejemplo siguiente.  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Conversión de cadenas en números  
 Puede usar la `Val` función para convertir explícitamente los dígitos de una cadena en un número. `Val`Lee la cadena hasta que encuentra un carácter que no sea un dígito, un espacio, una tabulación, un salto de línea o un punto. Las secuencias "&O" y "&H" modifican la base del sistema numérico y finalizan el análisis. Hasta que deje de leerse, `Val` convierte todos los caracteres adecuados en un valor numérico. Por ejemplo, la siguiente instrucción devuelve el valor `141.825` .  
  
 `Val("   14   1.825 miles")`  
  
 Cuando Visual Basic convierte una cadena en un valor numérico, usa la configuración de **Opciones regionales** especificada en el panel de **control** de Windows para interpretar el separador de miles, el separador decimal y el símbolo de moneda. Esto significa que una conversión podría realizarse con una configuración, pero no con otra. Por ejemplo, `"$14.20"` es aceptable en la configuración regional en inglés (Estados Unidos), pero no en la configuración regional en francés.  
  
## <a name="see-also"></a>Consulte también

- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](implicit-and-explicit-conversions.md)
- [Cómo: Convertir un objeto en otro tipo en Visual Basic](how-to-convert-an-object-to-another-type.md)
- [Conversiones de matriz](array-conversions.md)
- [Tipos de datos](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
- [Desarrollo de aplicaciones localizadas y globalizadas](/visualstudio/ide/globalizing-and-localizing-applications)
