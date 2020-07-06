---
ms.openlocfilehash: c557f1cb65a675446bc77c57ef91972df92712bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617257"
---
### <a name="iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a><span data-ttu-id="309ab-101">La propiedad IAsyncResult.CompletedSynchronously debe ser correcta para que se complete la tarea resultante</span><span class="sxs-lookup"><span data-stu-id="309ab-101">IAsyncResult.CompletedSynchronously property must be correct for the resulting task to complete</span></span>

#### <a name="details"></a><span data-ttu-id="309ab-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="309ab-102">Details</span></span>

<span data-ttu-id="309ab-103">Al llamar a TaskFactory.FromAsync, la implementación de la propiedad <xref:System.IAsyncResult.CompletedSynchronously> debe ser correcta para que se complete la tarea resultante.</span><span class="sxs-lookup"><span data-stu-id="309ab-103">When calling TaskFactory.FromAsync, the implementation of the <xref:System.IAsyncResult.CompletedSynchronously> property must be correct for the resulting task to complete.</span></span> <span data-ttu-id="309ab-104">Es decir, la propiedad debe devolver true solo si la implementación se completó de manera sincrónica.</span><span class="sxs-lookup"><span data-stu-id="309ab-104">That is, the property must return true if, and only if, the implementation completed synchronously.</span></span> <span data-ttu-id="309ab-105">Anteriormente, esta propiedad no se comprobaba.</span><span class="sxs-lookup"><span data-stu-id="309ab-105">Previously, the property was not checked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="309ab-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="309ab-106">Suggestion</span></span>

<span data-ttu-id="309ab-107">Si las implementaciones de <xref:System.IAsyncResult?displayProperty=fullName> devuelven true para la propiedad <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName> solo cuando una tarea se completa de manera sincrónica, no se observará ninguna interrupción.</span><span class="sxs-lookup"><span data-stu-id="309ab-107">If <xref:System.IAsyncResult?displayProperty=fullName> implementations correctly return true for the <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName> property only when a task completed synchronously, then no break will be observed.</span></span> <span data-ttu-id="309ab-108">Los usuarios deberían revisar las implementaciones de <xref:System.IAsyncResult?displayProperty=fullName> que posean (en caso de poseer alguna) para asegurarse de que evalúan correctamente si una tarea se completó de forma sincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="309ab-108">Users should review <xref:System.IAsyncResult?displayProperty=fullName> implementations they own (if any) to ensure that they correctly evaluate whether a task completed synchronously or not.</span></span>

| <span data-ttu-id="309ab-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="309ab-109">Name</span></span>    | <span data-ttu-id="309ab-110">Valor</span><span class="sxs-lookup"><span data-stu-id="309ab-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="309ab-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="309ab-111">Scope</span></span>   | <span data-ttu-id="309ab-112">Borde</span><span class="sxs-lookup"><span data-stu-id="309ab-112">Edge</span></span>        |
| <span data-ttu-id="309ab-113">Versión</span><span class="sxs-lookup"><span data-stu-id="309ab-113">Version</span></span> | <span data-ttu-id="309ab-114">4.5</span><span class="sxs-lookup"><span data-stu-id="309ab-114">4.5</span></span>         |
| <span data-ttu-id="309ab-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="309ab-115">Type</span></span>    | <span data-ttu-id="309ab-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="309ab-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="309ab-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="309ab-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
