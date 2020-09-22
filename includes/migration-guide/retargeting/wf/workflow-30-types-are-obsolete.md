---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606743"
---
### <a name="workflow-30-types-are-obsolete"></a>Los tipos de WorkFlow 3.0 están obsoletos

#### <a name="details"></a>Detalles

Las API de Windows Workflow Foundation (WWF) 3.0 (las procedentes del espacio de nombres System.Workflow) ahora están obsoletas.

#### <a name="suggestion"></a>Sugerencia

En su lugar, deben usarse nuevas API de WWF 4.0 (en System.Activities). Puede encontrar un ejemplo de uso de las nuevas API [aquí](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md). Hay disponible más información [aquí](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5). Además, las API de WWF 3.0 continúan siendo compatibles, por lo que pueden seguir usándose. También se puede evitar la advertencia de tiempo de compilación suprimiéndola o usando un compilador anterior.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.5         |
| Tipo    | Redestinación |
