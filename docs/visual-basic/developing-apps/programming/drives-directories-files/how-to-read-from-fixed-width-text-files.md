---
title: Procedimiento para leer archivos de texto de ancho fijo
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 3cea9bfe2388f0ca510b15cb020f899b81c4603c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334620"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="a598d-102">Cómo: Leer archivos de texto de ancho fijo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a598d-102">How to: read from fixed-width text files in Visual Basic</span></span>

<span data-ttu-id="a598d-103">El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros.</span><span class="sxs-lookup"><span data-stu-id="a598d-103">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="a598d-104">La propiedad `TextFieldType` define si el archivo analizado se trata de un archivo delimitado o uno que tiene campos de texto de ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="a598d-104">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="a598d-105">En un archivo de texto de ancho fijo, el campo puede tener un ancho variable al final.</span><span class="sxs-lookup"><span data-stu-id="a598d-105">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="a598d-106">Para especificar que el campo tiene un ancho variable al final, debe definirlo para que tenga un ancho menor o igual que cero.</span><span class="sxs-lookup"><span data-stu-id="a598d-106">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="a598d-107">Para analizar un archivo de texto de ancho fijo</span><span class="sxs-lookup"><span data-stu-id="a598d-107">To parse a fixed-width text file</span></span>  
  
1. <span data-ttu-id="a598d-108">Cree un nuevo objeto `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="a598d-108">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="a598d-109">El código siguiente crea el `TextFieldParser` denominado `Reader` y abre el archivo `test.log`.</span><span class="sxs-lookup"><span data-stu-id="a598d-109">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. <span data-ttu-id="a598d-110">Defina la propiedad `TextFieldType` como `FixedWidth` definiendo el ancho y el formato.</span><span class="sxs-lookup"><span data-stu-id="a598d-110">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="a598d-111">El código siguiente define las columnas de texto; la primera tiene un ancho de 5 caracteres, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.</span><span class="sxs-lookup"><span data-stu-id="a598d-111">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. <span data-ttu-id="a598d-112">Recorra en bucle los campos del archivo.</span><span class="sxs-lookup"><span data-stu-id="a598d-112">Loop through the fields in the file.</span></span> <span data-ttu-id="a598d-113">Si alguna línea está dañada, cree un informe de error y continúe el análisis.</span><span class="sxs-lookup"><span data-stu-id="a598d-113">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. <span data-ttu-id="a598d-114">Cierre los bloques `While` y `Using` con `End While` y `End Using`.</span><span class="sxs-lookup"><span data-stu-id="a598d-114">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a598d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a598d-115">Example</span></span>  

 <span data-ttu-id="a598d-116">En este ejemplo se lee el archivo `test.log`.</span><span class="sxs-lookup"><span data-stu-id="a598d-116">This example reads from the file `test.log`.</span></span>  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a598d-117">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a598d-117">Robust programming</span></span>  

 <span data-ttu-id="a598d-118">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="a598d-118">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="a598d-119">No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="a598d-119">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="a598d-120">El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.</span><span class="sxs-lookup"><span data-stu-id="a598d-120">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="a598d-121">El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="a598d-121">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="a598d-122">Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="a598d-122">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="a598d-123">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="a598d-123">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="a598d-124">La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="a598d-124">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="a598d-125">El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="a598d-125">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a598d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a598d-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="a598d-127">Leer archivos de texto delimitado por comas</span><span class="sxs-lookup"><span data-stu-id="a598d-127">How to: Read From Comma-Delimited Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="a598d-128">Leer archivos de texto con varios formatos</span><span class="sxs-lookup"><span data-stu-id="a598d-128">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="a598d-129">Análisis de archivos de texto con el objeto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="a598d-129">Parsing Text Files with the TextFieldParser Object</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="a598d-130">Tutorial: Manipular archivos y directorios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a598d-130">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="a598d-131">Solución de problemas: Leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="a598d-131">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
