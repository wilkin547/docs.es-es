---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620695"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing

#### <a name="details"></a>Detalles

La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.

#### <a name="suggestion"></a>Sugerencia

Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa. Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=fullName>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
