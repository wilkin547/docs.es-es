---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805120"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing

|   |   |
|---|---|
|Detalles|La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.|
|Sugerencia|Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa. Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
