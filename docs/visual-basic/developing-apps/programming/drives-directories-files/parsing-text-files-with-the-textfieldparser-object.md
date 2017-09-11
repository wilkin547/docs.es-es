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
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="fdf44-102">Analizar archivos de texto con el objeto TextFieldParser (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdf44-102">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>
<span data-ttu-id="fdf44-103">El objeto `TextFieldParser` permite analizar y procesar archivos muy grandes estructurados como columnas de texto con ancho delimitado, como archivos de registro o información de la base de datos heredada.</span><span class="sxs-lookup"><span data-stu-id="fdf44-103">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="fdf44-104">Analizar un archivo de texto con `TextFieldParser` es similar a recorrer en iteración un archivo de texto, mientras que el método parse para extraer campos de texto es similar a los métodos de manipulación de cadenas usados para acortar cadenas delimitadas.</span><span class="sxs-lookup"><span data-stu-id="fdf44-104">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="fdf44-105">Analizar diferentes tipos de archivos de texto</span><span class="sxs-lookup"><span data-stu-id="fdf44-105">Parsing different types of text files</span></span>  
 <span data-ttu-id="fdf44-106">Los archivos de texto pueden tener campos con diversas anchuras, delimitados por un carácter, como una coma o un espacio de tabulación.</span><span class="sxs-lookup"><span data-stu-id="fdf44-106">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="fdf44-107">Defina `TextFieldType` y el delimitador, como en el ejemplo siguiente, que usa el método `SetDelimiters` para definir un archivo de texto delimitado por tabulaciones:</span><span class="sxs-lookup"><span data-stu-id="fdf44-107">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 <span data-ttu-id="fdf44-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fdf44-108">[!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]</span></span>  
  
 <span data-ttu-id="fdf44-109">Otros archivos de texto pueden tener anchos de campos fijos.</span><span class="sxs-lookup"><span data-stu-id="fdf44-109">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="fdf44-110">En tales casos, debe definir `TextFieldType` como `FixedWidth` y definir los anchos de cada campo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="fdf44-110">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="fdf44-111">En este ejemplo se usa el método `SetFieldWidths` para definir las columnas de texto: la primera columna es de 5 caracteres de ancho, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.</span><span class="sxs-lookup"><span data-stu-id="fdf44-111">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 <span data-ttu-id="fdf44-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="fdf44-112">[!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]</span></span>  
  
 <span data-ttu-id="fdf44-113">Una vez definido el formato, puede recorrer en bucle el archivo usando el método `ReadFields` para procesar cada línea sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="fdf44-113">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="fdf44-114">Si un campo no coincide con el formato especificado, se genera una excepción <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>.</span><span class="sxs-lookup"><span data-stu-id="fdf44-114">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="fdf44-115">Cuando se producen dichas excepciones, en las propiedades `ErrorLine` y `ErrorLineNumber` se indica el texto que da lugar a la excepción y el número de línea de dicho texto.</span><span class="sxs-lookup"><span data-stu-id="fdf44-115">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="fdf44-116">Analizar archivos con varios formatos</span><span class="sxs-lookup"><span data-stu-id="fdf44-116">Parsing files with multiple formats</span></span>  
 <span data-ttu-id="fdf44-117">El método `PeekChars` del objeto `TextFieldParser` se puede usar para comprobar cada campo antes de leerlo, lo que le permite definir varios formatos para los campos y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="fdf44-117">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="fdf44-118">Para obtener más información, consulte [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span><span class="sxs-lookup"><span data-stu-id="fdf44-118">For more information, see [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf44-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdf44-119">See also</span></span>  
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

