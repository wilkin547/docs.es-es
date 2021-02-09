---
description: 'Más información acerca de: Cómo: Leer archivos de texto de ancho fijo en Visual Basic'
title: Procedimiento para leer archivos de texto de ancho fijo
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 4f5868fa68009851cc65eeaf5ff6431ac22840d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797463"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a><span data-ttu-id="1346e-103">Cómo: Leer archivos de texto de ancho fijo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1346e-103">How to: read from fixed-width text files in Visual Basic</span></span>

<span data-ttu-id="1346e-104">El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros.</span><span class="sxs-lookup"><span data-stu-id="1346e-104">The `TextFieldParser` object provides a way to easily and efficiently parse structured text files, such as logs.</span></span>  
  
 <span data-ttu-id="1346e-105">La propiedad `TextFieldType` define si el archivo analizado se trata de un archivo delimitado o uno que tiene campos de texto de ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="1346e-105">The `TextFieldType` property defines whether the parsed file is a delimited file or one that has fixed-width fields of text.</span></span> <span data-ttu-id="1346e-106">En un archivo de texto de ancho fijo, el campo puede tener un ancho variable al final.</span><span class="sxs-lookup"><span data-stu-id="1346e-106">In a fixed-width text file, the field at the end can have a variable width.</span></span> <span data-ttu-id="1346e-107">Para especificar que el campo tiene un ancho variable al final, debe definirlo para que tenga un ancho menor o igual que cero.</span><span class="sxs-lookup"><span data-stu-id="1346e-107">To specify that the field at the end has a variable width, define it to have a width less than or equal to zero.</span></span>  
  
### <a name="to-parse-a-fixed-width-text-file"></a><span data-ttu-id="1346e-108">Para analizar un archivo de texto de ancho fijo</span><span class="sxs-lookup"><span data-stu-id="1346e-108">To parse a fixed-width text file</span></span>  
  
1. <span data-ttu-id="1346e-109">Cree un nuevo `TextFieldParser`.</span><span class="sxs-lookup"><span data-stu-id="1346e-109">Create a new `TextFieldParser`.</span></span> <span data-ttu-id="1346e-110">El código siguiente crea el `TextFieldParser` denominado `Reader` y abre el archivo `test.log`.</span><span class="sxs-lookup"><span data-stu-id="1346e-110">The following code creates the `TextFieldParser` named `Reader` and opens the file `test.log`.</span></span>  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. <span data-ttu-id="1346e-111">Defina la propiedad `TextFieldType` como `FixedWidth` definiendo el ancho y el formato.</span><span class="sxs-lookup"><span data-stu-id="1346e-111">Define the `TextFieldType` property as `FixedWidth`, defining the width and format.</span></span> <span data-ttu-id="1346e-112">El código siguiente define las columnas de texto; la primera tiene un ancho de 5 caracteres, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.</span><span class="sxs-lookup"><span data-stu-id="1346e-112">The following code defines the columns of text; the first is 5 characters wide, the second 10, the third 11, and the fourth is of variable width.</span></span>  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. <span data-ttu-id="1346e-113">Recorra en bucle los campos del archivo.</span><span class="sxs-lookup"><span data-stu-id="1346e-113">Loop through the fields in the file.</span></span> <span data-ttu-id="1346e-114">Si alguna línea está dañada, cree un informe de error y continúe el análisis.</span><span class="sxs-lookup"><span data-stu-id="1346e-114">If any lines are corrupted, report an error and continue parsing.</span></span>  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. <span data-ttu-id="1346e-115">Cierre los bloques `While` y `Using` con `End While` y `End Using`.</span><span class="sxs-lookup"><span data-stu-id="1346e-115">Close the `While` and `Using` blocks with `End While` and `End Using`.</span></span>  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="1346e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1346e-116">Example</span></span>  

 <span data-ttu-id="1346e-117">En este ejemplo se lee el archivo `test.log`.</span><span class="sxs-lookup"><span data-stu-id="1346e-117">This example reads from the file `test.log`.</span></span>  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a><span data-ttu-id="1346e-118">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="1346e-118">Robust programming</span></span>  

 <span data-ttu-id="1346e-119">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="1346e-119">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="1346e-120">No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span><span class="sxs-lookup"><span data-stu-id="1346e-120">A row cannot be parsed using the specified format (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>).</span></span> <span data-ttu-id="1346e-121">El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.</span><span class="sxs-lookup"><span data-stu-id="1346e-121">The exception message specifies the line causing the exception, while the <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> property is assigned to the text contained in the line.</span></span>  
  
- <span data-ttu-id="1346e-122">El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="1346e-122">The specified file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="1346e-123">Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="1346e-123">A partial-trust situation in which the user does not have sufficient permissions to access the file.</span></span> <span data-ttu-id="1346e-124">(<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="1346e-124">(<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="1346e-125">La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="1346e-125">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="1346e-126">El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="1346e-126">The user does not have sufficient permissions to access the file (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1346e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1346e-127">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [<span data-ttu-id="1346e-128">Procedimiento para leer archivos de texto delimitado por comas</span><span class="sxs-lookup"><span data-stu-id="1346e-128">How to: Read From Comma-Delimited Text Files</span></span>](how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="1346e-129">Procedimiento para leer archivos de texto con varios formatos</span><span class="sxs-lookup"><span data-stu-id="1346e-129">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="1346e-130">Analizar archivos de texto con el objeto TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="1346e-130">Parsing Text Files with the TextFieldParser Object</span></span>](parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="1346e-131">Tutorial: Manipulación de archivos y directorios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1346e-131">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="1346e-132">Solución del problema: leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="1346e-132">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
