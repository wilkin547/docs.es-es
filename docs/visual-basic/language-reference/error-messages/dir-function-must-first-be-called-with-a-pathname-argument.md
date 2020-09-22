---
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 1064a44f7c266b9dcce05dfddedef6bb1e919999
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874465"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="d1860-102">Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'</span><span class="sxs-lookup"><span data-stu-id="d1860-102">'Dir' function must first be called with a 'PathName' argument</span></span>

<span data-ttu-id="d1860-103">Una llamada inicial a la `Dir` función no incluye el `PathName` argumento.</span><span class="sxs-lookup"><span data-stu-id="d1860-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="d1860-104">La primera llamada a `Dir` debe incluir `PathName` , pero las llamadas subsiguientes a no `Dir` necesitan incluir parámetros para recuperar el elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="d1860-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d1860-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d1860-105">To correct this error</span></span>  
  
1. <span data-ttu-id="d1860-106">Proporcione un `PathName` argumento en la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="d1860-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1860-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1860-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
