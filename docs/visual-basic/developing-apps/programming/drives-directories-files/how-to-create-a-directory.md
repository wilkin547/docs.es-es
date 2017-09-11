---
title: "Cómo: Crear un directorio en Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a45a785916b480dcee6e36fd295390266eaa0a0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="bdf7b-102">Cómo: Crear un directorio en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdf7b-102">How to: Create a Directory in Visual Basic</span></span>
<span data-ttu-id="bdf7b-103">Use el método `CreateDirectory` del objeto `My.Computer.FileSystem` para crear directorios.</span><span class="sxs-lookup"><span data-stu-id="bdf7b-103">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="bdf7b-104">Si el directorio ya existe, no se produce ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="bdf7b-104">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="bdf7b-105">Para crear un directorio</span><span class="sxs-lookup"><span data-stu-id="bdf7b-105">To create a directory</span></span>  
  
-   <span data-ttu-id="bdf7b-106">Use el método `CreateDirectory` especificando la ruta de acceso completa de la ubicación donde se debe crear el directorio.</span><span class="sxs-lookup"><span data-stu-id="bdf7b-106">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="bdf7b-107">Este ejemplo crea el directorio `NewDirectory` en `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="bdf7b-107">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     <span data-ttu-id="bdf7b-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bdf7b-108">[!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bdf7b-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="bdf7b-109">Robust Programming</span></span>  
 <span data-ttu-id="bdf7b-110">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="bdf7b-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="bdf7b-111">El nombre del directorio es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="bdf7b-111">The directory name is malformed.</span></span> <span data-ttu-id="bdf7b-112">Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="bdf7b-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="bdf7b-113">El directorio principal del directorio que se va a crear es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="bdf7b-113">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="bdf7b-114">El nombre del directorio es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="bdf7b-114">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="bdf7b-115">El nombre del directorio es demasiado largo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="bdf7b-115">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="bdf7b-116">El nombre del directorio son dos puntos ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="bdf7b-116">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="bdf7b-117">El usuario no tiene permiso para crear el directorio (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="bdf7b-117">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="bdf7b-118">El usuario no tiene permisos en una situación de confianza parcial (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="bdf7b-118">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf7b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdf7b-119">See Also</span></span>  
 <span data-ttu-id="bdf7b-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="bdf7b-120"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A></span></span>   
 [<span data-ttu-id="bdf7b-121">Creación, eliminación y movimiento de archivos y directorios</span><span class="sxs-lookup"><span data-stu-id="bdf7b-121">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)

