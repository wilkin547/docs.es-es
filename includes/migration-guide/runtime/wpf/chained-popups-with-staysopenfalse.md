---
ms.openlocfilehash: 171b7a3a962f8259e64b88f1ae893e649b5f24bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621397"
---
### <a name="chained-popups-with-staysopenfalse"></a>Menús emergentes encadenados con StaysOpen=False

#### <a name="details"></a>Detalles

Se supone que un menú emergente con StaysOpen=False se cierra al hacer clic fuera de la ventana emergente. Cuando se encadenaban dos o más de estos elementos Popup (es decir, uno contiene al otro), se producían muchos problemas, incluidos los siguientes:<ul><li>Se abren dos niveles, se hace clic fuera de P2 pero dentro de P1.  No sucede nada.</li><li>Se abren dos niveles, se hace clic fuera de P1.  Los dos menús emergentes se cierran.</li><li>Se abren y se cierran dos niveles.  Después, se intenta volver a abrir P2.  No sucede nada.</li><li>Se intenta abrir tres niveles.  No se puede.  (No sucede nada o se cierra el primero de los dos niveles, en función de dónde se hizo clic). Estos casos (y otras variantes) ahora funcionan según lo esperado.</li></ul>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7.1|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
