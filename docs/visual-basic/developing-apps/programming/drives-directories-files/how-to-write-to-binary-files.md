---
title: 'Cómo: Escribir en archivos binarios en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 59edf84c1addd287eb1d1615c46258f329b1c7e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587207"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a><span data-ttu-id="89882-102">Cómo: Escribir en archivos binarios en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="89882-102">How to: Write to Binary Files in Visual Basic</span></span>
<span data-ttu-id="89882-103">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> escribe datos en un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="89882-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> method writes data to a binary file.</span></span> <span data-ttu-id="89882-104">Si el parámetro `append` es `True`, anexará los datos al archivo; de lo contrario se sobrescriben los datos existentes en el archivo.</span><span class="sxs-lookup"><span data-stu-id="89882-104">If the `append` parameter is `True`, it will append the data to the file; otherwise data in the file is overwritten.</span></span>  
  
 <span data-ttu-id="89882-105">Si la ruta de acceso especificada excepto el nombre de archivo no es válida, se producirá una excepción <xref:System.IO.DirectoryNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="89882-105">If the specified path excluding the file name is not valid, a <xref:System.IO.DirectoryNotFoundException> exception will be thrown.</span></span> <span data-ttu-id="89882-106">Si la ruta de acceso es válida pero el archivo no existe, se creará el archivo.</span><span class="sxs-lookup"><span data-stu-id="89882-106">If the path is valid but the file does not exist, the file will be created.</span></span>  
  
### <a name="to-write-to-a-binary-file"></a><span data-ttu-id="89882-107">Para escribir en un archivo binario</span><span class="sxs-lookup"><span data-stu-id="89882-107">To write to a binary file</span></span>  
  
-   <span data-ttu-id="89882-108">Use el método `WriteAllBytes`, proporcionando la ruta de acceso del archivo, su nombre y los bytes que se deben escribir.</span><span class="sxs-lookup"><span data-stu-id="89882-108">Use the `WriteAllBytes` method, supplying the file path and name and the bytes to be written.</span></span> <span data-ttu-id="89882-109">En este ejemplo se anexa la matriz de datos `CustomerData` al archivo denominado `CollectedData.dat`.</span><span class="sxs-lookup"><span data-stu-id="89882-109">This example appends the data array `CustomerData` to the file named `CollectedData.dat`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="89882-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="89882-110">Robust Programming</span></span>  
 <span data-ttu-id="89882-111">Las condiciones siguientes pueden crear una excepción:</span><span class="sxs-lookup"><span data-stu-id="89882-111">The following conditions may create an exception:</span></span>  
  
-   <span data-ttu-id="89882-112">La ruta de acceso no es válida por uno de los siguientes motivos: es una cadena de longitud cero, contiene solo espacios en blanco, o contiene caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="89882-112">The path is not valid for one of the following reasons: it is a zero-length string; it contains only white space; or it contains invalid characters.</span></span> <span data-ttu-id="89882-113">(<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="89882-113">(<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="89882-114">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="89882-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="89882-115">`File` apunta a una ruta de acceso que no existe (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="89882-115">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="89882-116">El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="89882-116">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="89882-117">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="89882-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="89882-118">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="89882-118">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="89882-119">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="89882-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89882-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="89882-120">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>  
 [<span data-ttu-id="89882-121">Escribir texto en archivos</span><span class="sxs-lookup"><span data-stu-id="89882-121">How to: Write Text to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
