---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234814"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a>La versión de Entity Framework debe coincidir con la versión de .NET Framework

|   |   |
|---|---|
|Detalles|La versión de Entity Framework se debe hacer coincidir con la versión de .NET Framework. Para .NET Framework 4.5 se recomienda Entity Framework 5. Hay algunos problemas conocidos con EF 4.x en un proyecto de .NET Framework 4.5 relacionados con <xref:System.ComponentModel.DataAnnotations>. En .NET 4.5, estos se movieron a otro ensamblado, por lo que hay problemas a la hora de determinar qué anotaciones se van a usar.|
|Sugerencia|Actualizar a Entity Framework 5 para .NET Framework 4.5|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Redestinación|
