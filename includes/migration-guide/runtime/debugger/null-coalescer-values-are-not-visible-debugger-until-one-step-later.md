---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235793"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>Los valores NULL de fusionador no son visibles en el depurador hasta un paso posterior

|   |   |
|---|---|
|Detalles|Un error en .NET Framework 4.5 hace que los valores establecidos mediante una operación de fusión NULL no sean visibles en el depurador inmediatamente después de ejecutar la operación de asignación cuando se ejecuta en la versión de 64 bits de la plataforma.|
|Sugerencia|Una ejecución paso a paso adicional en el depurador hará que el valor local o del campo se actualice correctamente. Ademas, este problema se ha corregido en .NET Framework 4.6; la actualización a esa versión debería solucionar el problema.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
