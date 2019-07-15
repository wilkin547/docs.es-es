---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858599"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>Los valores NULL de fusionador no son visibles en el depurador hasta un paso posterior

|   |   |
|---|---|
|Detalles|Un error en .NET Framework 4.5 hace que los valores establecidos mediante una operación de fusión NULL no sean visibles en el depurador inmediatamente después de ejecutar la operación de asignación cuando se ejecuta en la versión de 64 bits de la plataforma.|
|Sugerencia|Una ejecución paso a paso adicional en el depurador hará que el valor local o del campo se actualice correctamente. Ademas, este problema se ha corregido en .NET Framework 4.6; la actualización a esa versión debería solucionar el problema.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

