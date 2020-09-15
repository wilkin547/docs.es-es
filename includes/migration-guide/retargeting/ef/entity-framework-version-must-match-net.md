---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617272"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a>La versión de Entity Framework debe coincidir con la versión de .NET Framework

#### <a name="details"></a>Detalles

La versión de Entity Framework (EF) se debe hacer coincidir con la de .NET Framework. Para .NET Framework 4.5 se recomienda Entity Framework 5. Hay algunos problemas conocidos con EF 4.x en un proyecto de .NET Framework 4.5 relacionados con <xref:System.ComponentModel.DataAnnotations>. En .NET Framework 4.5, estos se movieron a otro ensamblado, por lo que hay problemas a la hora de determinar qué anotaciones se van a usar.

#### <a name="suggestion"></a>Sugerencia

Actualizar a Entity Framework 5 para .NET Framework 4.5

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.5         |
| Tipo    | Redestinación |
