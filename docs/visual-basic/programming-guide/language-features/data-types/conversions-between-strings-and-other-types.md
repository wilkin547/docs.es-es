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
ms.openlocfilehash: 06dabbb5d5dfbfb545f01afb157fd532ca0551df
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197338"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Conversiones entre cadenas y otros tipos (Visual Basic)
Puede convertir un valor numérico, de `Boolean` o de fecha y hora en un `String`. También puede convertir en la dirección inversa, de un valor de cadena a numérico, `Boolean` o `Date`, siempre que el contenido de la cadena pueda interpretarse como un valor válido del tipo de datos de destino. Si no es así, se produce un error en tiempo de ejecución.  
  
 Las conversiones de todas estas asignaciones, en cualquier dirección, son conversiones de restricción. Debe utilizar las palabras clave de conversión de tipos (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, 0, 1, 2 , 3 y 4). Las funciones <xref:Microsoft.VisualBasic.Strings.Format%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A> proporcionan un control adicional sobre las conversiones entre cadenas y números.  
  
 Si ha definido una clase o estructura, puede definir operadores de conversión de tipos entre `String` y el tipo de la clase o estructura. Para obtener más información, consulta [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Conversión de números en cadenas  
 Puede usar la función `Format` para convertir un número en una cadena con formato, que puede incluir no solo los dígitos adecuados, sino también símbolos de formato como un signo de moneda (por ejemplo, `$`), separadores de miles o *símbolos de agrupación de dígitos* (como @no __t_3) y un separador decimal (como `.`). `Format` usa automáticamente los símbolos apropiados de acuerdo con la configuración **regional** especificada en el **Panel de control**de Windows.  
  
 Tenga en cuenta que el operador de concatenación (`&`) puede convertir un número en una cadena implícitamente, como se muestra en el ejemplo siguiente.  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Conversión de cadenas en números  
 Puede utilizar la función `Val` para convertir explícitamente los dígitos de una cadena en un número. `Val` lee la cadena hasta que encuentra un carácter que no sea un dígito, un espacio, una tabulación, un salto de línea o un punto. Las secuencias "& O" y "& H" modifican la base del sistema numérico y finalizan el análisis. Hasta que deja de leer, `Val` convierte todos los caracteres adecuados en un valor numérico. Por ejemplo, la siguiente instrucción devuelve el valor `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Cuando Visual Basic convierte una cadena en un valor numérico, usa la configuración de **Opciones regionales** especificada en el panel de **control** de Windows para interpretar el separador de miles, el separador decimal y el símbolo de moneda. Esto significa que una conversión podría realizarse con una configuración, pero no con otra. Por ejemplo, `"$14.20"` es aceptable en la configuración regional de inglés (Estados Unidos), pero no en la configuración regional en francés.  
  
## <a name="see-also"></a>Vea también

- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Cómo: convertir un objeto en otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Conversiones de matriz](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Desarrollo de aplicaciones localizadas y globalizadas](/visualstudio/ide/globalizing-and-localizing-applications)
