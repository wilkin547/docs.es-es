---
title: Habilitar y deshabilitar directivas
ms.date: 01/28/2021
helpviewer_keywords:
- directives, enable
- directives, disable
- disable directive
ms.openlocfilehash: 3104b25c903465f3a650304f477b25a74591c8ba
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99217243"
---
# <a name="disable-and-enable-directives-visual-basic"></a><span data-ttu-id="140f9-102">Directivas #Disable y #Enable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="140f9-102">#Disable and #Enable directives (Visual Basic)</span></span>

<span data-ttu-id="140f9-103">Las `#Disable` `#Enable` directivas y se Visual Basic las directivas de compilador de código fuente.</span><span class="sxs-lookup"><span data-stu-id="140f9-103">The `#Disable` and `#Enable` directives are Visual Basic source code compiler directives.</span></span> <span data-ttu-id="140f9-104">Se usan para deshabilitar y volver a habilitar advertencias específicas para las regiones de código.</span><span class="sxs-lookup"><span data-stu-id="140f9-104">They are used to disable and re-enable specific warnings for regions of code.</span></span>

```vb
' Suppress warning about no awaits in this method.
#Disable Warning BC42356
    Async Function TestAsync() As Task
        Console.WriteLine("testing")
    End Function
#Enable Warning BC42356
```

<span data-ttu-id="140f9-105">También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.</span><span class="sxs-lookup"><span data-stu-id="140f9-105">You can also disable and enable a comma-separated list of warning codes.</span></span>

## <a name="see-also"></a><span data-ttu-id="140f9-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="140f9-106">See also</span></span>

- [<span data-ttu-id="140f9-107">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="140f9-107">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="140f9-108">Cómo suprimir advertencias de análisis de código</span><span class="sxs-lookup"><span data-stu-id="140f9-108">How to suppress code analysis warnings</span></span>](../../../fundamentals/code-analysis/suppress-warnings.md)
