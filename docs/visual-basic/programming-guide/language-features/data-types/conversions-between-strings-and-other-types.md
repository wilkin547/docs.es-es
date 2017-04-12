---
title: Conversiones entre cadenas y otros tipos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data type conversion, string
- conversions, type
- string conversion
- conversions, data type
- type conversion, string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2d0a5fc7327ecd6339b5021e1b4cb87cc54bd2bc
ms.lasthandoff: 03/13/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Conversiones entre cadenas y otros tipos (Visual Basic)
Puede convertir un tipo numérico, `Boolean`, valor de fecha y hora o un `String`. También puede convertir en dirección inversa: valor de cadena a tipo numérico, `Boolean`, o `Date` , siempre que el contenido de la cadena se pueda interpretar como un valor válido del tipo de datos de destino. Si no es posible, se produce un error en tiempo de ejecución.  
  
 Las conversiones de todas estas asignaciones, en ambas direcciones, son conversiones de restricción. You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`). El <xref:Microsoft.VisualBasic.Strings.Format%2A>y <xref:Microsoft.VisualBasic.Conversion.Val%2A>funciones proporcionan un control adicional sobre las conversiones entre cadenas y números.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A>  
  
 Si ha definido una clase o estructura, puede definir operadores de conversión de tipos entre `String` y el tipo de la clase o estructura. Para obtener más información, consulte [Cómo: definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Conversión de números en cadenas  
 Puede usar el `Format` función para convertir un número en una cadena con formato, que puede incluir no sólo los dígitos adecuados, pero también aplicar formato a símbolos como un signo de moneda (como `$`), miles separadores o *símbolos de agrupación de dígitos* (como `,`) y un separador decimal (como `.`). `Format`utiliza automáticamente los símbolos adecuados según la **opciones regionales** configuración especificada en las ventanas de **Panel de Control**.  
  
 Tenga en cuenta que la concatenación (`&`) (operador) puede convertir un número en una cadena de forma implícita, como se muestra en el ejemplo siguiente.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Conversión de cadenas en números  
 Puede usar el `Val` función para convertir explícitamente los dígitos de una cadena en un número. `Val`lee la cadena hasta que encuentra un carácter que no sea un dígito, espacio, ficha, avance de línea o un período. Las secuencias "aspecto O" y "aspecto H" alteran la base del sistema numérico y finalizan la exploración. Hasta que finaliza la lectura, `Val` convierte todos los caracteres apropiados en un valor numérico. Por ejemplo, la siguiente instrucción devuelve el valor `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Cuando [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convierte una cadena en un valor numérico, usa el **opciones regionales** configuración especificada en las ventanas de **Panel de Control** para interpretar los miles separador, el separador decimal y el símbolo de moneda. Esto significa que una conversión puede realizarse correctamente bajo una configuración, pero no en otro. Por ejemplo, `"$14.20"` es aceptable en la configuración regional Inglés (Estados Unidos), pero no en cualquier configuración regional en francés.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversiones de restricción y ampliación](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Cómo: convertir un objeto a otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Introducción a aplicaciones internacionales basadas en .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
