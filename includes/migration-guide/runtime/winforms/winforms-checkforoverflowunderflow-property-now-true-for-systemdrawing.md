---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379667"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing

|   |   |
|---|---|
|Detalles|La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.|
|Sugerencia|Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa. Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
