---
ms.openlocfilehash: a806107456a65a4919592da9535a2617f677cfe0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496641"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="028a0-101">El elemento DispatcherSynchronizationContext.CreateCopy de WPF ahora devuelve una copia nueva en lugar de la instancia actual</span><span class="sxs-lookup"><span data-stu-id="028a0-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="028a0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="028a0-102">Details</span></span>

<span data-ttu-id="028a0-103">En .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> devolvía una referencia a la instancia actual, principalmente como optimización del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="028a0-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="028a0-104">En .NET Framework 4.5, devuelve una nueva instancia que permite concluir por primera vez que las mismas referencias indican que el subproceso de ejecución se encuentra en el contexto de sincronización correcto.</span><span class="sxs-lookup"><span data-stu-id="028a0-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="028a0-105">Es poco probable que el código que comprueba la identidad de estas referencias se vea afectado, pero debido al cambio, el código que llama a <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> se debería probar como parte de la migración a .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="028a0-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="028a0-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="028a0-106">Suggestion</span></span>

<span data-ttu-id="028a0-107">Tenga en cuenta que <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> ahora devolverá un objeto <xref:System.Threading.SynchronizationContext?displayProperty=fullName> nuevo.</span><span class="sxs-lookup"><span data-stu-id="028a0-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="028a0-108">Anteriormente, el código que usaba la equivalencia de referencias generadas de esta forma no comprobaba en realidad si se encontraba en el contexto correcto, pero sí lo hace si se compila en .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="028a0-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="028a0-109">Aunque es poco probable que cause problemas, debería bastar con ejecutar las rutas de acceso del código afectado para comprobar si lo hace.</span><span class="sxs-lookup"><span data-stu-id="028a0-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="028a0-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="028a0-110">Name</span></span>    | <span data-ttu-id="028a0-111">Valor</span><span class="sxs-lookup"><span data-stu-id="028a0-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="028a0-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="028a0-112">Scope</span></span>   |<span data-ttu-id="028a0-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="028a0-113">Minor</span></span>|
|<span data-ttu-id="028a0-114">Versión</span><span class="sxs-lookup"><span data-stu-id="028a0-114">Version</span></span>|<span data-ttu-id="028a0-115">4.5</span><span class="sxs-lookup"><span data-stu-id="028a0-115">4.5</span></span>|
|<span data-ttu-id="028a0-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="028a0-116">Type</span></span>|<span data-ttu-id="028a0-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="028a0-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="028a0-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="028a0-118">Affected APIs</span></span>

- <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy`

-->
