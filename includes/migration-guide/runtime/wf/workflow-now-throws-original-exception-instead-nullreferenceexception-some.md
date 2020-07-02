---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621393"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>El flujo de trabajo ahora inicia la excepción original en lugar de NullReferenceException en algunos casos

#### <a name="details"></a>Detalles

En .NET Framework 4.6.2 y versiones anteriores, cuando el método Execute de una actividad de flujo de trabajo inicia una excepción con un valor <code>null</code> para la propiedad <xref:System.Exception.Message>, el tiempo de ejecución de flujo de trabajo de System.Activities inicia una excepción <xref:System.NullReferenceException?displayProperty=fullName>, ocultando la original. En .NET Framework 4.7, se inicia la excepción enmascarada anteriormente.

#### <a name="suggestion"></a>Sugerencia

Si el código se basa en el control de la excepción <xref:System.NullReferenceException?displayProperty=fullName>, cámbielo para que detecte las excepciones que puedan iniciarse desde las actividades personalizadas.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.7|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
