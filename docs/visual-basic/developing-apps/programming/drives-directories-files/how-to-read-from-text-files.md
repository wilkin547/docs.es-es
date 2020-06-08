---
title: Procedimiento para leer archivos de texto
ms.date: 07/20/2015
helpviewer_keywords:
- extended characters [Visual Basic], reading
- reading text files [Visual Basic]
- reading data, text files
- examples [Visual Basic], reading text files
- text files [Visual Basic], reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
ms.openlocfilehash: 0d99209ed123686355e8d49c82ba23f94084f895
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411621"
---
# <a name="how-to-read-from-text-files-in-visual-basic"></a><span data-ttu-id="b68f3-102">Procedimiento para leer archivos de texto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b68f3-102">How to: Read From Text Files in Visual Basic</span></span>

<span data-ttu-id="b68f3-103">El método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> del objeto `My.Computer.FileSystem` permite leer de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="b68f3-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> method of the `My.Computer.FileSystem` object allows you to read from a text file.</span></span> <span data-ttu-id="b68f3-104">Se puede especificar la codificación del archivo si el contenido del mismo utiliza una codificación como ASCII o UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b68f3-104">The file encoding can be specified if the contents of the file use an encoding such as ASCII or UTF-8.</span></span>

<span data-ttu-id="b68f3-105">Si está leyendo de un archivo que incluye caracteres extendidos, deberá especificar la codificación del archivo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-105">If you are reading from a file with extended characters, you will need to specify the file encoding.</span></span>

> [!NOTE]
> <span data-ttu-id="b68f3-106">Para leer una única línea de texto de un archivo a la vez, utilice el método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> del objeto `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="b68f3-106">To read a file a single line of text at a time, use the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> method of the `My.Computer.FileSystem` object.</span></span> <span data-ttu-id="b68f3-107">El método `OpenTextFileReader` devuelve un objeto <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="b68f3-107">The `OpenTextFileReader` method returns a <xref:System.IO.StreamReader> object.</span></span> <span data-ttu-id="b68f3-108">Puede usar el método <xref:System.IO.StreamReader.ReadLine%2A> del objeto `StreamReader` para leer de un archivo una línea a la vez.</span><span class="sxs-lookup"><span data-stu-id="b68f3-108">You can use the <xref:System.IO.StreamReader.ReadLine%2A> method of the `StreamReader` object to read a file one line at a time.</span></span> <span data-ttu-id="b68f3-109">Puede buscar el final del archivo con el método <xref:System.IO.StreamReader.EndOfStream%2A> del objeto `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="b68f3-109">You can test for the end of the file using the <xref:System.IO.StreamReader.EndOfStream%2A> method of the `StreamReader` object.</span></span>

## <a name="to-read-from-a-text-file"></a><span data-ttu-id="b68f3-110">Para leer de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="b68f3-110">To read from a text file</span></span>

<span data-ttu-id="b68f3-111">Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="b68f3-111">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path.</span></span> <span data-ttu-id="b68f3-112">El ejemplo siguiente lee el contenido del archivo test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="b68f3-112">The following example reads the contents of test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#2)]

### <a name="to-read-from-a-text-file-that-is-encoded"></a><span data-ttu-id="b68f3-113">Para leer de un archivo de texto que está codificado</span><span class="sxs-lookup"><span data-stu-id="b68f3-113">To read from a text file that is encoded</span></span>

<span data-ttu-id="b68f3-114">Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso y el tipo de codificación del archivo.</span><span class="sxs-lookup"><span data-stu-id="b68f3-114">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path and file encoding type.</span></span> <span data-ttu-id="b68f3-115">El ejemplo siguiente lee el contenido del archivo UTF32 test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="b68f3-115">The following example reads the contents of the UTF32 file test.txt into a string and then displays it in a message box.</span></span>

[!code-vb[VbFileIORead#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#3)]

## <a name="robust-programming"></a><span data-ttu-id="b68f3-116">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b68f3-116">Robust Programming</span></span>

<span data-ttu-id="b68f3-117">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="b68f3-117">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="b68f3-118">La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, sólo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-118">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="b68f3-119">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-119">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="b68f3-120">El archivo no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-120">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>

- <span data-ttu-id="b68f3-121">El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-121">The file is in use by another process or an I/O error occurs (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="b68f3-122">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>

- <span data-ttu-id="b68f3-123">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-123">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>

- <span data-ttu-id="b68f3-124">No hay suficiente memoria para escribir la cadena en el búfer (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-124">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>

- <span data-ttu-id="b68f3-125">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="b68f3-125">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>

<span data-ttu-id="b68f3-126">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="b68f3-126">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="b68f3-127">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b68f3-127">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>

<span data-ttu-id="b68f3-128">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b68f3-128">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="b68f3-129">Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.</span><span class="sxs-lookup"><span data-stu-id="b68f3-129">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>

## <a name="see-also"></a><span data-ttu-id="b68f3-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b68f3-130">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
- [<span data-ttu-id="b68f3-131">Leer archivos</span><span class="sxs-lookup"><span data-stu-id="b68f3-131">Reading from Files</span></span>](reading-from-files.md)
- [<span data-ttu-id="b68f3-132">Cómo: Leer archivos de texto delimitado por comas</span><span class="sxs-lookup"><span data-stu-id="b68f3-132">How to: Read From Comma-Delimited Text Files</span></span>](how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="b68f3-133">Cómo: Leer archivos de texto de ancho fijo</span><span class="sxs-lookup"><span data-stu-id="b68f3-133">How to: Read From Fixed-width Text Files</span></span>](how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="b68f3-134">Cómo: Leer archivos de texto con varios formatos</span><span class="sxs-lookup"><span data-stu-id="b68f3-134">How to: Read From Text Files with Multiple Formats</span></span>](how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="b68f3-135">Solución de problemas: Leer y escribir en archivos de texto</span><span class="sxs-lookup"><span data-stu-id="b68f3-135">Troubleshooting: Reading from and Writing to Text Files</span></span>](troubleshooting-reading-from-and-writing-to-text-files.md)
- [<span data-ttu-id="b68f3-136">Tutorial: Manipulación de archivos y directorios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b68f3-136">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>](walkthrough-manipulating-files-and-directories.md)
- [<span data-ttu-id="b68f3-137">Codificaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="b68f3-137">File Encodings</span></span>](file-encodings.md)
