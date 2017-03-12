---
title: "Analizar archivos de texto con el objeto TextFieldParser (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "archivos, analizar"
  - "E/S [Visual Basic], analizar archivos"
  - "TextFieldParser (objeto), utilizar"
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Analizar archivos de texto con el objeto TextFieldParser (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El objeto `TextFieldParser` permite analizar y procesar archivos muy grandes estructurados como columnas de texto de ancho delimitado, como archivos de registro o información de base de datos heredada.  Analizar un archivo de texto con `TextFieldParser` es similar a recorrer en iteración un archivo de texto, mientras que el método de análisis para extraer archivos de texto es similar a los métodos de manipulación de cadenas que se utilizan para convertir cadenas delimitadas en tokens.  
  
## Analizar diferentes tipos de archivos de texto  
 Los archivos de texto pueden tener campos de varios anchos, delimitados por un carácter como una coma o un espacio de tabulación.  Defina la propiedad `TextFieldType` y el delimitador, como en el ejemplo siguiente, que utiliza el método `SetDelimiters` para definir un archivo de texto delimitado por tabulaciones:  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/parsing-text-files-with-_1.vb)]  
  
 Otros archivos de texto pueden tener anchos de campo fijos.  En tal caso, es necesario definir `TextFieldType` como `FixedWidth` y definir los anchos de cada campo, como en el ejemplo siguiente.  En este ejemplo se utiliza el método `SetFieldWidths`, para definir las columnas de texto: la primera columna tiene 5 caracteres de ancho, la segunda tiene 10, la tercera 11 y la cuarta es de ancho variable.  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/parsing-text-files-with-_2.vb)]  
  
 Cuando se define el formato, se puede recorrer el archivo utilizando el método `ReadFields` para procesar cada línea.  
  
 Si un campo no coincide con el formato especificado, se produce una excepción <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>.  Cuando se produce este tipo de excepciones, las propiedades `ErrorLine` y `ErrorLineNumber` contienen el texto que produce la excepción y el número de línea de ese texto.  
  
## Analizar archivos con varios formatos  
 El método `PeekChars` del objeto `TextFieldParser` se puede utilizar para comprobar cada archivo antes de leerlo, lo que permite definir varios formatos para los campos y actuar en consecuencia.  Para obtener más información, vea [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## Vea también  
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
 [Solución de problemas de excepciones: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)