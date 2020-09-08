---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496403"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Mejora del comportamiento de los KeyTip en WPF

#### <a name="details"></a>Detalles

El comportamiento de los KeyTip se ha modificado para equipararlo al de Microsoft Word y el Explorador de Windows. Mediante la comprobación de si el estado del KeyTip está habilitado o no cuando se presiona una <xref:System.Windows.Input.KeyEventArgs.SystemKey> (en concreto, <xref:System.Windows.Input.Key> o <xref:System.Windows.Input.Key.F11>), WPF administra las teclas de KeyTip de la forma adecuada. Los KeyTip ahora cierran un menú incluso cuando se abre con el mouse.

#### <a name="suggestion"></a>Sugerencia

N/D

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
