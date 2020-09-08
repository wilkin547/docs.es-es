---
ms.openlocfilehash: 5a96b40e5e0df6a47415acecab410444a713632b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496361"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a><span data-ttu-id="80595-101">Los elementos EventListener de ETW no capturan eventos de proveedores con palabras clave explícitas (como el proveedor de la TPL)</span><span class="sxs-lookup"><span data-stu-id="80595-101">ETW EventListeners do not capture events from providers with explicit keywords (like the TPL provider)</span></span>

#### <a name="details"></a><span data-ttu-id="80595-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="80595-102">Details</span></span>

<span data-ttu-id="80595-103">Los elementos EventListener de ETW con una máscara de palabra clave en blanco no capturarán correctamente los eventos de proveedores con palabras clave explícitas.</span><span class="sxs-lookup"><span data-stu-id="80595-103">ETW EventListeners with a blank keyword mask do not properly capture events from providers with explicit keywords.</span></span> <span data-ttu-id="80595-104">En .NET Framework 4.5, el proveedor de la TPL comenzó a suministrar palabras clave explícitas y dio pie a este problema.</span><span class="sxs-lookup"><span data-stu-id="80595-104">In the .NET Framework 4.5, the TPL provider began providing explicit keywords and triggered this issue.</span></span> <span data-ttu-id="80595-105">En .NET Framework 4.6, se actualizaron los elementos EventListener para evitar este problema.</span><span class="sxs-lookup"><span data-stu-id="80595-105">In the .NET Framework 4.6, EventListeners have been updated to no longer have this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80595-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="80595-106">Suggestion</span></span>

<span data-ttu-id="80595-107">Para solucionar este problema, reemplace las llamadas a <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> con llamadas a la sobrecarga de EnableEvents que especifique explícitamente la máscara &quot;cualquier palabra clave&quot; que se va a usar: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Como alternativa, este problema se ha solucionado en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión.</span><span class="sxs-lookup"><span data-stu-id="80595-107">To work around this problem, replace calls to <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> with calls to the EnableEvents overload that explicitly specifies the &quot;any keywords&quot; mask to use: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>.Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="80595-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="80595-108">Name</span></span>    | <span data-ttu-id="80595-109">Valor</span><span class="sxs-lookup"><span data-stu-id="80595-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80595-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="80595-110">Scope</span></span>   |<span data-ttu-id="80595-111">Borde</span><span class="sxs-lookup"><span data-stu-id="80595-111">Edge</span></span>|
|<span data-ttu-id="80595-112">Versión</span><span class="sxs-lookup"><span data-stu-id="80595-112">Version</span></span>|<span data-ttu-id="80595-113">4.5</span><span class="sxs-lookup"><span data-stu-id="80595-113">4.5</span></span>|
|<span data-ttu-id="80595-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="80595-114">Type</span></span>|<span data-ttu-id="80595-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="80595-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="80595-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="80595-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`

-->
