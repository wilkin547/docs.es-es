---
ms.openlocfilehash: 907c4aa5573c392a68afad0a4d937eadcd556440
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620608"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>Los valores NULL de fusionador no son visibles en el depurador hasta un paso posterior

#### <a name="details"></a>Detalles

Un error en .NET Framework 4.5 hace que los valores establecidos mediante una operación de fusión NULL no sean visibles en el depurador inmediatamente después de ejecutar la operación de asignación cuando se ejecuta en la versión de 64 bits de la plataforma.

#### <a name="suggestion"></a>Sugerencia

Una ejecución paso a paso adicional en el depurador hará que el valor local o del campo se actualice correctamente. Ademas, este problema se ha corregido en .NET Framework 4.6; la actualización a esa versión debería solucionar el problema.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
