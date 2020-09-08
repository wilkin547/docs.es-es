---
ms.openlocfilehash: f50022d9a7bacd7be40fe3050ced26e7c25cf7aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497826"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a><span data-ttu-id="92ae0-101">Al quitar un elemento de una colección personalizada de INCC se produce un bloqueo en Selector</span><span class="sxs-lookup"><span data-stu-id="92ae0-101">Crash in Selector when removing an item from a custom INCC collection</span></span>

#### <a name="details"></a><span data-ttu-id="92ae0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="92ae0-102">Details</span></span>

<span data-ttu-id="92ae0-103">Se puede iniciar una excepción <code>T:System.InvalidOperationException</code> en el escenario siguiente:</span><span class="sxs-lookup"><span data-stu-id="92ae0-103">An <code>T:System.InvalidOperationException</code> can occur in the following scenario:</span></span><ul><li><span data-ttu-id="92ae0-104">El ItemsSource de un control <code>T:System.Windows.Controls.Primitives.Selector</code> es una colección con una implementación personalizada de <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</span><span class="sxs-lookup"><span data-stu-id="92ae0-104">The ItemsSource for a <code>T:System.Windows.Controls.Primitives.Selector</code> is a collection with a custom implementation of <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</span></span></li><li><span data-ttu-id="92ae0-105">El elemento seleccionado se quita de la colección.</span><span class="sxs-lookup"><span data-stu-id="92ae0-105">The selected item is removed from the collection.</span></span></li><li><span data-ttu-id="92ae0-106"><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> tiene <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (lo que indica una posición desconocida).</span><span class="sxs-lookup"><span data-stu-id="92ae0-106">The <code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> has <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (indicating an unknown position).</span></span></li></ul><span data-ttu-id="92ae0-107">La pila de llamadas de la excepción comienza en System.Windows.Threading.Dispatcher.VerifyAccess() en System.Windows.DependencyObject.GetValue(DependencyProperty dp) en System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject elemento). Esta excepción se puede iniciar en .NET Framework 4.5 si la aplicación tiene más de un subproceso de distribuidor.</span><span class="sxs-lookup"><span data-stu-id="92ae0-107">The exception's callstack begins at System.Windows.Threading.Dispatcher.VerifyAccess() at System.Windows.DependencyObject.GetValue(DependencyProperty dp) at System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)This exception can occur in .NET Framework 4.5 if the application has more than one Dispatcher thread.</span></span> <span data-ttu-id="92ae0-108">En .NET Framework 4.7, la excepción también se puede iniciar en las aplicaciones con un único subproceso de distribuidor.</span><span class="sxs-lookup"><span data-stu-id="92ae0-108">In .NET Framework 4.7 the exception can also occur in applications with a single Dispatcher thread.</span></span> <span data-ttu-id="92ae0-109">El problema se corrigió en .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="92ae0-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="92ae0-110">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="92ae0-110">Suggestion</span></span>

<span data-ttu-id="92ae0-111">Actualice a .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="92ae0-111">Upgrade to .NET Framework 4.7.1.</span></span>

| <span data-ttu-id="92ae0-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="92ae0-112">Name</span></span>    | <span data-ttu-id="92ae0-113">Valor</span><span class="sxs-lookup"><span data-stu-id="92ae0-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="92ae0-114">Ámbito</span><span class="sxs-lookup"><span data-stu-id="92ae0-114">Scope</span></span>   |<span data-ttu-id="92ae0-115">Secundaria</span><span class="sxs-lookup"><span data-stu-id="92ae0-115">Minor</span></span>|
|<span data-ttu-id="92ae0-116">Versión</span><span class="sxs-lookup"><span data-stu-id="92ae0-116">Version</span></span>|<span data-ttu-id="92ae0-117">4.7</span><span class="sxs-lookup"><span data-stu-id="92ae0-117">4.7</span></span>|
|<span data-ttu-id="92ae0-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="92ae0-118">Type</span></span>|<span data-ttu-id="92ae0-119">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="92ae0-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="92ae0-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="92ae0-120">Affected APIs</span></span>

<span data-ttu-id="92ae0-121">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="92ae0-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
