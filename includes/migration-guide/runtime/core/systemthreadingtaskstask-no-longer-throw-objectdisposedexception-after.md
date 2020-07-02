---
ms.openlocfilehash: 3eab96149be1e40d528cfd552bbe05ca766cf4e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620593"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a><span data-ttu-id="423ae-101">System.Threading.Tasks.Task ya no inicia una excepción ObjectDisposedException después de desechar un objeto</span><span class="sxs-lookup"><span data-stu-id="423ae-101">System.Threading.Tasks.Task no longer throw ObjectDisposedException after object is disposed</span></span>

#### <a name="details"></a><span data-ttu-id="423ae-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="423ae-102">Details</span></span>

<span data-ttu-id="423ae-103">A excepción de <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, los métodos <xref:System.Threading.Tasks.Task?displayProperty=fullName> ya no inician una excepción <xref:System.ObjectDisposedException?displayProperty=fullName> después de desechar el objeto. Este cambio admite el uso de tareas en caché.</span><span class="sxs-lookup"><span data-stu-id="423ae-103">Except for <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, <xref:System.Threading.Tasks.Task?displayProperty=fullName> methods no longer throw an <xref:System.ObjectDisposedException?displayProperty=fullName> exception after the object is disposed.This change supports the use of cached tasks.</span></span> <span data-ttu-id="423ae-104">Por ejemplo, un método puede devolver una tarea almacenada en caché para representar una operación completada en lugar de asignar una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="423ae-104">For example, a method can return a cached task to represent an already completed operation instead of allocating a new task.</span></span> <span data-ttu-id="423ae-105">Esto no era posible en versiones anteriores de .NET Framework, ya que cualquier consumidor de la tarea podía desecharla, lo que hacía que se volviera inutilizable.</span><span class="sxs-lookup"><span data-stu-id="423ae-105">This was impossible in previous .NET Framework versions, because any consumer of the task could dispose of it, which rendered it unusable.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="423ae-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="423ae-106">Suggestion</span></span>

<span data-ttu-id="423ae-107">Tenga en cuenta que es posible que los métodos Task ya no inicien excepciones <xref:System.ObjectDisposedException?displayProperty=fullName> cuando el objeto se desecha.</span><span class="sxs-lookup"><span data-stu-id="423ae-107">Be aware that Task methods may no longer throw <xref:System.ObjectDisposedException?displayProperty=fullName> in cases when the object is disposed.</span></span> <span data-ttu-id="423ae-108">Si una aplicación dependía de esta excepción para conocer que se desechó una tarea, se debería actualizar para comprobar de forma explícita el estado de la tarea mediante <xref:System.Threading.Tasks.Task.Status>.</span><span class="sxs-lookup"><span data-stu-id="423ae-108">If an app was depending on this exception to know that a task was disposed, it should be updated to explicitly check the task's status using <xref:System.Threading.Tasks.Task.Status>.</span></span>

| <span data-ttu-id="423ae-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="423ae-109">Name</span></span>    | <span data-ttu-id="423ae-110">Valor</span><span class="sxs-lookup"><span data-stu-id="423ae-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="423ae-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="423ae-111">Scope</span></span>   |<span data-ttu-id="423ae-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="423ae-112">Minor</span></span>|
|<span data-ttu-id="423ae-113">Versión</span><span class="sxs-lookup"><span data-stu-id="423ae-113">Version</span></span>|<span data-ttu-id="423ae-114">4.5</span><span class="sxs-lookup"><span data-stu-id="423ae-114">4.5</span></span>|
|<span data-ttu-id="423ae-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="423ae-115">Type</span></span>|<span data-ttu-id="423ae-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="423ae-116">Runtime</span></span>|
