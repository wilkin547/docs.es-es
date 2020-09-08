---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497272"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="df82b-101">Problema de enlace de IsSelected de ListBoxItem con ObservableCollection&lt;T&gt;.Move</span><span class="sxs-lookup"><span data-stu-id="df82b-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="df82b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="df82b-102">Details</span></span>

<span data-ttu-id="df82b-103">Las llamadas a <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> o <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> en una colección enlazada a un control <xref:System.Windows.Controls.ListBox?displayProperty=fullName> con elementos seleccionados puede provocar un comportamiento incorrecto en la selección o anulación de selecciones futuras de elementos <xref:System.Windows.Controls.ListBox?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="df82b-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="df82b-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="df82b-104">Suggestion</span></span>

<span data-ttu-id="df82b-105">Las llamadas a <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> y <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> en lugar de a <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> serán la solución alternativa a este problema.</span><span class="sxs-lookup"><span data-stu-id="df82b-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="df82b-106">Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df82b-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="df82b-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="df82b-107">Name</span></span>    | <span data-ttu-id="df82b-108">Valor</span><span class="sxs-lookup"><span data-stu-id="df82b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="df82b-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="df82b-109">Scope</span></span>   |<span data-ttu-id="df82b-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="df82b-110">Minor</span></span>|
|<span data-ttu-id="df82b-111">Versión</span><span class="sxs-lookup"><span data-stu-id="df82b-111">Version</span></span>|<span data-ttu-id="df82b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="df82b-112">4.5</span></span>|
|<span data-ttu-id="df82b-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="df82b-113">Type</span></span>|<span data-ttu-id="df82b-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="df82b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="df82b-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="df82b-115">Affected APIs</span></span>

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
