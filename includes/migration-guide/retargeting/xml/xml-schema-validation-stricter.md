---
ms.openlocfilehash: ef0381dc2ce4373b2a62e8ebefa44152059ca332
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234790"
---
### <a name="xml-schema-validation-is-stricter"></a>Validación del esquema XML más estricta

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, la validación del esquema XML es más estricta. Si usa xsd:anyURI para validar un identificador URI, como un protocolo mailto, la validación producirá un error si hay espacios en el URI. En versiones anteriores de .NET Framework, la validación se realizaba correctamente. El cambio solo afecta a las aplicaciones que tienen como destino .NET Framework 4.5.|
|Sugerencia|Si se necesita la validación de .NET Framework 4.0 (menos estricta), la aplicación que realiza la validación puede establecer la versión 4.0 de .NET Framework como destino. Pero en la redestinación a .NET Framework 4.5, se debe realizar la revisión del código para asegurarse de que los URI no válidos (con espacios en blanco) no se esperan como valores de atributo con el tipo de datos anyURI.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Redestinación|
