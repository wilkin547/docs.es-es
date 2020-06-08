---
title: 'Cómo: Crear una copia de un archivo en el mismo directorio'
ms.date: 07/20/2015
f1_keywords:
- File.Copy
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: b2fdda86-e666-42c2-9706-9527e9fa68ff
ms.openlocfilehash: 741f0c80ba268369ebdd598460e9d5fa13d09571
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401685"
---
# <a name="how-to-create-a-copy-of-a-file-in-the-same-directory-in-visual-basic"></a><span data-ttu-id="6cdc6-102">Cómo: Crear una copia de un archivo en el mismo directorio en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6cdc6-102">How to: Create a Copy of a File in the Same Directory in Visual Basic</span></span>

<span data-ttu-id="6cdc6-103">Use el método `My.Computer.FileSystem.CopyFile` para copiar archivos.</span><span class="sxs-lookup"><span data-stu-id="6cdc6-103">Use the `My.Computer.FileSystem.CopyFile` method to copy files.</span></span> <span data-ttu-id="6cdc6-104">Con los parámetros puede sobrescribir archivos existentes, cambiar el nombre del archivo, mostrar el progreso de la operación y permitir al usuario cancelar la operación.</span><span class="sxs-lookup"><span data-stu-id="6cdc6-104">The parameters allow you to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder"></a><span data-ttu-id="6cdc6-105">Para crear una copia de un archivo en la misma carpeta</span><span class="sxs-lookup"><span data-stu-id="6cdc6-105">To create a copy of a file in the same folder</span></span>  
  
- <span data-ttu-id="6cdc6-106">Use el método `CopyFile`, proporcionando el archivo de destino y la ubicación.</span><span class="sxs-lookup"><span data-stu-id="6cdc6-106">Use the `CopyFile` method, supplying the target file and the location.</span></span> <span data-ttu-id="6cdc6-107">En el ejemplo siguiente se crea una copia de `test.txt` llamada `test2.txt`.</span><span class="sxs-lookup"><span data-stu-id="6cdc6-107">The following example creates a copy of `test.txt` called `test2.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#51)]  
  
### <a name="to-create-a-copy-of-a-file-in-the-same-folder-overwriting-existing-files"></a><span data-ttu-id="6cdc6-108">Para crear una copia de un archivo en la misma carpeta, sobrescribiendo archivos existentes</span><span class="sxs-lookup"><span data-stu-id="6cdc6-108">To create a copy of a file in the same folder, overwriting existing files</span></span>  
  
- <span data-ttu-id="6cdc6-109">Use el método `CopyFile`; indique el archivo de destino y la ubicación, y establezca `overwrite` en `True`.</span><span class="sxs-lookup"><span data-stu-id="6cdc6-109">Use the `CopyFile` method, supplying the target file and location, and setting `overwrite` to `True`.</span></span> <span data-ttu-id="6cdc6-110">En el ejemplo siguiente se crea una copia de `test.txt` llamada `test2.txt` y sobrescribe cualquier archivo existente con dicho nombre.</span><span class="sxs-lookup"><span data-stu-id="6cdc6-110">The following example creates a copy of `test.txt` called `test2.txt` and overwrites any existing files by that name.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#52)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6cdc6-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="6cdc6-111">Robust Programming</span></span>  

 <span data-ttu-id="6cdc6-112">Las condiciones siguientes pueden provocar que se produzca una excepción:</span><span class="sxs-lookup"><span data-stu-id="6cdc6-112">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="6cdc6-113">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="6cdc6-114">El sistema no pudo recuperar la ruta de acceso absoluta (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-114">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="6cdc6-115">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="6cdc6-116">El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-116">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="6cdc6-117">La ruta de acceso combinada apunta a un directorio existente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-117">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="6cdc6-118">El archivo de destino existe y `overwrite` está establecido en `False` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-118">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="6cdc6-119">El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-119">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="6cdc6-120">Hay un archivo en uso con el mismo nombre en la carpeta de destino (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-120">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="6cdc6-121">Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-121">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="6cdc6-122">`ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y el usuario ha cancelado la operación (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-122">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="6cdc6-123">`ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y se produce un error de E/S no especificado (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-123">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="6cdc6-124">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-124">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="6cdc6-125">El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-125">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="6cdc6-126">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="6cdc6-126">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cdc6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cdc6-127">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="6cdc6-128">Copiar archivos con un modelo específico en un directorio</span><span class="sxs-lookup"><span data-stu-id="6cdc6-128">How to: Copy Files with a Specific Pattern to a Directory</span></span>](how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="6cdc6-129">Crear una copia de un archivo en un directorio diferente</span><span class="sxs-lookup"><span data-stu-id="6cdc6-129">How to: Create a Copy of a File in a Different Directory</span></span>](how-to-create-a-copy-of-a-file-in-a-different-directory.md)
- [<span data-ttu-id="6cdc6-130">Copiar un directorio en otro directorio</span><span class="sxs-lookup"><span data-stu-id="6cdc6-130">How to: Copy a Directory to Another Directory</span></span>](how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="6cdc6-131">Cambiar el nombre de un archivo</span><span class="sxs-lookup"><span data-stu-id="6cdc6-131">How to: Rename a File</span></span>](how-to-rename-a-file.md)
