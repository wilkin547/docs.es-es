---
ms.openlocfilehash: fc6066fd0b23d299158114cb397934041b99ba47
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620704"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a><span data-ttu-id="24c1b-101">El elemento DispatcherSynchronizationContext.CreateCopy de WPF ahora devuelve una copia nueva en lugar de la instancia actual</span><span class="sxs-lookup"><span data-stu-id="24c1b-101">WPF DispatcherSynchronizationContext.CreateCopy now returns a new copy instead of the current instance</span></span>

#### <a name="details"></a><span data-ttu-id="24c1b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="24c1b-102">Details</span></span>

<span data-ttu-id="24c1b-103">En .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> devolvía una referencia a la instancia actual, principalmente como optimización del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="24c1b-103">In the .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> returned a reference to the current instance, primarily as a performance optimization.</span></span> <span data-ttu-id="24c1b-104">En .NET Framework 4.5, devuelve una nueva instancia que permite concluir por primera vez que las mismas referencias indican que el subproceso de ejecución se encuentra en el contexto de sincronización correcto.</span><span class="sxs-lookup"><span data-stu-id="24c1b-104">In the .NET Framework 4.5, it returns a new instance which makes it possible for the first time to conclude that equal references indicate the executing thread is in the correct synchronization context.</span></span>  <span data-ttu-id="24c1b-105">Es poco probable que el código que comprueba la identidad de estas referencias se vea afectado, pero debido al cambio, el código que llama a <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> se debería probar como parte de la migración a .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="24c1b-105">It is unlikely that code that checks the identity of these references will be affected, but because of the change, code that calls <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> should be tested as part of migration to the .NET Framework 4.5 or newer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="24c1b-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="24c1b-106">Suggestion</span></span>

<span data-ttu-id="24c1b-107">Tenga en cuenta que <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> ahora devolverá un objeto <xref:System.Threading.SynchronizationContext?displayProperty=fullName> nuevo.</span><span class="sxs-lookup"><span data-stu-id="24c1b-107">Be aware that <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> will now return a new <xref:System.Threading.SynchronizationContext?displayProperty=fullName> object.</span></span> <span data-ttu-id="24c1b-108">Anteriormente, el código que usaba la equivalencia de referencias generadas de esta forma no comprobaba en realidad si se encontraba en el contexto correcto, pero sí lo hace si se compila en .NET Framework 4.5 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="24c1b-108">Previously, code that used equivalence of references generated this way was not actually checking whether it was in the proper context, but does when built against .NET Framework 4.5 or later.</span></span>  <span data-ttu-id="24c1b-109">Aunque es poco probable que cause problemas, debería bastar con ejecutar las rutas de acceso del código afectado para comprobar si lo hace.</span><span class="sxs-lookup"><span data-stu-id="24c1b-109">While unlikely to cause issues, exercising the affected code paths should be enough to determine if this poses any problem.</span></span>

| <span data-ttu-id="24c1b-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="24c1b-110">Name</span></span>    | <span data-ttu-id="24c1b-111">Valor</span><span class="sxs-lookup"><span data-stu-id="24c1b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="24c1b-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="24c1b-112">Scope</span></span>   |<span data-ttu-id="24c1b-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="24c1b-113">Minor</span></span>|
|<span data-ttu-id="24c1b-114">Versión</span><span class="sxs-lookup"><span data-stu-id="24c1b-114">Version</span></span>|<span data-ttu-id="24c1b-115">4.5</span><span class="sxs-lookup"><span data-stu-id="24c1b-115">4.5</span></span>|
|<span data-ttu-id="24c1b-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="24c1b-116">Type</span></span>|<span data-ttu-id="24c1b-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="24c1b-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="24c1b-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="24c1b-118">Affected APIs</span></span>

-<xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType></li></ul>|
