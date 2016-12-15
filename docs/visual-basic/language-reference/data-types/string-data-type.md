---
title: "String (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.String"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "" (literales de cadena)"
  - "$ (carácter de tipo identificador)"
  - "tipos de datos [Visual Basic], asignar"
  - "cadenas de longitud fija"
  - "cadenas de longitud fija, string (tipo de datos)"
  - "caracteres de tipo identificador, $"
  - "literales, cadena"
  - "String (tipo de datos)"
  - "string (palabra clave) [Visual Basic]"
  - "literales de cadena"
  - "cadenas [Visual Basic], caracteres"
  - "cadenas [Visual Basic], longitud fija"
  - "texto [Visual Basic], String (tipo de datos)"
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# String (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene secuencias de puntos de código de 16 bits \(2 bytes\) sin signo cuyo valor oscila entre 0 y 65535.  Cada *punto de código* o código de carácter, representa un carácter Unicode único.  Una cadena puede contener de 0 a 2.000 millones \(2^31\) de caracteres Unicode, aproximadamente.  
  
## Comentarios  
 Utilice el tipo de datos `String` para contener varios caracteres sin la sobrecarga de administración de matriz de `Char()`, una matriz de elementos `Char`.  
  
 El valor predeterminado de `String` es `Nothing` \(una referencia nula\).  Observe que esto no es lo mismo que la cadena vacía \(valor `""`\).  
  
## Caracteres Unicode  
 Los primeros 128 puntos de código \(0 a 127\) de Unicode corresponden a las letras y símbolos de un teclado estándar de EE.UU.  teclado.  Estos primeros 128 puntos de código son los mismos que los que el juego de caracteres ASCII define.  Los siguientes 128 puntos de código \(128–255\) representan caracteres especiales, como letras de alfabetos latinos, acentos, símbolos de moneda y fracciones.  Unicode usa los puntos de código restantes \(256\-65535\) para una gran variedad de símbolos.  Esto incluye caracteres de texto de todo el mundo, signos diacríticos y símbolos matemáticos y técnicos.  
  
 Puede usar métodos como <xref:System.Char.IsDigit%2A> y <xref:System.Char.IsPunctuation%2A> en un carácter individual de una variable `String` para determinar su clasificación Unicode.  
  
## Requisitos de formato  
 Debe agregar un literal `String` entre comillas \(`" "`\).   Si necesita incluir comillas como uno de los caracteres de la cadena, use dos comillas contiguas \(`""`\).  Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Observe que las comillas contiguas que representan un solo signo de comillas en la cadena son independientes de las comillas que comienzan y terminan el literal `String`.  
  
## Manipulación de cadenas  
 Cuando asigna una cadena a una variable `String`, esa cadena es *inmutable*, lo que significa que no puede cambiar su longitud ni su contenido.  Cuando modifica una cadena de alguna manera, Visual Basic crea una nueva cadena y abandona la anterior.  La variable `String` señala a continuación a la nueva cadena.  
  
 Puede manipular el contenido de una variable `String` mediante varias funciones de cadena.  En el ejemplo siguiente se muestra la función <xref:Microsoft.VisualBasic.Strings.Left%2A>.  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Una cadena creada por otro componente puede completarse con espacios iniciales o finales.  Si recibe este tipo de cadena, puede utilizar las funciones <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A> y <xref:Microsoft.VisualBasic.Strings.RTrim%2A> para quitar estos espacios.  
  
 Para obtener más información sobre la manipulación de cadenas, vea [Cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## Sugerencias de programación  
  
-   **Números negativos.** Tenga presente que los caracteres contenidos en `String` no tienen signo y no pueden representar valores negativos.  En cualquier caso, no debería utilizar `String` para contener valores numéricos.  
  
-   **Consideraciones de interoperabilidad.** Si trabaja con componentes no escritos para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que los caracteres de cadena pueden tener un ancho de datos distinto \(8 bits\) en otros entornos.  Si está pasando un argumento de cadena de caracteres de 8 bits a este tipo de componentes, declárelo como `Byte()`, una matriz de elementos `Byte`, en lugar de `String` en el nuevo código de Visual Basic.  
  
-   **Caracteres de tipo.** Si se agrega el carácter de tipo identificador `$` a cualquier identificador, se convierte su tipo de datos al tipo `String`.  `String` no tiene caracteres de tipo literal.  Sin embargo, el compilador trata los literales incluidos entre comillas \(`" "`\) como `String`.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la clase <xref:System.String?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.String?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Char \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Cómo: Llamar a una función de Windows que adopta tipos sin signo](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)