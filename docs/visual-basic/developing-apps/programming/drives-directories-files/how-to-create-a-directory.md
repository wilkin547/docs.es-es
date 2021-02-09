---
description: 'Más información acerca de: Procedimiento: para crear un directorio en Visual Basic'
title: Procedimiento para crear un directorio
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: 39a0f1b2f482b27b6f207f0ca8a498db198e9d59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797606"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a><span data-ttu-id="aca92-103">Cómo: Crear un directorio en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aca92-103">How to: Create a Directory in Visual Basic</span></span>

<span data-ttu-id="aca92-104">Use el método `CreateDirectory` del objeto `My.Computer.FileSystem` para crear directorios.</span><span class="sxs-lookup"><span data-stu-id="aca92-104">Use the `CreateDirectory` method of the `My.Computer.FileSystem` object to create directories.</span></span>  
  
 <span data-ttu-id="aca92-105">Si el directorio ya existe, no se produce ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="aca92-105">If the directory already exists, no exception is thrown.</span></span>  
  
### <a name="to-create-a-directory"></a><span data-ttu-id="aca92-106">Para crear un directorio</span><span class="sxs-lookup"><span data-stu-id="aca92-106">To create a directory</span></span>  
  
- <span data-ttu-id="aca92-107">Use el método `CreateDirectory` especificando la ruta de acceso completa de la ubicación donde se debe crear el directorio.</span><span class="sxs-lookup"><span data-stu-id="aca92-107">Use the `CreateDirectory` method by specifying the full path of the location where the directory should be created.</span></span> <span data-ttu-id="aca92-108">Este ejemplo crea el directorio `NewDirectory` en `C:\Documents and Settings\All Users\Documents`.</span><span class="sxs-lookup"><span data-stu-id="aca92-108">This example creates the directory `NewDirectory` in `C:\Documents and Settings\All Users\Documents`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="aca92-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="aca92-109">Robust Programming</span></span>  

 <span data-ttu-id="aca92-110">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="aca92-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="aca92-111">El nombre del directorio es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="aca92-111">The directory name is malformed.</span></span> <span data-ttu-id="aca92-112">Por ejemplo, contiene caracteres no válidos o solo tiene espacios en blanco (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="aca92-112">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="aca92-113">El directorio principal del directorio que se va a crear es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="aca92-113">The parent directory of the directory to be created is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="aca92-114">El nombre del directorio es `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="aca92-114">The directory name is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="aca92-115">El nombre del directorio es demasiado largo (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="aca92-115">The directory name is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="aca92-116">El nombre del directorio son dos puntos ":" (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="aca92-116">The directory name is a colon ":" (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="aca92-117">El usuario no tiene permiso para crear el directorio (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="aca92-117">The user does not have permission to create the directory (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="aca92-118">El usuario no tiene permisos en una situación de confianza parcial (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="aca92-118">The user lacks permissions in a partial-trust situation (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca92-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aca92-119">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [<span data-ttu-id="aca92-120">Creación, eliminación y movimiento de archivos y directorios</span><span class="sxs-lookup"><span data-stu-id="aca92-120">Creating, Deleting, and Moving Files and Directories</span></span>](creating-deleting-and-moving-files-and-directories.md)
