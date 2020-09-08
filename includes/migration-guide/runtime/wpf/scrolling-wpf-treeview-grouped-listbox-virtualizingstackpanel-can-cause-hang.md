---
ms.openlocfilehash: 31ada197db36be192317e32a37a353d375d9cc65
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497167"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="d28de-101">Desplazar una instancia de TreeView o ListBox agrupada de WPF en un elemento VirtualizingStackPanel puede hacer que el programa no responda</span><span class="sxs-lookup"><span data-stu-id="d28de-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="d28de-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d28de-102">Details</span></span>

<span data-ttu-id="d28de-103">En .NET Framework 4.5, desplazar un elemento <xref:System.Windows.Controls.TreeView?displayProperty=fullName> de WPF en un panel StackPanel virtualizado puede hacer que el programa no responda si hay márgenes en la ventanilla (entre los elementos de <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, por ejemplo, o en algún elemento ItemsPresenter).</span><span class="sxs-lookup"><span data-stu-id="d28de-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="d28de-104">Además, en algunos casos, los elementos de diferentes tamaños de la vista pueden originar inestabilidad aun cuando no haya márgenes.</span><span class="sxs-lookup"><span data-stu-id="d28de-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d28de-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d28de-105">Suggestion</span></span>

<span data-ttu-id="d28de-106">Este error puede evitarse actualizando a .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="d28de-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="d28de-107">Como alternativa, se pueden eliminar los márgenes de las colecciones de vista (como las instancias de <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) dentro de los paneles StackPanel virtualizados si todos los elementos contenidos son del mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="d28de-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="d28de-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d28de-108">Name</span></span>    | <span data-ttu-id="d28de-109">Valor</span><span class="sxs-lookup"><span data-stu-id="d28de-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d28de-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d28de-110">Scope</span></span>   |<span data-ttu-id="d28de-111">Major</span><span class="sxs-lookup"><span data-stu-id="d28de-111">Major</span></span>|
|<span data-ttu-id="d28de-112">Versión</span><span class="sxs-lookup"><span data-stu-id="d28de-112">Version</span></span>|<span data-ttu-id="d28de-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d28de-113">4.5</span></span>|
|<span data-ttu-id="d28de-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="d28de-114">Type</span></span>|<span data-ttu-id="d28de-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d28de-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d28de-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d28de-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)`

-->
