---
title: "Cómo: Leer archivos de texto en Visual Basic"
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
- extended characters, reading
- reading text files
- reading data, text files
- examples [Visual Basic], reading text files
- text files, reading
ms.assetid: 735fe9d7-0f7a-4185-ba02-f35e580ec4b8
caps.latest.revision: 27
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
ms.openlocfilehash: 9b38b7f869a1d4ff290042a18a9bc2e0fa2709b7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-text-files-in-visual-basic"></a><span data-ttu-id="9b198-102">Cómo: Leer archivos de texto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b198-102">How to: Read From Text Files in Visual Basic</span></span>
<span data-ttu-id="9b198-103">El método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> del objeto `My.Computer.FileSystem` permite leer de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="9b198-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.ReadAllText%2A> method of the `My.Computer.FileSystem` object allows you to read from a text file.</span></span> <span data-ttu-id="9b198-104">Se puede especificar la codificación del archivo si el contenido del mismo utiliza una codificación como ASCII o UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9b198-104">The file encoding can be specified if the contents of the file use an encoding such as ASCII or UTF-8.</span></span>  
  
 <span data-ttu-id="9b198-105">Si está leyendo de un archivo que incluye caracteres extendidos, deberá especificar la codificación del archivo.</span><span class="sxs-lookup"><span data-stu-id="9b198-105">If you are reading from a file with extended characters, you will need to specify the file encoding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b198-106">Para leer una única línea de texto de un archivo a la vez, utilice el método <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> del objeto `My.Computer.FileSystem`.</span><span class="sxs-lookup"><span data-stu-id="9b198-106">To read a file a single line of text at a time, use the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.OpenTextFileReader%2A> method of the `My.Computer.FileSystem` object.</span></span> <span data-ttu-id="9b198-107">El método `OpenTextFileReader` devuelve un objeto <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="9b198-107">The `OpenTextFileReader` method returns a <xref:System.IO.StreamReader> object.</span></span> <span data-ttu-id="9b198-108">Puede usar el método <xref:System.IO.StreamReader.ReadLine%2A> del objeto `StreamReader` para leer de un archivo una línea a la vez.</span><span class="sxs-lookup"><span data-stu-id="9b198-108">You can use the <xref:System.IO.StreamReader.ReadLine%2A> method of the `StreamReader` object to read a file one line at a time.</span></span> <span data-ttu-id="9b198-109">Puede buscar el final del archivo con el método <xref:System.IO.StreamReader.EndOfStream%2A> del objeto `StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="9b198-109">You can test for the end of the file using the <xref:System.IO.StreamReader.EndOfStream%2A> method of the `StreamReader` object.</span></span>  
  
### <a name="to-read-from-a-text-file"></a><span data-ttu-id="9b198-110">Para leer de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="9b198-110">To read from a text file</span></span>  
  
-   <span data-ttu-id="9b198-111">Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9b198-111">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path.</span></span> <span data-ttu-id="9b198-112">El ejemplo siguiente lee el contenido del archivo test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b198-112">The following example reads the contents of test.txt into a string and then displays it in a message box.</span></span>  
  
     <span data-ttu-id="9b198-113">[!code-vb[VbFileIORead#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b198-113">[!code-vb[VbFileIORead#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_1.vb)]</span></span>  
  
### <a name="to-read-from-a-text-file-that-is-encoded"></a><span data-ttu-id="9b198-114">Para leer de un archivo de texto que está codificado</span><span class="sxs-lookup"><span data-stu-id="9b198-114">To read from a text file that is encoded</span></span>  
  
-   <span data-ttu-id="9b198-115">Utilice el método `ReadAllText` del objeto `My.Computer.FileSystem` para leer el contenido de un archivo de texto en una cadena, proporcionando la ruta de acceso y el tipo de codificación del archivo.</span><span class="sxs-lookup"><span data-stu-id="9b198-115">Use the `ReadAllText` method of the `My.Computer.FileSystem` object to read the contents of a text file into a string, supplying the path and file encoding type.</span></span> <span data-ttu-id="9b198-116">El ejemplo siguiente lee el contenido del archivo UTF32 test.txt, lo coloca en una cadena y, a continuación, lo muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9b198-116">The following example reads the contents of the UTF32 file test.txt into a string and then displays it in a message box.</span></span>  
  
     <span data-ttu-id="9b198-117">[!code-vb[VbFileIORead#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b198-117">[!code-vb[VbFileIORead#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9b198-118">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9b198-118">Robust Programming</span></span>  
 <span data-ttu-id="9b198-119">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="9b198-119">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9b198-120">La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, sólo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-120">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="9b198-121">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-121">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="9b198-122">El archivo no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-122">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="9b198-123">El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-123">The file is in use by another process or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="9b198-124">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-124">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="9b198-125">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-125">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="9b198-126">No hay suficiente memoria para escribir la cadena en el búfer (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-126">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
-   <span data-ttu-id="9b198-127">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="9b198-127">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="9b198-128">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="9b198-128">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="9b198-129">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b198-129">For example, the file Form1.vb may not be a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] source file.</span></span>  
  
 <span data-ttu-id="9b198-130">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b198-130">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="9b198-131">Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.</span><span class="sxs-lookup"><span data-stu-id="9b198-131">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b198-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b198-132">See Also</span></span>  
 <span data-ttu-id="9b198-133"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="9b198-133"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="9b198-134"><xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A></span><span class="sxs-lookup"><span data-stu-id="9b198-134"><xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A></span></span>   
 <span data-ttu-id="9b198-135">[Reading from Files in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  (Leer archivos en Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b198-135">[Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md) </span></span>  
 <span data-ttu-id="9b198-136">[Cómo: Leer archivos de texto delimitados por comas](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="9b198-136">[How to: Read From Comma-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md) </span></span>  
 <span data-ttu-id="9b198-137">[Cómo: Leer archivos de texto de ancho fijo](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="9b198-137">[How to: Read From Fixed-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md) </span></span>  
 <span data-ttu-id="9b198-138">[Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span><span class="sxs-lookup"><span data-stu-id="9b198-138">[How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md) </span></span>  
 <span data-ttu-id="9b198-139">[Solución de problemas: Leer y escribir en archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span><span class="sxs-lookup"><span data-stu-id="9b198-139">[Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md) </span></span>  
 <span data-ttu-id="9b198-140">[Tutorial: Manipulación de archivos y directorios en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span><span class="sxs-lookup"><span data-stu-id="9b198-140">[Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md) </span></span>  
 [<span data-ttu-id="9b198-141">Codificaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="9b198-141">File Encodings</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)

