---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496373"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="18ce3-101">El flujo de trabajo ahora inicia la excepción original en lugar de NullReferenceException en algunos casos</span><span class="sxs-lookup"><span data-stu-id="18ce3-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="18ce3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="18ce3-102">Details</span></span>

<span data-ttu-id="18ce3-103">En .NET Framework 4.6.2 y versiones anteriores, cuando el método Execute de una actividad de flujo de trabajo inicia una excepción con un valor <code>null</code> para la propiedad <xref:System.Exception.Message>, el tiempo de ejecución de flujo de trabajo de System.Activities inicia una excepción <xref:System.NullReferenceException?displayProperty=fullName>, ocultando la original. En .NET Framework 4.7, se inicia la excepción enmascarada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="18ce3-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="18ce3-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="18ce3-104">Suggestion</span></span>

<span data-ttu-id="18ce3-105">Si el código se basa en el control de la excepción <xref:System.NullReferenceException?displayProperty=fullName>, cámbielo para que detecte las excepciones que puedan iniciarse desde las actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="18ce3-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="18ce3-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="18ce3-106">Name</span></span>    | <span data-ttu-id="18ce3-107">Valor</span><span class="sxs-lookup"><span data-stu-id="18ce3-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="18ce3-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="18ce3-108">Scope</span></span>   |<span data-ttu-id="18ce3-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="18ce3-109">Minor</span></span>|
|<span data-ttu-id="18ce3-110">Versión</span><span class="sxs-lookup"><span data-stu-id="18ce3-110">Version</span></span>|<span data-ttu-id="18ce3-111">4.7</span><span class="sxs-lookup"><span data-stu-id="18ce3-111">4.7</span></span>|
|<span data-ttu-id="18ce3-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="18ce3-112">Type</span></span>|<span data-ttu-id="18ce3-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="18ce3-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="18ce3-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="18ce3-114">Affected APIs</span></span>

- <xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)`
- `M:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)`
- ``M:System.Activities.AsyncCodeActivity`1.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)``
- `M:System.Activities.WorkflowInvoker.Invoke`

-->
