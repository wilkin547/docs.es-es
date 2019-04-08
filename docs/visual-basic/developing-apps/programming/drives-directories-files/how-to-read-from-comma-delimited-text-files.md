---
title: 'Cómo: Leer archivos de texto delimitados por comas en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- reading text files [Visual Basic], comma-delimited
- text files [Visual Basic], reading
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
ms.openlocfilehash: 27a832dc5851393b8d655996e3f052cb3d759c7c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835445"
---
# <a name="how-to-read-from-comma-delimited-text-files-in-visual-basic"></a><span data-ttu-id="babe3-102">Cómo: Leer archivos de texto delimitados por comas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="babe3-102">How to: read from comma-delimited text files in Visual Basic</span></span>
<span data-ttu-id="babe3-103">El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros.</span><span class="sxs-lookup"><span data-stu-id="babe3-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span> <span data-ttu-id="babe3-104">La propiedad `TextFieldType` define si se trata de un archivo delimitado o de uno con campos de texto de ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="babe3-104">The `TextFieldType` property defines whether it is a delimited file or one with fixed-width fields of text.</span></span>  
  
### <a name="to-parse-a-comma-delimited-text-file"></a><span data-ttu-id="babe3-105">Para analizar un archivo de texto delimitado por comas</span><span class="sxs-lookup"><span data-stu-id="babe3-105">To parse a comma delimited text file</span></span>  
  
1.  <span data-ttu-id="babe3-106">Cree un nuevo objeto `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="babe3-106">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="babe3-107">El código siguiente crea el `TextFieldParser` denominado `MyReader` y abre el archivo `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="babe3-107">The following code creates the `TextFieldParser` named `MyReader` and opens the file `test.txt`.</span></span>  
  
     [!code-vb[VbFileIORead#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#15)]  
  
2.  <span data-ttu-id="babe3-108">Defina el tipo `TextField` y el delimitador.</span><span class="sxs-lookup"><span data-stu-id="babe3-108">Define the `TextField` type and delimiter.</span></span> <span data-ttu-id="babe3-109">El código siguiente define la propiedad `TextFieldType` como `Delimited` y el delimitador como ",".</span><span class="sxs-lookup"><span data-stu-id="babe3-109">The following code defines the `TextFieldType` property as `Delimited` and the delimiter as ",".</span></span>  
  
     [!code-vb[VbFileIORead#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#16)]  
  
3.  <span data-ttu-id="babe3-110">Recorra en bucle los campos del archivo.</span><span class="sxs-lookup"><span data-stu-id="babe3-110">Loop through the fields in the file.</span></span> <span data-ttu-id="babe3-111">Si hay alguna línea dañada, informe del error y siga analizando.</span><span class="sxs-lookup"><span data-stu-id="babe3-111">If any lines are corrupt, report an error and continue parsing.</span></span> <span data-ttu-id="babe3-112">El siguiente código recorre en bucle el archivo y muestra los campos por turnos e indica aquellos que tienen un formato incorrecto.</span><span class="sxs-lookup"><span data-stu-id="babe3-112">The following code loops through the file, displaying each field in turn and reporting any fields that are formatted incorrectly.</span></span>  
  
     [!code-vb[VbFileIORead#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#17)]  
  
4.  <span data-ttu-id="babe3-113">Cierre los bloques `While` y `Using` con `End While` y `End Using`.</span><span class="sxs-lookup"><span data-stu-id="babe3-113">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#18)]  
  
## <a name="example"></a><span data-ttu-id="babe3-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="babe3-114">Example</span></span>  
 <span data-ttu-id="babe3-115">En este ejemplo se lee el archivo `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="babe3-115">This example reads from the file `test.txt`.</span></span>  
  
 [!code-vb[VbFileIORead#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="babe3-116">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="babe3-116">Robust programming</span></span>  
 <span data-ttu-id="babe3-117">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="babe3-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="babe3-118">No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="babe3-118">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="babe3-119">El mensaje de excepción especifica la línea que inicia la excepción, mientras que a la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se le asigna el texto incluido en la línea.</span><span class="sxs-lookup"><span data-stu-id="babe3-119">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned the text contained in the line.</span></span>  
  
-   <span data-ttu-id="babe3-120">El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="babe3-120">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="babe3-121">Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="babe3-121">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="babe3-122">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="babe3-122">(<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="babe3-123">La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="babe3-123">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="babe3-124">El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="babe3-124">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babe3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="babe3-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="babe3-126">Cómo: Leer archivos de texto de ancho fijo</span><span class="sxs-lookup"><span data-stu-id="babe3-126">How to: Read From Fixed-width Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="babe3-127">Cómo: Leer archivos de texto con varios formatos</span><span class="sxs-lookup"><span data-stu-id="babe3-127">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="babe3-128">Análisis de archivos de texto con el objeto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="babe3-128">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="babe3-129">Tutorial: Manipulación de archivos y directorios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="babe3-129">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="babe3-130">Solución de problemas: Leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="babe3-130">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
