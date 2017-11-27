---
title: Char (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16ff547fccbf4481d31ca79537962cc7090fc9b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="char-data-type-visual-basic"></a>Char (Tipo de datos, Visual Basic)
Contiene puntos de código de (2 bytes) de 16 bits sin signo comprendidos entre valor comprendido entre 0 y 65535. Cada *punto de código*, o el código de carácter, representa un único carácter Unicode.  
  
## <a name="remarks"></a>Comentarios  
 Use la `Char` cuando deba contener solo un único tipo de datos de caracteres y no es necesario que la sobrecarga de `String`. En algunos casos puede usar `Char()`, una matriz de `Char` elementos, para contener varios caracteres.  
  
 El valor predeterminado de `Char` es el carácter con un punto de código de 0.  
  
## <a name="unicode-characters"></a>Caracteres Unicode  
 Los primeros puntos de 128 código (0 – 127) de Unicode corresponden a las letras y símbolos de un teclado estándar de Estados Unidos. Estos primeros puntos de 128 código son las mismas que las define el juego de caracteres ASCII. Los siguientes puntos de 128 código (128 – 255) representan caracteres especiales, como letras de alfabetos latinos, acentos, símbolos de moneda y fracciones. Unicode utiliza los puntos de código restantes (256-65535) para una amplia variedad de símbolos, incluidos los caracteres de texto en todo el mundo, signos diacríticos y símbolos matemáticos y técnicos.  
  
 Puede usar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en un `Char` variable para determinar su clasificación Unicode.  
  
## <a name="type-conversions"></a>Conversiones de tipos  
 Visual Basic no convertir directamente entre `Char` y los tipos numéricos. Puede usar el <xref:Microsoft.VisualBasic.Strings.Asc%2A> o <xref:Microsoft.VisualBasic.Strings.AscW%2A> función para convertir un `Char` valor a un `Integer` que representa su punto de código. Puede usar el <xref:Microsoft.VisualBasic.Strings.Chr%2A> o <xref:Microsoft.VisualBasic.Strings.ChrW%2A> función para convertir un `Integer` valor a un `Char` que tenga ese punto de código.  
  
 Si la comprobación de tipos cambia ([Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)) está activado, debe agregar el carácter de tipo literal a un solo carácter literal de cadena para identificarlo como el `Char` tipo de datos. Esto se ilustra en el siguiente ejemplo:  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Números negativos.** `Char`es un tipo sin signo y no puede representar un valor negativo. En cualquier caso, no debe usar `Char` para contener valores numéricos.  
  
-   **Consideraciones de interoperabilidad.** Si se interactúa con componentes que no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los tipos de caracteres tienen un ancho de datos distinto (8 bits) en otros entornos. Si se pasa un argumento de 8 bits a esos componentes, declárelo como `Byte` en lugar de `Char` en el código de Visual Basic.  
  
-   **De ampliación.** El `Char` tipo de datos se amplía a `String`. Esto significa que se puede convertir `Char` a `String` y no se producirán un <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
-   **Caracteres de tipo.** Si se agrega el carácter de tipo literal `C` en una cadena de carácter único literal fuerza que el `Char` tipo de datos. `Char`no tiene ningún carácter de tipo identificador.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Char?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [String (tipo de datos)](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
