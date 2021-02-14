---
description: "Obtenga más información sobre: la función ' dir ' debe llamarse primero con un argumento ' PathName '"
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 076828978b27911a97a4767cde1b1d7b04317a31
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479977"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="7b70a-103">Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'</span><span class="sxs-lookup"><span data-stu-id="7b70a-103">'Dir' function must first be called with a 'PathName' argument</span></span>

<span data-ttu-id="7b70a-104">Una llamada inicial a la `Dir` función no incluye el `PathName` argumento.</span><span class="sxs-lookup"><span data-stu-id="7b70a-104">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="7b70a-105">La primera llamada a `Dir` debe incluir `PathName` , pero las llamadas subsiguientes a no `Dir` necesitan incluir parámetros para recuperar el elemento siguiente.</span><span class="sxs-lookup"><span data-stu-id="7b70a-105">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7b70a-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7b70a-106">To correct this error</span></span>

- <span data-ttu-id="7b70a-107">Proporcione un `PathName` argumento en la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="7b70a-107">Supply a `PathName` argument in the function call.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b70a-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b70a-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
