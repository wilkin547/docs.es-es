---
title: Conversiones entre cadenas y otros tipos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 1e42fca7800a76cab10fd60058e34d31ae8b8830
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907327"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Conversiones entre cadenas y otros tipos (Visual Basic)
Puede convertir un valor numérico, `Boolean`, o el valor de fecha y hora un `String`. También puede convertir en dirección inversa, de un valor de cadena a numéricos, `Boolean`, o `Date` , siempre que se puede interpretar el contenido de la cadena como un valor válido del tipo de datos de destino. Si no es posible, se produce un error en tiempo de ejecución.  
  
 Las conversiones de todas estas asignaciones, en cualquier dirección, son conversiones de restricción. Debe usar las palabras clave de conversión de tipos (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, y `CType`). El <xref:Microsoft.VisualBasic.Strings.Format%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A> funciones proporcionan mayor control sobre las conversiones entre cadenas y números.  
  
 Si ha definido una clase o estructura, puede definir operadores de conversión de tipos entre `String` y el tipo de la clase o estructura. Para obtener más información, vea [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Conversión de números en cadenas  
 Puede usar el `Format` funcionando para convertir un número en una cadena con formato, que puede incluir no sólo los dígitos adecuados, pero también aplicar formato a los símbolos como un signo de moneda (como `$`), miles separadores o *agrupación de dígitos símbolos* (como `,`) y un separador decimal (como `.`). `Format` usa automáticamente los símbolos adecuados según la **opciones regionales** configuración especificada en el Windows **Panel de Control**.  
  
 Tenga en cuenta que la concatenación (`&`) operador puede convertir un número en una cadena de forma implícita, como se muestra en el ejemplo siguiente.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Conversión de cadenas en números  
 Puede usar el `Val` función para convertir explícitamente los dígitos de una cadena en un número. `Val` lee la cadena hasta que encuentra un carácter que no sea un dígito, espacio, ficha, avance de línea o período. Las secuencias "& O" y "& H" alteran la base del sistema numérico y finalizan la exploración. Hasta que se detiene la lectura, `Val` convierte todos los caracteres apropiados en un valor numérico. Por ejemplo, la siguiente instrucción devuelve el valor `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Cuando Visual Basic convierte una cadena en un valor numérico, utiliza el **opciones regionales** configuración especificada en el Windows **Panel de Control** para interpretar los miles separador, separador de decimales y símbolo de moneda. Esto significa que una conversión puede realizarse correctamente en una configuración, pero no en otro. Por ejemplo, `"$14.20"` es aceptable en la configuración regional Inglés (Estados Unidos), pero no en cualquier configuración regional en francés.  
  
## <a name="see-also"></a>Vea también

- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Cómo: Convertir un objeto a otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Conversiones de matriz](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Introducción a aplicaciones internacionales basadas en .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
