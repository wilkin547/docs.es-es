---
ms.openlocfilehash: c0a281b05f453b68495e6fa6fca45f3f36a204a3
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "50746795"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>La validación del esquema XSD ahora detecta correctamente las infracciones de restricciones únicas si se usan claves compuestas y una de las claves está vacía

|   |   |
|---|---|
|Detalles|Las versiones de .NET Framework anteriores a la 4.6 presentaban un error que hacía que la validación de XSD no detectara restricciones únicas en claves compuestas si alguna de las claves estaba vacía. Este problema se corrigió en .NET Framework 4.6. De este modo, se conseguirá una mayor corrección en la validación, pero también podría hacer que cierto XML no valide lo que antes sí validaría.|
|Sugerencia|Si se necesita una validación de .NET Framework 4.0 menos estricta, se puede establecer la versión 4.5 (o anterior) de .NET Framework como destino de la aplicación de validación. Pero en la redestinación a .NET Framework 4.6, se debe realizar la revisión del código para asegurarse de que no se espere la validación de claves compuestas duplicadas (como se indica en la descripción de este problema).|
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Redestinación|

