---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235846"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing

|   |   |
|---|---|
|Detalles|La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.|
|Sugerencia|Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa. Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
