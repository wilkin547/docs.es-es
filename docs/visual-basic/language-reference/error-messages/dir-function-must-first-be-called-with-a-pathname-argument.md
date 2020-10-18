---
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 7f8191b0ef5452fcf6f3a20c3e0f28ca84ef9c4a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163433"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="0cc60-102">Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'</span><span class="sxs-lookup"><span data-stu-id="0cc60-102">'Dir' function must first be called with a 'PathName' argument</span></span>

<span data-ttu-id="0cc60-103">Una llamada inicial a la `Dir` función no incluye el `PathName` argumento.</span><span class="sxs-lookup"><span data-stu-id="0cc60-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="0cc60-104">La primera llamada a `Dir` debe incluir `PathName` , pero las llamadas subsiguientes a no `Dir` necesitan incluir parámetros para recuperar el elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="0cc60-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0cc60-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0cc60-105">To correct this error</span></span>

- <span data-ttu-id="0cc60-106">Proporcione un `PathName` argumento en la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="0cc60-106">Supply a `PathName` argument in the function call.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cc60-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cc60-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
