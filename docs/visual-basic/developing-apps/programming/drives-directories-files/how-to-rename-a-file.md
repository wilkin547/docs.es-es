---
title: 'Cómo: Cambiar el nombre de un archivo'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files [Visual Basic], renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
ms.openlocfilehash: 3de41ee6627315f0e26964b75f564ff98fe472ec
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411595"
---
# <a name="how-to-rename-a-file-in-visual-basic"></a><span data-ttu-id="f9de2-102">Cómo: Cambiar el nombre de un archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9de2-102">How to: Rename a File in Visual Basic</span></span>

<span data-ttu-id="f9de2-103">Use el método `RenameFile` del objeto `My.Computer.FileSystem` para cambiar el nombre de un archivo proporcionando la ubicación actual, el nombre de archivo y el nombre de archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="f9de2-103">Use the `RenameFile` method of the `My.Computer.FileSystem` object to rename a file by supplying the current location, file name, and the new file name.</span></span> <span data-ttu-id="f9de2-104">No se puede usar este método para mover un archivo. Use el método `MoveFile` para mover y cambiar el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="f9de2-104">This method cannot be used to move a file; use the `MoveFile` method to move and rename the file.</span></span>  
  
### <a name="to-rename-a-file"></a><span data-ttu-id="f9de2-105">Para cambiar el nombre de un archivo</span><span class="sxs-lookup"><span data-stu-id="f9de2-105">To rename a file</span></span>  
  
- <span data-ttu-id="f9de2-106">Use el método `My.Computer.FileSystem.RenameFile` para cambiar el nombre de un archivo.</span><span class="sxs-lookup"><span data-stu-id="f9de2-106">Use the `My.Computer.FileSystem.RenameFile` method to rename a file.</span></span> <span data-ttu-id="f9de2-107">En este ejemplo se cambia el nombre del archivo `Test.txt` por `SecondTest.txt`.</span><span class="sxs-lookup"><span data-stu-id="f9de2-107">This example renames the file named `Test.txt` to `SecondTest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#9)]  
  
 <span data-ttu-id="f9de2-108">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f9de2-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="f9de2-109">En el selector de fragmentos de código, el fragmento de código se encuentra en **Sistema de archivos - procesamiento de unidades, carpetas y archivos**.</span><span class="sxs-lookup"><span data-stu-id="f9de2-109">In the code snippet picker, the snippet is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="f9de2-110">Para obtener más información, vea [Code Snippets](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="f9de2-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f9de2-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="f9de2-111">Robust Programming</span></span>  

 <span data-ttu-id="f9de2-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="f9de2-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="f9de2-113">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="f9de2-114">`newName` contiene información de ruta de acceso (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-114">`newName` contains path information (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="f9de2-115">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="f9de2-116">`newName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-116">`newName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="f9de2-117">El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-117">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="f9de2-118">Hay un archivo o directorio con el nombre especificado en `newName` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-118">There is an existing file or directory with the name specified in `newName` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="f9de2-119">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="f9de2-120">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="f9de2-121">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="f9de2-122">El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="f9de2-122">The user does not have the required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9de2-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9de2-123">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>
- [<span data-ttu-id="f9de2-124">Mover archivos</span><span class="sxs-lookup"><span data-stu-id="f9de2-124">How to: Move a File</span></span>](how-to-move-a-file.md)
- [<span data-ttu-id="f9de2-125">Creación, eliminación y movimiento de archivos y directorios</span><span class="sxs-lookup"><span data-stu-id="f9de2-125">Creating, Deleting, and Moving Files and Directories</span></span>](creating-deleting-and-moving-files-and-directories.md)
- [<span data-ttu-id="f9de2-126">Crear una copia de un archivo en el mismo directorio</span><span class="sxs-lookup"><span data-stu-id="f9de2-126">How to: Create a Copy of a File in the Same Directory</span></span>](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="f9de2-127">Crear una copia de un archivo en un directorio diferente</span><span class="sxs-lookup"><span data-stu-id="f9de2-127">How to: Create a Copy of a File in a Different Directory</span></span>](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
