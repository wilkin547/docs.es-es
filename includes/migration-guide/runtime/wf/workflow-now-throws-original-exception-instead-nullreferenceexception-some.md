---
ms.openlocfilehash: 6e5e90a4cfb862b3bfd74ac5a3715e97a736f598
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802520"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="ede2f-101">El flujo de trabajo ahora inicia la excepción original en lugar de NullReferenceException en algunos casos</span><span class="sxs-lookup"><span data-stu-id="ede2f-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ede2f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ede2f-102">Details</span></span>|<span data-ttu-id="ede2f-103">En .NET Framework 4.6.2 y versiones anteriores, cuando el método Execute de una actividad de flujo de trabajo inicia una excepción con un valor <code>null</code> para la propiedad <xref:System.Exception.Message>, el tiempo de ejecución de flujo de trabajo de System.Activities inicia una excepción <xref:System.NullReferenceException?displayProperty=name>, ocultando la original. En .NET Framework 4.7, se inicia la excepción enmascarada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ede2f-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=name>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>|
|<span data-ttu-id="ede2f-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ede2f-104">Suggestion</span></span>|<span data-ttu-id="ede2f-105">Si el código se basa en el control de la excepción <xref:System.NullReferenceException?displayProperty=name>, cámbielo para que detecte las excepciones que puedan iniciarse desde las actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ede2f-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=name>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>|
|<span data-ttu-id="ede2f-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ede2f-106">Scope</span></span>|<span data-ttu-id="ede2f-107">Secundaria</span><span class="sxs-lookup"><span data-stu-id="ede2f-107">Minor</span></span>|
|<span data-ttu-id="ede2f-108">Versión</span><span class="sxs-lookup"><span data-stu-id="ede2f-108">Version</span></span>|<span data-ttu-id="ede2f-109">4.7</span><span class="sxs-lookup"><span data-stu-id="ede2f-109">4.7</span></span>|
|<span data-ttu-id="ede2f-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="ede2f-110">Type</span></span>|<span data-ttu-id="ede2f-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ede2f-111">Runtime</span></span>|
|<span data-ttu-id="ede2f-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ede2f-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

