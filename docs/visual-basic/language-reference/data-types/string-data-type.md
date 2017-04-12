---
title: La cadena de tipo de datos (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.String
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings, string data type
- literals, string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals
- data types [Visual Basic], assigning
- String literals
- identifier type characters, $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
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
ms.openlocfilehash: 9221a89a1fb46609b4b8550968e3a2bbe874772c
ms.lasthandoff: 03/13/2017

---
# <a name="string-data-type-visual-basic"></a>String (Tipo de datos, Visual Basic)
Contiene secuencias de puntos de código de (2 bytes) sin signo de 16 bits de ese intervalo con un valor comprendido entre 0 y 65535. Cada *punto de código*, o código de carácter representa un único carácter Unicode. Una cadena puede contener de 0 a dos mil millones (2 ^ 31) caracteres Unicode.  
  
## <a name="remarks"></a>Comentarios  
 Utilice la `String` tipo de datos para contener varios caracteres sin la sobrecarga de administración de la matriz de `Char()`, una matriz de `Char` elementos.  
  
 El valor predeterminado de `String` es `Nothing` (una referencia nula). Tenga en cuenta que no es el mismo que la cadena vacía (valor `""`).  
  
## <a name="unicode-characters"></a>Caracteres Unicode  
 Los primeros puntos de 128 código (0 – 127) de Unicode corresponden a las letras y símbolos de un teclado estándar de Estados Unidos. Estos primeros 128 puntos de código son los mismos que los define el juego de caracteres ASCII. El segundo 128 puntos de código (128 – 255) representan caracteres especiales, como letras de alfabetos latinos, acentos, símbolos de moneda y fracciones. Unicode utiliza los puntos de código restantes (256-65535) para una amplia variedad de símbolos. Esto incluye los caracteres de texto en todo el mundo, signos diacríticos y símbolos matemáticos y técnicos.  
  
 Puede utilizar métodos como <xref:System.Char.IsDigit%2A>y <xref:System.Char.IsPunctuation%2A>en un carácter individual de un `String` variable para determinar su clasificación Unicode.</xref:System.Char.IsPunctuation%2A> </xref:System.Char.IsDigit%2A>  
  
## <a name="format-requirements"></a>Requisitos de formato  
 Debe incluir un `String` literal entre comillas (`" "`). Si se debe incluir una comilla como uno de los caracteres de la cadena, utilice dos comillas contiguas (`""`). Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Tenga en cuenta que las comillas contiguas que representan una comilla en la cadena son independientes de las comillas que comienzan y terminan el `String` literal.  
  
## <a name="string-manipulations"></a>Manipulaciones de cadenas  
 Una vez que se asigna una cadena a un `String` variable, esa cadena es *inmutable*, lo que significa que no puede cambiar su longitud ni su contenido. Cuando se modifica una cadena de cualquier manera, Visual Basic crea una nueva cadena y abandona la anterior. El `String` variable apunta a la nueva cadena.  
  
 Puede manipular el contenido de una `String` variable mediante una variedad de funciones de cadena. En el ejemplo siguiente se muestra la <xref:Microsoft.VisualBasic.Strings.Left%2A>función</xref:Microsoft.VisualBasic.Strings.Left%2A>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Una cadena creada por otro componente puede completarse con espacios iniciales o finales. Si recibe este tipo de cadena, puede utilizar el <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, y <xref:Microsoft.VisualBasic.Strings.RTrim%2A>funciones para quitar estos espacios.</xref:Microsoft.VisualBasic.Strings.RTrim%2A> </xref:Microsoft.VisualBasic.Strings.LTrim%2A> </xref:Microsoft.VisualBasic.Strings.Trim%2A>  
  
 Para obtener más información acerca de las manipulaciones de cadenas, vea [cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
-   **Números negativos.** Recuerde que los caracteres contenidos en `String` están firmados y no pueden representar valores negativos. En cualquier caso, no debe usar `String` para contener valores numéricos.  
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los caracteres de una cadena tienen un ancho de datos distinto (8 bits) en otros entornos. Si se pasa un argumento de cadena de caracteres de 8 bits a esos componentes, declárelo como `Byte()`, una matriz de `Byte` elementos, en lugar de `String` en el nuevo código de Visual Basic.  
  
-   **Caracteres de tipo.** Al anexar el carácter de tipo identificador `$` a cualquier identificador, se convierte a la `String` el tipo de datos. `String`no tiene ningún carácter de tipo literal. Sin embargo, el compilador trata los literales encerrados entre comillas (`" "`) como `String`.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la <xref:System.String?displayProperty=fullName>clase.</xref:System.String?displayProperty=fullName>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.String?displayProperty=fullName></xref:System.String?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Char (tipo de datos)](../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Funciones de conversión de tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de la conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Cómo: llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

