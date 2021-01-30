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
# <a name="disable-and-enable-directives-visual-basic"></a>Directivas #Disable y #Enable (Visual Basic)

Las `#Disable` `#Enable` directivas y se Visual Basic las directivas de compilador de código fuente. Se usan para deshabilitar y volver a habilitar advertencias específicas para las regiones de código.

```vb
' Suppress warning about no awaits in this method.
#Disable Warning BC42356
    Async Function TestAsync() As Task
        Console.WriteLine("testing")
    End Function
#Enable Warning BC42356
```

También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](../index.md)
- [Cómo suprimir advertencias de análisis de código](../../../fundamentals/code-analysis/suppress-warnings.md)
