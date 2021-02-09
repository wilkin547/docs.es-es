---
description: 'Más información acerca de: Procedimiento: para cambiar el nombre de un archivo en Visual Basic'
title: Procedimiento para cambiar el nombre de un archivo
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files [Visual Basic], renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
ms.openlocfilehash: cf182fa94befdfdcb1568052a0193d483670cf49
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797411"
---
# <a name="how-to-rename-a-file-in-visual-basic"></a><span data-ttu-id="c521a-103">Cómo: Cambiar el nombre de un archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c521a-103">How to: Rename a File in Visual Basic</span></span>

<span data-ttu-id="c521a-104">Use el método `RenameFile` del objeto `My.Computer.FileSystem` para cambiar el nombre de un archivo proporcionando la ubicación actual, el nombre de archivo y el nombre de archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="c521a-104">Use the `RenameFile` method of the `My.Computer.FileSystem` object to rename a file by supplying the current location, file name, and the new file name.</span></span> <span data-ttu-id="c521a-105">No se puede usar este método para mover un archivo. Use el método `MoveFile` para mover y cambiar el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="c521a-105">This method cannot be used to move a file; use the `MoveFile` method to move and rename the file.</span></span>  
  
### <a name="to-rename-a-file"></a><span data-ttu-id="c521a-106">Para cambiar el nombre de un archivo</span><span class="sxs-lookup"><span data-stu-id="c521a-106">To rename a file</span></span>  
  
- <span data-ttu-id="c521a-107">Use el método `My.Computer.FileSystem.RenameFile` para cambiar el nombre de un archivo.</span><span class="sxs-lookup"><span data-stu-id="c521a-107">Use the `My.Computer.FileSystem.RenameFile` method to rename a file.</span></span> <span data-ttu-id="c521a-108">En este ejemplo se cambia el nombre del archivo `Test.txt` por `SecondTest.txt`.</span><span class="sxs-lookup"><span data-stu-id="c521a-108">This example renames the file named `Test.txt` to `SecondTest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#9)]  
  
 <span data-ttu-id="c521a-109">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c521a-109">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c521a-110">En el selector de fragmentos de código, el fragmento de código se encuentra en **Sistema de archivos - procesamiento de unidades, carpetas y archivos**.</span><span class="sxs-lookup"><span data-stu-id="c521a-110">In the code snippet picker, the snippet is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="c521a-111">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="c521a-111">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c521a-112">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c521a-112">Robust Programming</span></span>  

 <span data-ttu-id="c521a-113">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="c521a-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="c521a-114">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="c521a-115">`newName` contiene información de ruta de acceso (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-115">`newName` contains path information (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="c521a-116">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-116">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="c521a-117">`newName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-117">`newName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="c521a-118">El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-118">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="c521a-119">Hay un archivo o directorio con el nombre especificado en `newName` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-119">There is an existing file or directory with the name specified in `newName` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="c521a-120">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-120">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="c521a-121">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-121">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="c521a-122">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="c521a-123">El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="c521a-123">The user does not have the required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c521a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c521a-124">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>
- [<span data-ttu-id="c521a-125">Procedimiento para mover un archivo</span><span class="sxs-lookup"><span data-stu-id="c521a-125">How to: Move a File</span></span>](how-to-move-a-file.md)
- [<span data-ttu-id="c521a-126">Creación, eliminación y movimiento de archivos y directorios</span><span class="sxs-lookup"><span data-stu-id="c521a-126">Creating, Deleting, and Moving Files and Directories</span></span>](creating-deleting-and-moving-files-and-directories.md)
- [<span data-ttu-id="c521a-127">Procedimiento para crear una copia de un archivo en el mismo directorio</span><span class="sxs-lookup"><span data-stu-id="c521a-127">How to: Create a Copy of a File in the Same Directory</span></span>](how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="c521a-128">Procedimiento para crear una copia de un archivo en otro directorio</span><span class="sxs-lookup"><span data-stu-id="c521a-128">How to: Create a Copy of a File in a Different Directory</span></span>](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
