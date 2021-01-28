---
ms.openlocfilehash: b26e346f7076a57aef8ae7587ab1222b4100a323
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957941"
---
## <a name="suppress-a-warning"></a>Suprimir una advertencia

Para suprimir una infracción de regla, establezca la opción Severity para el ID. de regla específico `none` en en un archivo EditorConfig. Por ejemplo:

```ini
[*.{cs,vb}]
dotnet_diagnostic.CA1822.severity = none
```

Visual Studio proporciona formas adicionales de suprimir las advertencias de las reglas de análisis de código. Para obtener más información, vea [suprimir infracciones](/visualstudio/code-quality/use-roslyn-analyzers#suppress-violations).

Para obtener más información sobre los niveles de gravedad de las reglas, consulte [configurar la gravedad](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)de la regla.
