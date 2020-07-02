---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622151"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="8d2cd-101">Desplazar una instancia de TreeView o ListBox agrupada de WPF en un elemento VirtualizingStackPanel puede hacer que el programa no responda</span><span class="sxs-lookup"><span data-stu-id="8d2cd-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="8d2cd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d2cd-102">Details</span></span>

<span data-ttu-id="8d2cd-103">En .NET Framework 4.5, desplazar un elemento <xref:System.Windows.Controls.TreeView?displayProperty=fullName> de WPF en un panel StackPanel virtualizado puede hacer que el programa no responda si hay márgenes en la ventanilla (entre los elementos de <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, por ejemplo, o en algún elemento ItemsPresenter).</span><span class="sxs-lookup"><span data-stu-id="8d2cd-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="8d2cd-104">Además, en algunos casos, los elementos de diferentes tamaños de la vista pueden originar inestabilidad aun cuando no haya márgenes.</span><span class="sxs-lookup"><span data-stu-id="8d2cd-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8d2cd-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8d2cd-105">Suggestion</span></span>

<span data-ttu-id="8d2cd-106">Este error puede evitarse actualizando a .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="8d2cd-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="8d2cd-107">Como alternativa, se pueden eliminar los márgenes de las colecciones de vista (como las instancias de <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) dentro de los paneles StackPanel virtualizados si todos los elementos contenidos son del mismo tamaño.</span><span class="sxs-lookup"><span data-stu-id="8d2cd-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="8d2cd-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="8d2cd-108">Name</span></span>    | <span data-ttu-id="8d2cd-109">Valor</span><span class="sxs-lookup"><span data-stu-id="8d2cd-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8d2cd-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8d2cd-110">Scope</span></span>   |<span data-ttu-id="8d2cd-111">Major</span><span class="sxs-lookup"><span data-stu-id="8d2cd-111">Major</span></span>|
|<span data-ttu-id="8d2cd-112">Versión</span><span class="sxs-lookup"><span data-stu-id="8d2cd-112">Version</span></span>|<span data-ttu-id="8d2cd-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8d2cd-113">4.5</span></span>|
|<span data-ttu-id="8d2cd-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d2cd-114">Type</span></span>|<span data-ttu-id="8d2cd-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8d2cd-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8d2cd-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8d2cd-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
