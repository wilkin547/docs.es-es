---
ms.openlocfilehash: b26e346f7076a57aef8ae7587ab1222b4100a323
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957941"
---
## <a name="suppress-a-warning"></a><span data-ttu-id="323b3-101">Suprimir una advertencia</span><span class="sxs-lookup"><span data-stu-id="323b3-101">Suppress a warning</span></span>

<span data-ttu-id="323b3-102">Para suprimir una infracción de regla, establezca la opción Severity para el ID. de regla específico `none` en en un archivo EditorConfig.</span><span class="sxs-lookup"><span data-stu-id="323b3-102">To suppress a rule violation, set the severity option for the specific rule ID to `none` in an EditorConfig file.</span></span> <span data-ttu-id="323b3-103">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="323b3-103">For example:</span></span>

```ini
[*.{cs,vb}]
dotnet_diagnostic.CA1822.severity = none
```

<span data-ttu-id="323b3-104">Visual Studio proporciona formas adicionales de suprimir las advertencias de las reglas de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="323b3-104">Visual Studio provides additional ways to suppress warnings from code analysis rules.</span></span> <span data-ttu-id="323b3-105">Para obtener más información, vea [suprimir infracciones](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).</span><span class="sxs-lookup"><span data-stu-id="323b3-105">For more information, see [Suppress violations](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).</span></span>

<span data-ttu-id="323b3-106">Para obtener más información sobre los niveles de gravedad de las reglas, consulte [configurar la gravedad](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)de la regla.</span><span class="sxs-lookup"><span data-stu-id="323b3-106">For more information about rule severities, see [Configure rule severity](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).</span></span>
