---
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935231"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="5c669-102">Número o nombre de archivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="5c669-102">Bad file name or number</span></span>
<span data-ttu-id="5c669-103">Se produjo un error al intentar obtener acceso al archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5c669-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="5c669-104">Entre las posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="5c669-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="5c669-105">La instrucción hace referencia a un archivo con un nombre de archivo o un número que no se especificó en el `FileOpen` instrucción o que se especificó en un `FileOpen` instrucción pero era posteriormente cerrado.</span><span class="sxs-lookup"><span data-stu-id="5c669-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="5c669-106">Una instrucción hace referencia a un archivo con un número que está fuera del intervalo del número de archivos.</span><span class="sxs-lookup"><span data-stu-id="5c669-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="5c669-107">Una instrucción hace referencia a un nombre de archivo o un número que no es válido.</span><span class="sxs-lookup"><span data-stu-id="5c669-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5c669-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5c669-108">To correct this error</span></span>  
  
1. <span data-ttu-id="5c669-109">Asegúrese de que se especifica el nombre de archivo en un `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5c669-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="5c669-110">Tenga en cuenta que si se ha invocado el `FileClose` instrucción sin argumentos, puede haber accidentalmente cerrado todos los archivos abiertos.</span><span class="sxs-lookup"><span data-stu-id="5c669-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="5c669-111">Si el código genera números de archivo de forma algorítmica, asegúrese de que los números son válidos.</span><span class="sxs-lookup"><span data-stu-id="5c669-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="5c669-112">Compruebe los nombres de archivo para asegurarse de que se ajusten a las convenciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5c669-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c669-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c669-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="5c669-114">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c669-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
