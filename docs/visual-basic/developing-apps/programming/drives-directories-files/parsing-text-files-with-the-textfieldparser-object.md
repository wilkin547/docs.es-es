---
title: Analizar archivos de texto con el objeto TextFieldParser (Visual Basic)
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
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files, parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ad7407ca1928f9b4a2405bc5831777fbf965b61f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a>Analizar archivos de texto con el objeto TextFieldParser (Visual Basic)
El objeto `TextFieldParser` permite analizar y procesar archivos muy grandes estructurados como columnas de texto con ancho delimitado, como archivos de registro o información de la base de datos heredada. Analizar un archivo de texto con `TextFieldParser` es similar a recorrer en iteración un archivo de texto, mientras que el método parse para extraer campos de texto es similar a los métodos de manipulación de cadenas usados para acortar cadenas delimitadas.  
  
## <a name="parsing-different-types-of-text-files"></a>Analizar diferentes tipos de archivos de texto  
 Los archivos de texto pueden tener campos con diversas anchuras, delimitados por un carácter, como una coma o un espacio de tabulación. Defina `TextFieldType` y el delimitador, como en el ejemplo siguiente, que usa el método `SetDelimiters` para definir un archivo de texto delimitado por tabulaciones:  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]  
  
 Otros archivos de texto pueden tener anchos de campos fijos. En tales casos, debe definir `TextFieldType` como `FixedWidth` y definir los anchos de cada campo, como en el ejemplo siguiente. En este ejemplo se usa el método `SetFieldWidths` para definir las columnas de texto: la primera columna es de 5 caracteres de ancho, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]  
  
 Una vez definido el formato, puede recorrer en bucle el archivo usando el método `ReadFields` para procesar cada línea sucesivamente.  
  
 Si un campo no coincide con el formato especificado, se genera una excepción <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>. Cuando se producen dichas excepciones, en las propiedades `ErrorLine` y `ErrorLineNumber` se indica el texto que da lugar a la excepción y el número de línea de dicho texto.  
  
## <a name="parsing-files-with-multiple-formats"></a>Analizar archivos con varios formatos  
 El método `PeekChars` del objeto `TextFieldParser` se puede usar para comprobar cada campo antes de leerlo, lo que le permite definir varios formatos para los campos y actuar en consecuencia. Para obtener más información, consulte [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>

