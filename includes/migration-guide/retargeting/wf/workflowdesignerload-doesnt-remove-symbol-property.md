---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616086"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>El método WorkflowDesigner.Load no elimina una propiedad de símbolo

#### <a name="details"></a>Detalles

Al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo y cargar un flujo de trabajo de la versión 3.5 rehospedado con el método <xref:System.Activities.Presentation.WorkflowDesigner.Load>, se inicia una excepción <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> mientras se guarda el flujo de trabajo.

#### <a name="suggestion"></a>Sugerencia

Este error solo se manifiesta al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo, por lo que una solución alternativa consiste en establecer `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` en la versión 4.0 de .NET Framework. Como alternativa, el problema se puede solucionar si se usa el método <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> para cargar el flujo de trabajo, en lugar de <xref:System.Activities.Presentation.WorkflowDesigner.Load>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.5         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
