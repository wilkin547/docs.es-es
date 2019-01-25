---
title: '&#39;Dir&#39; primero se debe llamar la función con un &#39;PathName&#39; argumento'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518493"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a><span data-ttu-id="71640-102">&#39;Dir&#39; primero se debe llamar la función con un &#39;PathName&#39; argumento</span><span class="sxs-lookup"><span data-stu-id="71640-102">&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument</span></span>
<span data-ttu-id="71640-103">Una llamada inicial a la `Dir` función no incluye el `PathName` argumento.</span><span class="sxs-lookup"><span data-stu-id="71640-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="71640-104">La primera llamada a `Dir` debe incluir un `PathName`, las llamadas posteriores, pero a `Dir` no es necesario incluir parámetros para recuperar el elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="71640-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="71640-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="71640-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="71640-106">Proporcione un `PathName` argumento en la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="71640-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71640-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="71640-107">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
