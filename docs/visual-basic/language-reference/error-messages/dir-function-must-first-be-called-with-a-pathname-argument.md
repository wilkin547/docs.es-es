---
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: d255b8dddd098835764f72b8a166eaa08b0353df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803459"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="95b48-102">Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'</span><span class="sxs-lookup"><span data-stu-id="95b48-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="95b48-103">Una llamada inicial a la `Dir` función no incluye el `PathName` argumento.</span><span class="sxs-lookup"><span data-stu-id="95b48-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="95b48-104">La primera llamada a `Dir` debe incluir un `PathName`, las llamadas posteriores, pero a `Dir` no es necesario incluir parámetros para recuperar el elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="95b48-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95b48-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="95b48-105">To correct this error</span></span>  
  
1. <span data-ttu-id="95b48-106">Proporcione un `PathName` argumento en la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="95b48-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b48-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="95b48-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
