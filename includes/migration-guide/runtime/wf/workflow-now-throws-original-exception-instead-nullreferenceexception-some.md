---
ms.openlocfilehash: 6e5e90a4cfb862b3bfd74ac5a3715e97a736f598
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802520"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a>El flujo de trabajo ahora inicia la excepción original en lugar de NullReferenceException en algunos casos

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6.2 y versiones anteriores, cuando el método Execute de una actividad de flujo de trabajo inicia una excepción con un valor <code>null</code> para la propiedad <xref:System.Exception.Message>, el tiempo de ejecución de flujo de trabajo de System.Activities inicia una excepción <xref:System.NullReferenceException?displayProperty=name>, ocultando la original. En .NET Framework 4.7, se inicia la excepción enmascarada anteriormente.|
|Sugerencia|Si el código se basa en el control de la excepción <xref:System.NullReferenceException?displayProperty=name>, cámbielo para que detecte las excepciones que puedan iniciarse desde las actividades personalizadas.|
|Ámbito|Secundaria|
|Versión|4.7|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

