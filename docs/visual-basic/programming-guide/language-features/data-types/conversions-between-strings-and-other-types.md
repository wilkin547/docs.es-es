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
ms.openlocfilehash: 40a28d664bc6ed3d094ccc7c342d6411fe88fd7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Conversiones entre cadenas y otros tipos (Visual Basic)
Puede convertir un valor numérico, `Boolean`, o fecha y hora valor a un `String`. También puede convertir en la dirección inversa, de un valor de cadena en valor numérico, `Boolean`, o `Date` , siempre que el contenido de la cadena se pueda interpretar como un valor válido del tipo de datos de destino. Si no es posible, se produce un error en tiempo de ejecución.  
  
 Las conversiones de todas estas asignaciones, en ambas direcciones, son conversiones de restricción. Debe usar las palabras clave de conversión de tipos (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, y `CType`). El <xref:Microsoft.VisualBasic.Strings.Format%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A> funciones proporcionan un control adicional sobre las conversiones entre cadenas y números.  
  
 Si ha definido una clase o estructura, puede definir operadores de conversión de tipo entre `String` y el tipo de la clase o estructura. Para obtener más información, consulte [Cómo: definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Conversión de números en cadenas  
 Puede usar el `Format` función para convertir un número en una cadena con formato, que puede incluir no sólo los dígitos adecuados, pero también aplicar formato a los símbolos, como un signo de moneda (como `$`), miles separadores o *agrupación de dígitos símbolos* (como `,`) y un separador decimal (como `.`). `Format` usa automáticamente los símbolos adecuados según la **opciones regionales** configuración especificada en las ventanas de **el Panel de Control**.  
  
 Tenga en cuenta que la concatenación (`&`) operador puede convertir un número en una cadena implícitamente, como se muestra en el ejemplo siguiente.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Conversión de cadenas en números  
 Puede usar el `Val` función para convertir explícitamente los dígitos de una cadena en un número. `Val` lee la cadena hasta que encuentra un carácter que no sea un dígito, espacio, ficha, avance de línea o período. Las secuencias "& O" y "& H" alteran la base del sistema numérico y finalizan el examen. Hasta que finaliza la lectura, `Val` convierte todos los caracteres apropiados en un valor numérico. Por ejemplo, la siguiente instrucción devuelve el valor `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Cuando Visual Basic convierte una cadena en un valor numérico, usa el **opciones regionales** configuración especificada en las ventanas de **el Panel de Control** para interpretar los miles separador, el separador decimal, y símbolo de divisa. Esto significa que una conversión puede realizarse correctamente bajo una configuración, pero no en otra. Por ejemplo, `"$14.20"` es aceptable en la configuración regional Inglés (Estados Unidos), pero no en cualquier configuración regional en francés.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Cómo: convertir un objeto a otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Conversiones de matriz](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Introducción a aplicaciones internacionales basadas en .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
