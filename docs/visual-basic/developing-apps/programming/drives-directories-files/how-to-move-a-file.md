---
title: 'Cómo: Mover archivos'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
ms.openlocfilehash: 2dafeb3b5f8b8c3a8976b25c1a57f405aebb32b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401607"
---
# <a name="how-to-move-a-file-in-visual-basic"></a><span data-ttu-id="e6d74-102">Cómo: Mover un archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6d74-102">How to: Move a File in Visual Basic</span></span>

<span data-ttu-id="e6d74-103">El método `My.Computer.FileSystem.MoveFile` se puede usar para mover un archivo a otra carpeta.</span><span class="sxs-lookup"><span data-stu-id="e6d74-103">The `My.Computer.FileSystem.MoveFile` method can be used to move a file to another folder.</span></span> <span data-ttu-id="e6d74-104">Si la estructura de destino no existe, se creará.</span><span class="sxs-lookup"><span data-stu-id="e6d74-104">If the target structure does not exist, it will be created.</span></span>  
  
### <a name="to-move-a-file"></a><span data-ttu-id="e6d74-105">Para mover un archivo</span><span class="sxs-lookup"><span data-stu-id="e6d74-105">To move a file</span></span>  
  
- <span data-ttu-id="e6d74-106">Use el método `MoveFile` para mover el archivo, y especifique el nombre y la ubicación de los archivos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="e6d74-106">Use the `MoveFile` method to move the file, specifying the file name and location for both the source file and the target file.</span></span> <span data-ttu-id="e6d74-107">En este ejemplo se mueve el archivo denominado `test.txt` de `TestDir1` a `TestDir2`.</span><span class="sxs-lookup"><span data-stu-id="e6d74-107">This example moves the file named `test.txt` from `TestDir1` to `TestDir2`.</span></span> <span data-ttu-id="e6d74-108">Observe que el nombre del archivo de destino se especifica aunque coincida con el nombre del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="e6d74-108">Note that the target file name is specified even though it is the same as the source file name.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#24)]  
  
### <a name="to-move-a-file-and-rename-it"></a><span data-ttu-id="e6d74-109">Para mover un archivo y cambiarle el nombre</span><span class="sxs-lookup"><span data-stu-id="e6d74-109">To move a file and rename it</span></span>  
  
- <span data-ttu-id="e6d74-110">Use el método `MoveFile` para mover el archivo, y especifique el nombre y la ubicación del archivo de origen, la ubicación de destino y el nuevo nombre en la ubicación de destino.</span><span class="sxs-lookup"><span data-stu-id="e6d74-110">Use the `MoveFile` method to move the file, specifying the source file name and location, the target location, and the new name at the target location.</span></span> <span data-ttu-id="e6d74-111">En este ejemplo se mueve el archivo denominado `test.txt` de `TestDir1` a `TestDir2` y su nombre se cambia a `nexttest.txt`.</span><span class="sxs-lookup"><span data-stu-id="e6d74-111">This example moves the file named `test.txt` from `TestDir1` to `TestDir2` and renames it `nexttest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#25)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e6d74-112">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="e6d74-112">Robust Programming</span></span>  

 <span data-ttu-id="e6d74-113">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="e6d74-113">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="e6d74-114">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="e6d74-115">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="e6d74-116">`destinationFileName` es `Nothing` o una cadena vacía (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-116">`destinationFileName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="e6d74-117">El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-117">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="e6d74-118">La ruta de acceso combinada apunta a un directorio existente, el archivo de destino existe y `overwrite` está establecido en `False`, un archivo del directorio de destino con el mismo nombre está en uso o el usuario no tiene permisos suficientes para acceder al archivo (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-118">The combined path points to an existing directory, the destination file exists and `overwrite` is set to `False`, a file in the target directory with the same name is in use, or the user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="e6d74-119">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="e6d74-120">`showUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException`y el usuario canceló la operación o se produjo un error de E/S no especificado (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-120">`showUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and either the user has cancelled the operation or an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="e6d74-121">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="e6d74-122">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="e6d74-123">El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="e6d74-123">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d74-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6d74-124">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>
- [<span data-ttu-id="e6d74-125">Cambiar el nombre de un archivo</span><span class="sxs-lookup"><span data-stu-id="e6d74-125">How to: Rename a File</span></span>](how-to-rename-a-file.md)
- [<span data-ttu-id="e6d74-126">Crear una copia de un archivo en un directorio diferente</span><span class="sxs-lookup"><span data-stu-id="e6d74-126">How to: Create a Copy of a File in a Different Directory</span></span>](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [<span data-ttu-id="e6d74-127">Analizar rutas de acceso a archivos</span><span class="sxs-lookup"><span data-stu-id="e6d74-127">How to: Parse File Paths</span></span>](how-to-parse-file-paths.md)
