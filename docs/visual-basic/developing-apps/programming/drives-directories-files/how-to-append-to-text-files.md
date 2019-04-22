---
title: Procedimiento para anexar a archivos de texto en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
ms.openlocfilehash: 83f34e9cb669e8d2e841b13875b5237626164dd9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819845"
---
# <a name="how-to-append-to-text-files-in-visual-basic"></a><span data-ttu-id="a9c27-102">Procedimiento para anexar a archivos de texto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9c27-102">How to: Append to Text Files in Visual Basic</span></span>
<span data-ttu-id="a9c27-103">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> se puede usar para anexar datos a un archivo de texto especificando que el parámetro `append` está establecido en `True`.</span><span class="sxs-lookup"><span data-stu-id="a9c27-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to append to a text file by specifying that the `append` parameter is set to `True`.</span></span>  
  
### <a name="to-append-to-a-text-file"></a><span data-ttu-id="a9c27-104">Para anexar a un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="a9c27-104">To append to a text file</span></span>  
  
-   <span data-ttu-id="a9c27-105">Use el método `WriteAllText`, especificando el archivo de destino y la cadena que se va a anexar y estableciendo el parámetro `append` en `True`.</span><span class="sxs-lookup"><span data-stu-id="a9c27-105">Use the `WriteAllText` method, specifying the target file and string to be appended and setting the `append` parameter to `True`.</span></span>  
  
     <span data-ttu-id="a9c27-106">En este ejemplo se escribe la cadena `"This is a test string."` en el archivo `Testfile.txt`.</span><span class="sxs-lookup"><span data-stu-id="a9c27-106">This example writes the string `"This is a test string."` to the file named `Testfile.txt`.</span></span>  
  
     [!code-vb[VbFileIOWrite#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a9c27-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a9c27-107">Robust Programming</span></span>  
 <span data-ttu-id="a9c27-108">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="a9c27-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="a9c27-109">La ruta de acceso no es válida por una de las siguientes razones: es una cadena de longitud cero, solo contiene un espacio en blanco, contiene caracteres no válidos o es una ruta de acceso de dispositivo (empieza por \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="a9c27-109">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="a9c27-110">La ruta de acceso no es válida porque es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="a9c27-110">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="a9c27-111">`File` apunta a una ruta de acceso que no existe (<xref:System.IO.FileNotFoundException> o <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="a9c27-111">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="a9c27-112">El archivo está en uso por otro proceso o hay un error de E/S (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="a9c27-112">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="a9c27-113">La ruta supera la longitud máxima definida por el sistema (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="a9c27-113">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="a9c27-114">Un nombre de archivo o de directorio de la ruta de acceso contiene un signo de dos puntos (:) o tiene un formato no válido (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="a9c27-114">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="a9c27-115">El usuario no tiene los permisos necesarios para ver la ruta de acceso (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="a9c27-115">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c27-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9c27-116">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [<span data-ttu-id="a9c27-117">Escritura en archivos</span><span class="sxs-lookup"><span data-stu-id="a9c27-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
