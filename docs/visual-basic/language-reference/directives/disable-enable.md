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
- [Procedimiento para suprimir advertencias de análisis de código](../../../fundamentals/code-analysis/suppress-warnings.md)
