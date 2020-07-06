---
ms.openlocfilehash: 349854b0dec5a585990b9c5e7c0b575df5bf70f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615777"
---
### <a name="xsd-schema-validation-now-correctly-detects-violations-of-unique-constraints-if-compound-keys-are-used-and-one-key-is-empty"></a>La validación del esquema XSD ahora detecta correctamente las infracciones de restricciones únicas si se usan claves compuestas y una de las claves está vacía

#### <a name="details"></a>Detalles

Las versiones de .NET Framework anteriores a la 4.6 presentaban un error que hacía que la validación de XSD no detectara restricciones únicas en claves compuestas si alguna de las claves estaba vacía. Este problema se corrigió en .NET Framework 4.6. De este modo, se conseguirá una mayor corrección en la validación, pero también podría hacer que cierto XML no valide lo que antes sí validaría.

#### <a name="suggestion"></a>Sugerencia

Si se necesita una validación de .NET Framework 4.0 menos estricta, se puede establecer la versión 4.5 (o anterior) de .NET Framework como destino de la aplicación de validación. Pero en la redestinación a .NET Framework 4.6, se debe realizar la revisión del código para asegurarse de que no se espere la validación de claves compuestas duplicadas (como se indica en la descripción de este problema).

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6         |
| Tipo    | Redestinación |
