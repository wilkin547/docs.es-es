---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496679"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a><span data-ttu-id="4eda3-101">System.Threading.Tasks.Task ya no inicia una excepción ObjectDisposedException después de desechar un objeto</span><span class="sxs-lookup"><span data-stu-id="4eda3-101">System.Threading.Tasks.Task no longer throw ObjectDisposedException after object is disposed</span></span>

#### <a name="details"></a><span data-ttu-id="4eda3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4eda3-102">Details</span></span>

<span data-ttu-id="4eda3-103">A excepción de <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, los métodos <xref:System.Threading.Tasks.Task?displayProperty=fullName> ya no inician una excepción <xref:System.ObjectDisposedException?displayProperty=fullName> después de desechar el objeto. Este cambio admite el uso de tareas en caché.</span><span class="sxs-lookup"><span data-stu-id="4eda3-103">Except for <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, <xref:System.Threading.Tasks.Task?displayProperty=fullName> methods no longer throw an <xref:System.ObjectDisposedException?displayProperty=fullName> exception after the object is disposed.This change supports the use of cached tasks.</span></span> <span data-ttu-id="4eda3-104">Por ejemplo, un método puede devolver una tarea almacenada en caché para representar una operación completada en lugar de asignar una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="4eda3-104">For example, a method can return a cached task to represent an already completed operation instead of allocating a new task.</span></span> <span data-ttu-id="4eda3-105">Esto no era posible en versiones anteriores de .NET Framework, ya que cualquier consumidor de la tarea podía desecharla, lo que hacía que se volviera inutilizable.</span><span class="sxs-lookup"><span data-stu-id="4eda3-105">This was impossible in previous .NET Framework versions, because any consumer of the task could dispose of it, which rendered it unusable.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4eda3-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4eda3-106">Suggestion</span></span>

<span data-ttu-id="4eda3-107">Tenga en cuenta que es posible que los métodos Task ya no inicien excepciones <xref:System.ObjectDisposedException?displayProperty=fullName> cuando el objeto se desecha.</span><span class="sxs-lookup"><span data-stu-id="4eda3-107">Be aware that Task methods may no longer throw <xref:System.ObjectDisposedException?displayProperty=fullName> in cases when the object is disposed.</span></span> <span data-ttu-id="4eda3-108">Si una aplicación dependía de esta excepción para conocer que se desechó una tarea, se debería actualizar para comprobar de forma explícita el estado de la tarea mediante <xref:System.Threading.Tasks.Task.Status>.</span><span class="sxs-lookup"><span data-stu-id="4eda3-108">If an app was depending on this exception to know that a task was disposed, it should be updated to explicitly check the task's status using <xref:System.Threading.Tasks.Task.Status>.</span></span>

| <span data-ttu-id="4eda3-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="4eda3-109">Name</span></span>    | <span data-ttu-id="4eda3-110">Valor</span><span class="sxs-lookup"><span data-stu-id="4eda3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4eda3-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4eda3-111">Scope</span></span>   |<span data-ttu-id="4eda3-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="4eda3-112">Minor</span></span>|
|<span data-ttu-id="4eda3-113">Versión</span><span class="sxs-lookup"><span data-stu-id="4eda3-113">Version</span></span>|<span data-ttu-id="4eda3-114">4.5</span><span class="sxs-lookup"><span data-stu-id="4eda3-114">4.5</span></span>|
|<span data-ttu-id="4eda3-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="4eda3-115">Type</span></span>|<span data-ttu-id="4eda3-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4eda3-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4eda3-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4eda3-117">Affected APIs</span></span>

<span data-ttu-id="4eda3-118">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="4eda3-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
