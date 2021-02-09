---
description: 'Más información acerca de: Analizar archivos de texto con el objeto TextFieldParser (Visual Basic)'
title: Análisis de archivos de texto con el objeto TextFieldParser
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, using
- I/O [Visual Basic], parsing files
- files [Visual Basic], parsing
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
ms.openlocfilehash: 7ba3e9f98e4fea882260e8f194d59fda8eda9f69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797385"
---
# <a name="parsing-text-files-with-the-textfieldparser-object-visual-basic"></a><span data-ttu-id="6b60c-103">Analizar archivos de texto con el objeto TextFieldParser (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b60c-103">Parsing text files with the TextFieldParser object (Visual Basic)</span></span>

<span data-ttu-id="6b60c-104">El objeto `TextFieldParser` permite analizar y procesar archivos muy grandes estructurados como columnas de texto con ancho delimitado, como archivos de registro o información de la base de datos heredada.</span><span class="sxs-lookup"><span data-stu-id="6b60c-104">The `TextFieldParser` object allows you to parse and process very large file that are structured as delimited-width columns of text, such as log files or legacy database information.</span></span> <span data-ttu-id="6b60c-105">Analizar un archivo de texto con `TextFieldParser` es similar a recorrer en iteración un archivo de texto, mientras que el método parse para extraer campos de texto es similar a los métodos de manipulación de cadenas usados para acortar cadenas delimitadas.</span><span class="sxs-lookup"><span data-stu-id="6b60c-105">Parsing a text file with `TextFieldParser` is similar to iterating over a text file, while the parse method to extract fields of text is similar to string manipulation methods used to tokenize delimited strings.</span></span>  
  
## <a name="parsing-different-types-of-text-files"></a><span data-ttu-id="6b60c-106">Analizar diferentes tipos de archivos de texto</span><span class="sxs-lookup"><span data-stu-id="6b60c-106">Parsing different types of text files</span></span>  

 <span data-ttu-id="6b60c-107">Los archivos de texto pueden tener campos con diversas anchuras, delimitados por un carácter, como una coma o un espacio de tabulación.</span><span class="sxs-lookup"><span data-stu-id="6b60c-107">Text files may have fields of various width, delimited by a character such as a comma or a tab space.</span></span> <span data-ttu-id="6b60c-108">Defina `TextFieldType` y el delimitador, como en el ejemplo siguiente, que usa el método `SetDelimiters` para definir un archivo de texto delimitado por tabulaciones:</span><span class="sxs-lookup"><span data-stu-id="6b60c-108">Define `TextFieldType` and the delimiter, as in the following example, which uses the `SetDelimiters` method to define a tab-delimited text file:</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#21)]  
  
 <span data-ttu-id="6b60c-109">Otros archivos de texto pueden tener anchos de campos fijos.</span><span class="sxs-lookup"><span data-stu-id="6b60c-109">Other text files may have field widths that are fixed.</span></span> <span data-ttu-id="6b60c-110">En tales casos, debe definir `TextFieldType` como `FixedWidth` y definir los anchos de cada campo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6b60c-110">In such cases, you need to define the `TextFieldType` as `FixedWidth` and define the widths of each field, as in the following example.</span></span> <span data-ttu-id="6b60c-111">En este ejemplo se usa el método `SetFieldWidths` para definir las columnas de texto: la primera columna es de 5 caracteres de ancho, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.</span><span class="sxs-lookup"><span data-stu-id="6b60c-111">This example uses the `SetFieldWidths` method to define the columns of text: the first column is 5 characters wide, the second is 10, the third is 11, and the fourth is of variable width.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#22)]  
  
 <span data-ttu-id="6b60c-112">Una vez definido el formato, puede recorrer en bucle el archivo usando el método `ReadFields` para procesar cada línea sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6b60c-112">Once the format is defined, you can loop through the file, using the `ReadFields` method to process each line in turn.</span></span>  
  
 <span data-ttu-id="6b60c-113">Si un campo no coincide con el formato especificado, se genera una excepción <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>.</span><span class="sxs-lookup"><span data-stu-id="6b60c-113">If a field does not match the specified format, a <xref:Microsoft.VisualBasic.FileIO.MalformedLineException> exception is thrown.</span></span> <span data-ttu-id="6b60c-114">Cuando se producen dichas excepciones, en las propiedades `ErrorLine` y `ErrorLineNumber` se indica el texto que da lugar a la excepción y el número de línea de dicho texto.</span><span class="sxs-lookup"><span data-stu-id="6b60c-114">When such exceptions are thrown, the `ErrorLine` and `ErrorLineNumber` properties hold the text causing the exception and the line number of that text.</span></span>  
  
## <a name="parsing-files-with-multiple-formats"></a><span data-ttu-id="6b60c-115">Analizar archivos con varios formatos</span><span class="sxs-lookup"><span data-stu-id="6b60c-115">Parsing files with multiple formats</span></span>  

 <span data-ttu-id="6b60c-116">El método `PeekChars` del objeto `TextFieldParser` se puede usar para comprobar cada campo antes de leerlo, lo que le permite definir varios formatos para los campos y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="6b60c-116">The `PeekChars` method of the `TextFieldParser` object can be used to check each field before reading it, allowing you to define multiple formats for the fields and react accordingly.</span></span> <span data-ttu-id="6b60c-117">Para obtener más información, consulte [Cómo: Leer archivos de texto con varios formatos](how-to-read-from-text-files-with-multiple-formats.md).</span><span class="sxs-lookup"><span data-stu-id="6b60c-117">For more information, see [How to: Read From Text Files with Multiple Formats](how-to-read-from-text-files-with-multiple-formats.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b60c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b60c-118">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>
