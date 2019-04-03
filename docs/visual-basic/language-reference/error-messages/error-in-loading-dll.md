---
title: Error al cargar la biblioteca DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816907"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="131f5-102">Error al cargar la biblioteca DLL (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131f5-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="131f5-103">Una biblioteca de vínculos dinámicos (DLL) es una biblioteca especificada en el `Lib` cláusula de una `Declare` instrucción.</span><span class="sxs-lookup"><span data-stu-id="131f5-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="131f5-104">Posibles causas de este error son:</span><span class="sxs-lookup"><span data-stu-id="131f5-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="131f5-105">El archivo no es ejecutable de DLL.</span><span class="sxs-lookup"><span data-stu-id="131f5-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="131f5-106">El archivo no es un archivo DLL de Windows de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="131f5-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="131f5-107">El archivo DLL hace referencia a otro archivo DLL que no está presente.</span><span class="sxs-lookup"><span data-stu-id="131f5-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="131f5-108">El archivo DLL o un archivo DLL que se hace referencia no está en un directorio especificado en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="131f5-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="131f5-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="131f5-109">To correct this error</span></span>  
  
-   <span data-ttu-id="131f5-110">Si el archivo es un archivo de texto de origen y, por lo tanto, no DLL ejecutable, debe estar compilado y vinculado a una formato ejecutable de DLL.</span><span class="sxs-lookup"><span data-stu-id="131f5-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="131f5-111">Si el archivo no es una DLL de Windows de Microsoft, obtenga el equivalente de Windows Microsoft.</span><span class="sxs-lookup"><span data-stu-id="131f5-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="131f5-112">Si el archivo DLL hace referencia a otro archivo DLL que no está presente, obtenga el archivo DLL que se hace referencia y que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="131f5-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="131f5-113">Si el archivo DLL o un archivo DLL que se hace referencia no está en un directorio especificado por la ruta de acceso, mueva el archivo DLL en un directorio que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="131f5-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131f5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="131f5-114">See also</span></span>

- [<span data-ttu-id="131f5-115">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="131f5-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
