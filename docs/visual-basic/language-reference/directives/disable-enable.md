---
description: 'Más información sobre: #Disable y directivas de #Enable (Visual Basic)'
title: Habilitar y deshabilitar directivas
ms.date: 01/28/2021
helpviewer_keywords:
- directives, enable
- directives, disable
- disable directive
ms.openlocfilehash: d600cc959639a3f70bca5678fbc81aae0806c9cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797268"
---
# <a name="disable-and-enable-directives-visual-basic"></a><span data-ttu-id="8d864-103">Directivas #Disable y #Enable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d864-103">#Disable and #Enable directives (Visual Basic)</span></span>

<span data-ttu-id="8d864-104">Las `#Disable` `#Enable` directivas y se Visual Basic las directivas de compilador de código fuente.</span><span class="sxs-lookup"><span data-stu-id="8d864-104">The `#Disable` and `#Enable` directives are Visual Basic source code compiler directives.</span></span> <span data-ttu-id="8d864-105">Se usan para deshabilitar y volver a habilitar advertencias específicas para las regiones de código.</span><span class="sxs-lookup"><span data-stu-id="8d864-105">They are used to disable and re-enable specific warnings for regions of code.</span></span>

```vb
' Suppress warning about no awaits in this method.
#Disable Warning BC42356
    Async Function TestAsync() As Task
        Console.WriteLine("testing")
    End Function
#Enable Warning BC42356
```

<span data-ttu-id="8d864-106">También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.</span><span class="sxs-lookup"><span data-stu-id="8d864-106">You can also disable and enable a comma-separated list of warning codes.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d864-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d864-107">See also</span></span>

- [<span data-ttu-id="8d864-108">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d864-108">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="8d864-109">Procedimiento para suprimir advertencias de análisis de código</span><span class="sxs-lookup"><span data-stu-id="8d864-109">How to suppress code analysis warnings</span></span>](../../../fundamentals/code-analysis/suppress-warnings.md)
