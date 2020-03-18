---
title: 'Cómo: Crear una copia de un archivo en un directorio diferente'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
ms.openlocfilehash: e9a14e1f3743979548b92a3db653d09a470a1875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348839"
---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a><span data-ttu-id="15e70-102">Cómo: Crear una copia de un archivo en un directorio diferente en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15e70-102">How to: Create a Copy of a File in a Different Directory in Visual Basic</span></span>

<span data-ttu-id="15e70-103">El método `My.Computer.FileSystem.CopyFile` le permite copiar archivos.</span><span class="sxs-lookup"><span data-stu-id="15e70-103">The `My.Computer.FileSystem.CopyFile` method allows you to copy files.</span></span> <span data-ttu-id="15e70-104">Sus parámetros proporcionan la capacidad de sobrescribir archivos existentes, cambiar el nombre al archivo, mostrar el progreso de la operación y permitir al usuario cancelar la operación.</span><span class="sxs-lookup"><span data-stu-id="15e70-104">Its parameters provide the ability to overwrite existing files, rename the file, show the progress of the operation, and allow the user to cancel the operation.</span></span>  
  
### <a name="to-copy-a-text-file-to-another-folder"></a><span data-ttu-id="15e70-105">Para copiar un archivo de texto en otra carpeta</span><span class="sxs-lookup"><span data-stu-id="15e70-105">To copy a text file to another folder</span></span>  
  
- <span data-ttu-id="15e70-106">Use el método `CopyFile` para copiar un archivo, especificando un archivo de origen y el directorio de destino.</span><span class="sxs-lookup"><span data-stu-id="15e70-106">Use the `CopyFile` method to copy a file, specifying a source file and the target directory.</span></span> <span data-ttu-id="15e70-107">El parámetro `overwrite` le permite especificar si se deben sobrescribir los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="15e70-107">The `overwrite` parameter allows you to specify whether or not to overwrite existing files.</span></span> <span data-ttu-id="15e70-108">Los ejemplos de código siguientes muestran cómo usar `CopyFile`.</span><span class="sxs-lookup"><span data-stu-id="15e70-108">The following code examples demonstrate how to use `CopyFile`.</span></span>  
  
     [!code-vb[VbFileIOMisc#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#24)]  
  
## <a name="robust-programming"></a><span data-ttu-id="15e70-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="15e70-109">Robust Programming</span></span>  

 <span data-ttu-id="15e70-110">Las condiciones siguientes pueden provocar que se produzca una excepción:</span><span class="sxs-lookup"><span data-stu-id="15e70-110">The following conditions may cause an exception to be thrown:</span></span>  
  
- <span data-ttu-id="15e70-111">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-111">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="15e70-112">El sistema no pudo recuperar la ruta de acceso absoluta (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-112">The system could not retrieve the absolute path (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="15e70-113">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="15e70-114">El archivo de origen no es válido o no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-114">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="15e70-115">La ruta de acceso combinada apunta a un directorio existente (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-115">The combined path points to an existing directory (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="15e70-116">El archivo de destino existe y `overwrite` está establecido en `False` (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-116">The destination file exists and `overwrite` is set to `False` (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="15e70-117">El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-117">The user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="15e70-118">Hay un archivo en uso con el mismo nombre en la carpeta de destino (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-118">A file in the target folder with the same name is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="15e70-119">Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="15e70-120">`ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y el usuario ha cancelado la operación (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-120">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and the user has cancelled the operation (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="15e70-121">`ShowUI` está establecido en `True`, `onUserCancel` está establecido en `ThrowException` y se produce un error de E/S no especificado (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-121">`ShowUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
- <span data-ttu-id="15e70-122">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-122">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="15e70-123">El usuario no tiene el permiso necesario (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-123">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="15e70-124">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="15e70-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e70-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="15e70-125">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- [<span data-ttu-id="15e70-126">Copiar archivos con un modelo específico en un directorio</span><span class="sxs-lookup"><span data-stu-id="15e70-126">How to: Copy Files with a Specific Pattern to a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)
- [<span data-ttu-id="15e70-127">Crear una copia de un archivo en el mismo directorio</span><span class="sxs-lookup"><span data-stu-id="15e70-127">How to: Create a Copy of a File in the Same Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)
- [<span data-ttu-id="15e70-128">Copiar un directorio en otro directorio</span><span class="sxs-lookup"><span data-stu-id="15e70-128">How to: Copy a Directory to Another Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)
- [<span data-ttu-id="15e70-129">Cambiar el nombre de un archivo</span><span class="sxs-lookup"><span data-stu-id="15e70-129">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
