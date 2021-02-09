---
description: 'Más información acerca de: Procedimiento: para analizar rutas de acceso a archivos en Visual Basic'
title: Procedimiento para analizar rutas de acceso a archivos
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], parsing [Visual Basic]
- parsing, file paths [Visual Basic]
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
ms.openlocfilehash: dff423679324974d64c613a292c253d99d668c7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797502"
---
# <a name="how-to-parse-file-paths-in-visual-basic"></a><span data-ttu-id="71027-103">Cómo: Analizar rutas de acceso a archivos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71027-103">How to: Parse File Paths in Visual Basic</span></span>

<span data-ttu-id="71027-104">El objeto <xref:Microsoft.VisualBasic.FileIO.FileSystem> ofrece una serie de métodos útiles al analizar rutas de acceso a archivos.</span><span class="sxs-lookup"><span data-stu-id="71027-104">The <xref:Microsoft.VisualBasic.FileIO.FileSystem> object offers a number of useful methods when parsing file paths.</span></span>  
  
- <span data-ttu-id="71027-105">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> toma dos rutas de acceso y devuelve una ruta de acceso combinada con el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="71027-105">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A> method takes two paths and returns a properly formatted combined path.</span></span>  
  
- <span data-ttu-id="71027-106">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> devuelve la ruta de acceso absoluta del elemento primario de la ruta de acceso proporcionada.</span><span class="sxs-lookup"><span data-stu-id="71027-106">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A> method returns the absolute path of the parent of the provided path.</span></span>  
  
- <span data-ttu-id="71027-107">El método <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> devuelve un objeto <xref:System.IO.FileInfo> que se puede consultar para determinar las propiedades del archivo, como el nombre y la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="71027-107">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method returns a <xref:System.IO.FileInfo> object that can be queried to determine the file's properties, such as its name and path.</span></span>  
  
 <span data-ttu-id="71027-108">No tome ninguna decisión sobre el contenido del archivo basándose en la extensión del nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="71027-108">Do not make decisions about the contents of the file based on the file name extension.</span></span> <span data-ttu-id="71027-109">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="71027-109">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
### <a name="to-determine-a-files-name-and-path"></a><span data-ttu-id="71027-110">Para determinar el nombre y la ruta de acceso de un archivo</span><span class="sxs-lookup"><span data-stu-id="71027-110">To determine a file's name and path</span></span>  
  
- <span data-ttu-id="71027-111">Use las propiedades <xref:System.IO.FileInfo.DirectoryName%2A> y <xref:System.IO.FileInfo.Name%2A> del objeto <xref:System.IO.FileInfo> para determinar el nombre y la ruta de acceso de un archivo.</span><span class="sxs-lookup"><span data-stu-id="71027-111">Use the <xref:System.IO.FileInfo.DirectoryName%2A> and <xref:System.IO.FileInfo.Name%2A> properties of the <xref:System.IO.FileInfo> object to determine a file's name and path.</span></span> <span data-ttu-id="71027-112">Este ejemplo determina el nombre y la ruta de acceso, y los muestra.</span><span class="sxs-lookup"><span data-stu-id="71027-112">This example determines the name and path and displays them.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#54)]  
  
### <a name="to-combine-a-files-name-and-directory-to-create-the-full-path"></a><span data-ttu-id="71027-113">Para combinar el nombre y el directorio de un archivo para crear la ruta de acceso completa</span><span class="sxs-lookup"><span data-stu-id="71027-113">To combine a file's name and directory to create the full path</span></span>  
  
- <span data-ttu-id="71027-114">Use el método `CombinePath` , y proporcione el directorio y el nombre.</span><span class="sxs-lookup"><span data-stu-id="71027-114">Use the `CombinePath` method, supplying the directory and name.</span></span> <span data-ttu-id="71027-115">En este ejemplo se toman las cadenas `folderPath` y `fileName` creadas en el ejemplo anterior, se combinan y se muestra el resultado.</span><span class="sxs-lookup"><span data-stu-id="71027-115">This example takes the strings `folderPath` and `fileName` created in the previous example, combines them, and displays the result.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="71027-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="71027-116">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>
- <xref:System.IO.FileInfo>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>
- [<span data-ttu-id="71027-117">Procedimiento para obtener la colección de archivos de un directorio</span><span class="sxs-lookup"><span data-stu-id="71027-117">How to: Get the Collection of Files in a Directory</span></span>](how-to-get-the-collection-of-files-in-a-directory.md)
