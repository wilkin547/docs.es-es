---
title: "Cómo: Analizar rutas de acceso a archivos en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 913fe45cf6fc7afdc6e0f31e028bc18808cecf89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="c791f-102">Cómo: Analizar rutas de acceso a archivos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c791f-102">How to: Parse File Paths in Visual Basic</span></span>
<span data-ttu-id="c791f-103">El objeto <xref:Microsoft.VisualBasic.FileIO.FileSystem> ofrece una serie de métodos útiles al analizar rutas de acceso a archivos.</span><span class="sxs-lookup"><span data-stu-id="c791f-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
-   <span data-ttu-id="c791f-104">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> toma dos rutas de acceso y devuelve una ruta de acceso combinada con el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="c791f-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
-   <span data-ttu-id="c791f-105">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> devuelve la ruta de acceso absoluta del elemento primario de la ruta de acceso proporcionada.</span><span class="sxs-lookup"><span data-stu-id="c791f-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
-   <span data-ttu-id="c791f-106">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> devuelve un objeto <xref:System.IO.FileInfo> que se puede consultar para determinar las propiedades del archivo, como el nombre y la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c791f-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="c791f-107">No tome ninguna decisión sobre el contenido del archivo basándose en la extensión del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="c791f-107">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="c791f-108">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c791f-108">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="c791f-109">Para determinar el nombre y la ruta de acceso de un archivo</span><span class="sxs-lookup"><span data-stu-id="c791f-109">To determine a file's name and path</span></span>  
  
-   <span data-ttu-id="c791f-110">Use las propiedades <xref:System.IO.FileInfo.DirectoryName%2A> y <xref:System.IO.FileInfo.Name%2A> del objeto <xref:System.IO.FileInfo> para determinar el nombre y la ruta de acceso de un archivo.</span><span class="sxs-lookup"><span data-stu-id="c791f-110">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="c791f-111">Este ejemplo determina el nombre y la ruta de acceso, y los muestra.</span><span class="sxs-lookup"><span data-stu-id="c791f-111">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="c791f-112">Para combinar el nombre y el directorio de un archivo para crear la ruta de acceso completa</span><span class="sxs-lookup"><span data-stu-id="c791f-112">To combine a file's name and directory to create the full path</span></span>  
  
-   <span data-ttu-id="c791f-113">Use el método `CombinePath` , y proporcione el directorio y el nombre.</span><span class="sxs-lookup"><span data-stu-id="c791f-113">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="c791f-114">En este ejemplo se toman las cadenas `folderPath` y `fileName` creadas en el ejemplo anterior, se combinan y se muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="c791f-114">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c791f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c791f-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>  
 <xref:System.IO.FileInfo>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>  
 [<span data-ttu-id="c791f-116">Obtener la colección de archivos de un directorio</span><span class="sxs-lookup"><span data-stu-id="c791f-116">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
