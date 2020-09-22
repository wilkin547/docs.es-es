---
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: d57a9e78e6ae179d3050e5a92399ca731fa16ba7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874904"
---
# <a name="bad-file-name-or-number"></a><span data-ttu-id="87b23-102">Número o nombre de archivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="87b23-102">Bad file name or number</span></span>

<span data-ttu-id="87b23-103">Error al intentar obtener acceso al archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="87b23-103">An error occurred while trying to access the specified file.</span></span> <span data-ttu-id="87b23-104">Entre las posibles causas de este error se encuentran:</span><span class="sxs-lookup"><span data-stu-id="87b23-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="87b23-105">Una instrucción hace referencia a un archivo con un nombre o número de archivo que no se especificó en la `FileOpen` instrucción o que se especificó en una `FileOpen` instrucción pero que se cerró posteriormente.</span><span class="sxs-lookup"><span data-stu-id="87b23-105">A statement refers to a file with a file name or number that was not specified in the `FileOpen` statement or that was specified in a `FileOpen` statement but was subsequently closed.</span></span>  
  
- <span data-ttu-id="87b23-106">Una instrucción hace referencia a un archivo con un número que está fuera del intervalo de números de archivo.</span><span class="sxs-lookup"><span data-stu-id="87b23-106">A statement refers to a file with a number that is out of the range of file numbers.</span></span>  
  
- <span data-ttu-id="87b23-107">Una instrucción hace referencia a un nombre de archivo o un número que no es válido.</span><span class="sxs-lookup"><span data-stu-id="87b23-107">A statement refers to a file name or number that is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="87b23-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="87b23-108">To correct this error</span></span>  
  
1. <span data-ttu-id="87b23-109">Asegúrese de que el nombre de archivo se especifica en una `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="87b23-109">Make sure the file name is specified in a `FileOpen` statement.</span></span> <span data-ttu-id="87b23-110">Tenga en cuenta que si se invoca la `FileClose` instrucción sin argumentos, es posible que haya cerrado accidentalmente todos los archivos abiertos.</span><span class="sxs-lookup"><span data-stu-id="87b23-110">Note that if you invoked the `FileClose` statement without arguments, you may have inadvertently closed all open files.</span></span>  
  
2. <span data-ttu-id="87b23-111">Si el código genera los números de archivo de forma algorítmica, asegúrese de que los números sean válidos.</span><span class="sxs-lookup"><span data-stu-id="87b23-111">If your code is generating file numbers algorithmically, make sure the numbers are valid.</span></span>  
  
3. <span data-ttu-id="87b23-112">Compruebe los nombres de archivo para asegurarse de que se ajustan a las convenciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="87b23-112">Check the file names to make sure they conform to operating system conventions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b23-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87b23-113">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [<span data-ttu-id="87b23-114">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87b23-114">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
