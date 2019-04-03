---
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: b6da1031b60a4cd73c53588cf18992797c3fddab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839072"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="a66ea-102">Número o nombre de archivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="a66ea-102">Bad file name or number</span></span>
<span data-ttu-id="a66ea-103">Se produjo un error al intentar obtener acceso al archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="a66ea-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="a66ea-104">Entre las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="a66ea-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="a66ea-105">La instrucción hace referencia a un archivo con un nombre de archivo o un número que no se especificó en el `FileOpen` instrucción o que se especificó en un `FileOpen` instrucción pero era posteriormente cerrado.</span><span class="sxs-lookup"><span data-stu-id="a66ea-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
-   <span data-ttu-id="a66ea-106">Una instrucción hace referencia a un archivo con un número que está fuera del intervalo del número de archivos.</span><span class="sxs-lookup"><span data-stu-id="a66ea-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
-   <span data-ttu-id="a66ea-107">Una instrucción hace referencia a un nombre de archivo o un número que no es válido.</span><span class="sxs-lookup"><span data-stu-id="a66ea-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a66ea-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a66ea-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="a66ea-109">Asegúrese de que se especifica el nombre de archivo en un `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a66ea-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="a66ea-110">Tenga en cuenta que si se ha invocado el `FileClose` instrucción sin argumentos, puede haber accidentalmente cerrado todos los archivos abiertos.</span><span class="sxs-lookup"><span data-stu-id="a66ea-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2.  <span data-ttu-id="a66ea-111">Si el código genera números de archivo de forma algorítmica, asegúrese de que los números son válidos.</span><span class="sxs-lookup"><span data-stu-id="a66ea-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3.  <span data-ttu-id="a66ea-112">Compruebe los nombres de archivo para asegurarse de que se ajusten a las convenciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a66ea-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66ea-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a66ea-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="a66ea-114">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a66ea-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
