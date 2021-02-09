---
description: 'Más información acerca de: Procedimiento: para eliminar un archivo en Visual Basic'
title: Procedimiento para eliminar un archivo
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 49bfe2e4a0d9114e2f653ae14dab303e35e2dfeb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797580"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="e0ade-103">Cómo: Eliminar un archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e0ade-103">How to: Delete a File in Visual Basic</span></span>

<span data-ttu-id="e0ade-104">El método `DeleteFile` del objeto `My.Computer.FileSystem` permite eliminar un archivo.</span><span class="sxs-lookup"><span data-stu-id="e0ade-104">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="e0ade-105">Entre las opciones que ofrece se encuentran: enviar el archivo eliminado a la **Papelera de reciclaje**, pedir al usuario que confirme la eliminación del archivo o qué hacer si el usuario cancela la operación.</span><span class="sxs-lookup"><span data-stu-id="e0ade-105">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="e0ade-106">Para eliminar un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="e0ade-106">To delete a text file</span></span>  
  
- <span data-ttu-id="e0ade-107">Use el método `DeleteFile` para eliminar el archivo.</span><span class="sxs-lookup"><span data-stu-id="e0ade-107">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="e0ade-108">En el código siguiente se muestra cómo eliminar el archivo denominado `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="e0ade-108">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="e0ade-109">Para eliminar un archivo de texto y pedirle al usuario que confirme que se debe eliminar el archivo</span><span class="sxs-lookup"><span data-stu-id="e0ade-109">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
- <span data-ttu-id="e0ade-110">Use el método `DeleteFile` para eliminar el archivo, estableciendo `showUI` en `AllDialogs`.</span><span class="sxs-lookup"><span data-stu-id="e0ade-110">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="e0ade-111">En el código siguiente se muestra cómo eliminar el archivo denominado `test.txt` y se permite al usuario confirmar la eliminación del archivo.</span><span class="sxs-lookup"><span data-stu-id="e0ade-111">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="e0ade-112">Para eliminar un archivo de texto y enviarlo a la Papelera de reciclaje</span><span class="sxs-lookup"><span data-stu-id="e0ade-112">To delete a text file and send it to the Recycle Bin</span></span>  
  
- <span data-ttu-id="e0ade-113">Use el método `DeleteFile` para eliminar el archivo, especificando `SendToRecycleBin` para el parámetro `recycle`.</span><span class="sxs-lookup"><span data-stu-id="e0ade-113">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="e0ade-114">En el código siguiente se muestra cómo eliminar el archivo denominado `test.txt` y enviarlo a la **Papelera de reciclaje**.</span><span class="sxs-lookup"><span data-stu-id="e0ade-114">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a><span data-ttu-id="e0ade-115">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="e0ade-115">Robust Programming</span></span>  

 <span data-ttu-id="e0ade-116">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="e0ade-116">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="e0ade-117">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="e0ade-118">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="e0ade-119">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="e0ade-120">Un nombre de archivo o de carpeta de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-120">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="e0ade-121">El archivo está en uso (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-121">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="e0ade-122">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="e0ade-123">El archivo no existe (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-123">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="e0ade-124">El usuario no tiene permiso para eliminar el archivo o el archivo es de solo lectura (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-124">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="e0ade-125">Existe una situación de confianza parcial en la que el usuario no tiene suficientes permisos (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-125">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="e0ade-126">El usuario canceló la operación y `onUserCancel` está establecido en `ThrowException` (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="e0ade-126">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ade-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0ade-127">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [<span data-ttu-id="e0ade-128">Procedimiento para obtener la colección de archivos de un directorio</span><span class="sxs-lookup"><span data-stu-id="e0ade-128">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
