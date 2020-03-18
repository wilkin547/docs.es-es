---
title: 'Cómo: Leer archivos binarios'
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: c33bc72a5c79901e3715ed6a587ffdb8e3565e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74335294"
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a><span data-ttu-id="ea8d9-102">Cómo: Leer archivos binarios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea8d9-102">How to: Read From Binary Files in Visual Basic</span></span>

<span data-ttu-id="ea8d9-103">El objeto `My.Computer.FileSystem` proporciona el método `ReadAllBytes` para leer archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-103">The `My.Computer.FileSystem` object provides the `ReadAllBytes` method for reading from binary files.</span></span>  
  
### <a name="to-read-from-a-binary-file"></a><span data-ttu-id="ea8d9-104">Para leer un archivo binario</span><span class="sxs-lookup"><span data-stu-id="ea8d9-104">To read from a binary file</span></span>  
  
- <span data-ttu-id="ea8d9-105">Use el método `ReadAllBytes`, que devuelve el contenido de un archivo como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-105">Use the `ReadAllBytes` method, which returns the contents of a file as a byte array.</span></span> <span data-ttu-id="ea8d9-106">En este ejemplo se lee el archivo `C:/Documents and Settings/selfportrait.jpg`.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-106">This example reads from the file `C:/Documents and Settings/selfportrait.jpg`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#78)]  
  
- <span data-ttu-id="ea8d9-107">Para los archivos binarios grandes, puede usar el método <xref:System.IO.FileStream.Read%2A> del objeto <xref:System.IO.FileStream> para leer solo una cantidad especificada del archivo a la vez.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-107">For large binary files, you can use the <xref:System.IO.FileStream.Read%2A> method of the <xref:System.IO.FileStream> object to read from the file only a specified amount at a time.</span></span> <span data-ttu-id="ea8d9-108">Después, puede limitar la cantidad de contenido del archivo que se carga en memoria para cada operación de lectura.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-108">You can then limit how much of the file is loaded into memory for each read operation.</span></span> <span data-ttu-id="ea8d9-109">En el ejemplo de código siguiente se copia un archivo y se permite al autor de la llamada especificar la cantidad de contenido del archivo que se lee en memoria por cada operación de lectura.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-109">The following code example copies a file and allows the caller to specify how much of the file is read into memory per read operation.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#91)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ea8d9-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ea8d9-110">Robust Programming</span></span>  

 <span data-ttu-id="ea8d9-111">Las condiciones siguientes pueden provocar que se produzca una excepción:</span><span class="sxs-lookup"><span data-stu-id="ea8d9-111">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="ea8d9-112">La ruta de acceso no es válida por una de las razones siguientes: es una cadena de longitud cero, sólo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="ea8d9-113">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="ea8d9-114">El archivo no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-114">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="ea8d9-115">El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-115">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="ea8d9-116">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-116">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="ea8d9-117">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-117">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="ea8d9-118">No hay suficiente memoria para escribir la cadena en el búfer (<xref:System.OutOfMemoryException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-118">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
- <span data-ttu-id="ea8d9-119">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="ea8d9-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="ea8d9-120">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="ea8d9-121">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-121">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="ea8d9-122">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-122">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="ea8d9-123">Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.</span><span class="sxs-lookup"><span data-stu-id="ea8d9-123">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8d9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea8d9-124">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [<span data-ttu-id="ea8d9-125">Leer archivos</span><span class="sxs-lookup"><span data-stu-id="ea8d9-125">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="ea8d9-126">Leer archivos de texto con varios formatos</span><span class="sxs-lookup"><span data-stu-id="ea8d9-126">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="ea8d9-127">Almacenar y leer datos en el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="ea8d9-127">Storing Data to and Reading from the Clipboard</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
