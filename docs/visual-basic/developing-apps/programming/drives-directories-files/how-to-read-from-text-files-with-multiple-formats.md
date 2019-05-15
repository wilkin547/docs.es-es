---
title: Procedimiento para leer archivos de texto con varios formatos en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- TextFieldParser object, reading from a file
- TextFieldType enumeration
- My.Computer.FileSystem.WriteAllText method, parsing structured text files
- WriteAllText method [Visual Basic], parsing structured text files
- PeekChars method [Visual Basic], determining format of text
- reading text files [Visual Basic], multiple formats
- I/O [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
ms.openlocfilehash: 9fa484f0a74d900bd6f0365f2ce71fd32e1422db
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623189"
---
# <a name="how-to-read-from-text-files-with-multiple-formats-in-visual-basic"></a><span data-ttu-id="ad875-102">Procedimiento para leer archivos de texto con varios formatos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad875-102">How to: Read From Text Files with Multiple Formats in Visual Basic</span></span>
<span data-ttu-id="ad875-103">El objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros.</span><span class="sxs-lookup"><span data-stu-id="ad875-103">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="ad875-104">Puede procesar un archivo con varios formatos usando el método `PeekChars` para determinar el formato de cada línea a medida que va analizando el archivo.</span><span class="sxs-lookup"><span data-stu-id="ad875-104">You can process a file with multiple formats by using the `PeekChars` method to determine the format of each line as you parse through the file.</span></span>  
  
### <a name="to-parse-a-text-file-with-multiple-formats"></a><span data-ttu-id="ad875-105">Para analizar un archivo de texto con varios formatos</span><span class="sxs-lookup"><span data-stu-id="ad875-105">To parse a text file with multiple formats</span></span>  
  
1. <span data-ttu-id="ad875-106">Agregue un archivo de texto denominado testfile.txt al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ad875-106">Add a text file named testfile.txt to your project.</span></span> <span data-ttu-id="ad875-107">Agregue el contenido siguiente al archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="ad875-107">Add the following content to the text file.</span></span>  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2. <span data-ttu-id="ad875-108">Defina el formato esperado y el formato usado cuando se cree un informe un error.</span><span class="sxs-lookup"><span data-stu-id="ad875-108">Define the expected format and the format used when an error is reported.</span></span> <span data-ttu-id="ad875-109">La última entrada en cada matriz es -1, por consiguiente se presupone que el último campo es de ancho variable.</span><span class="sxs-lookup"><span data-stu-id="ad875-109">The last entry in each array is -1, therefore the last field is assumed to be of variable width.</span></span> <span data-ttu-id="ad875-110">Esto se produce cuando la última entrada en la matriz es menor o igual que 0.</span><span class="sxs-lookup"><span data-stu-id="ad875-110">This occurs when the last entry in the array is less than or equal to 0.</span></span>  
  
     [!code-vb[VbFileIORead#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#4)]  
  
3. <span data-ttu-id="ad875-111">Cree un objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> que defina el ancho y el formato.</span><span class="sxs-lookup"><span data-stu-id="ad875-111">Create a new <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object, defining the width and format.</span></span>  
  
     [!code-vb[VbFileIORead#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#5)]  
  
4. <span data-ttu-id="ad875-112">Recorra en iteración las filas, probando el formato antes de leerlas.</span><span class="sxs-lookup"><span data-stu-id="ad875-112">Loop through the rows, testing for format before reading.</span></span>  
  
     [!code-vb[VbFileIORead#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#6)]  
  
5. <span data-ttu-id="ad875-113">Escriba los errores en la consola.</span><span class="sxs-lookup"><span data-stu-id="ad875-113">Write errors to the console.</span></span>  
  
     [!code-vb[VbFileIORead#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="ad875-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad875-114">Example</span></span>  
 <span data-ttu-id="ad875-115">A continuación se proporciona el ejemplo completo que lee del archivo `testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="ad875-115">Following is the complete example that reads from the file `testfile.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ad875-116">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ad875-116">Robust Programming</span></span>  
 <span data-ttu-id="ad875-117">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="ad875-117">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ad875-118">No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="ad875-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="ad875-119">El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.</span><span class="sxs-lookup"><span data-stu-id="ad875-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="ad875-120">El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="ad875-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="ad875-121">Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="ad875-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="ad875-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="ad875-122">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="ad875-123">La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="ad875-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="ad875-124">El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="ad875-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad875-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad875-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>
- <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>
- [<span data-ttu-id="ad875-126">Cómo: Leer archivos de texto delimitado por comas</span><span class="sxs-lookup"><span data-stu-id="ad875-126">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="ad875-127">Cómo: Leer archivos de texto de ancho fijo</span><span class="sxs-lookup"><span data-stu-id="ad875-127">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="ad875-128">Análisis de archivos de texto con el objeto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="ad875-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
