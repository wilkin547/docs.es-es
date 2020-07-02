---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621393"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="a0ae1-101">El flujo de trabajo ahora inicia la excepción original en lugar de NullReferenceException en algunos casos</span><span class="sxs-lookup"><span data-stu-id="a0ae1-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="a0ae1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a0ae1-102">Details</span></span>

<span data-ttu-id="a0ae1-103">En .NET Framework 4.6.2 y versiones anteriores, cuando el método Execute de una actividad de flujo de trabajo inicia una excepción con un valor <code>null</code> para la propiedad <xref:System.Exception.Message>, el tiempo de ejecución de flujo de trabajo de System.Activities inicia una excepción <xref:System.NullReferenceException?displayProperty=fullName>, ocultando la original. En .NET Framework 4.7, se inicia la excepción enmascarada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a0ae1-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a0ae1-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a0ae1-104">Suggestion</span></span>

<span data-ttu-id="a0ae1-105">Si el código se basa en el control de la excepción <xref:System.NullReferenceException?displayProperty=fullName>, cámbielo para que detecte las excepciones que puedan iniciarse desde las actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a0ae1-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="a0ae1-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="a0ae1-106">Name</span></span>    | <span data-ttu-id="a0ae1-107">Valor</span><span class="sxs-lookup"><span data-stu-id="a0ae1-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a0ae1-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a0ae1-108">Scope</span></span>   |<span data-ttu-id="a0ae1-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="a0ae1-109">Minor</span></span>|
|<span data-ttu-id="a0ae1-110">Versión</span><span class="sxs-lookup"><span data-stu-id="a0ae1-110">Version</span></span>|<span data-ttu-id="a0ae1-111">4.7</span><span class="sxs-lookup"><span data-stu-id="a0ae1-111">4.7</span></span>|
|<span data-ttu-id="a0ae1-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="a0ae1-112">Type</span></span>|<span data-ttu-id="a0ae1-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a0ae1-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a0ae1-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a0ae1-114">Affected APIs</span></span>

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|
