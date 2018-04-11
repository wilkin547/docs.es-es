---
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="53387-102">Número o nombre de archivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="53387-102">Bad file name or number</span></span>
<span data-ttu-id="53387-103">Se produjo un error al intentar obtener acceso al archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="53387-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="53387-104">Entre las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="53387-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="53387-105">Una instrucción hace referencia a un archivo con un nombre de archivo o un número que no se especificó en el `FileOpen` instrucción o que se especificó en un `FileOpen` instrucción pero era posteriormente cerrado.</span><span class="sxs-lookup"><span data-stu-id="53387-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="53387-106">Una instrucción hace referencia a un archivo con un número que está fuera del intervalo del número de archivos.</span><span class="sxs-lookup"><span data-stu-id="53387-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="53387-107">Una instrucción hace referencia a un nombre de archivo o un número que no es válido.</span><span class="sxs-lookup"><span data-stu-id="53387-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="53387-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="53387-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="53387-109">Asegúrese de que se especifica el nombre de archivo en un `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="53387-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="53387-110">Tenga en cuenta que si invoca el `FileClose` instrucción sin argumentos, puede haber accidentalmente cerrado todos los archivos abiertos.</span><span class="sxs-lookup"><span data-stu-id="53387-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="53387-111">Si el código está generando números de los archivos de forma algorítmica, asegúrese de que los números son válidos.</span><span class="sxs-lookup"><span data-stu-id="53387-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="53387-112">Compruebe los nombres de archivo para asegurarse de que se ajusten a las convenciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="53387-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53387-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="53387-113">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [<span data-ttu-id="53387-114">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53387-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
