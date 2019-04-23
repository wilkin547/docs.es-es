---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805053"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Se puede producir un error en la deserialización de objetos entre dominios de aplicación

|   |   |
|---|---|
|Detalles|En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.|
|Sugerencia|Consulte [Mitigación: deserialización de objetos en distintos dominios de aplicación](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)|
|Ámbito|Borde|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|
