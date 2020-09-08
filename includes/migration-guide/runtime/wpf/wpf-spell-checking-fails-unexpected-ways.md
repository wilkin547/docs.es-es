---
ms.openlocfilehash: d4e60f2a59980263916718ebcc71cc359952c031
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496525"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a>Se produce un error inesperado en la revisión ortográfica de WPF

#### <a name="details"></a>Detalles

Esto incluye una serie de problemas del corrector ortográfico de WPF:<ul><li>En ocasiones, el corrector ortográfico de WPF inicia una excepción <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName>.</li><li>Se produce un error en el corrector ortográfico de WPF con una excepción <xref:System.UnauthorizedAccessException> cuando las aplicaciones se inician mediante "Ejecutar como otro usuario".</li><li>El corrector ortográfico de WPF identifica incorrectamente errores ortográficos en palabras compuestas, como "Hausnummer" en alemán.</li></ul>

#### <a name="suggestion"></a>Sugerencia

Problema 1: esto se ha solucionado en .NET Framework 4.6.2. Problema 2: el corrector ortográfico de WPF ya no se admite cuando las aplicaciones se inician con la opción "Ejecutar como otro usuario". A partir de .NET Framework 4.6.2, las aplicaciones iniciadas de esta manera ya no se bloquean de forma inesperada; en su lugar, el corrector ortográfico se deshabilita en modo silencioso. Problema 3: esto se ha solucionado en .NET Framework 4.6.2.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
