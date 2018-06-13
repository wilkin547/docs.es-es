---
title: '&#39;Dir&#39; en primer lugar debe llamar la función con un &#39;PathName&#39; argumento'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 3a271d7c2c2f7b98bae8f3f6fa9b67b65e3548f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585465"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="13f97-102">&#39;Dir&#39; en primer lugar debe llamar la función con un &#39;PathName&#39; argumento</span><span class="sxs-lookup"><span data-stu-id="13f97-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="13f97-103">Una llamada inicial a la `Dir` función no incluye la `PathName` argumento.</span><span class="sxs-lookup"><span data-stu-id="13f97-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="13f97-104">La primera llamada a `Dir` debe incluir un `PathName`, pero posteriores llamadas a `Dir` no es necesario incluir parámetros para recuperar el elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="13f97-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="13f97-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="13f97-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="13f97-106">Proporcione un `PathName` argumento en la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="13f97-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f97-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="13f97-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
