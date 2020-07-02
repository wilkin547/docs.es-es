---
ms.openlocfilehash: b92dc8a1c48e83846c3d9a1d86e66629f31b7722
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622121"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="6f623-101">Incapacidad intermitente para desplazarse hasta el último elemento de instancias ItemsControl (como ListBox y DataGrid) al usar elementos DataTemplate personalizados</span><span class="sxs-lookup"><span data-stu-id="6f623-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="6f623-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6f623-102">Details</span></span>

<span data-ttu-id="6f623-103">En algunos casos, un error de .NET Framework 4.5 impide que las instancias de ItemsControl (como <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) se desplacen hasta su último elemento cuando se usan elementos DataTemplate personalizados.</span><span class="sxs-lookup"><span data-stu-id="6f623-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="6f623-104">Si se trata de efectuar el desplazamiento una segunda vez (después de haber vuelto arriba), sí funciona.</span><span class="sxs-lookup"><span data-stu-id="6f623-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6f623-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6f623-105">Suggestion</span></span>

<span data-ttu-id="6f623-106">Este problema se resolvió en .NET Framework 4.5.2, por lo que otra posible solución es actualizar a esta versión (u otra posterior) de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6f623-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="6f623-107">Los usuarios también pueden arrastrar las barras de desplazamiento hasta los últimos elementos de estas colecciones, pero puede ser posible que tengan que hacerlo dos veces para conseguirlo.</span><span class="sxs-lookup"><span data-stu-id="6f623-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="6f623-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6f623-108">Name</span></span>    | <span data-ttu-id="6f623-109">Valor</span><span class="sxs-lookup"><span data-stu-id="6f623-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6f623-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6f623-110">Scope</span></span>   |<span data-ttu-id="6f623-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6f623-111">Minor</span></span>|
|<span data-ttu-id="6f623-112">Versión</span><span class="sxs-lookup"><span data-stu-id="6f623-112">Version</span></span>|<span data-ttu-id="6f623-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6f623-113">4.5</span></span>|
|<span data-ttu-id="6f623-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="6f623-114">Type</span></span>|<span data-ttu-id="6f623-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6f623-115">Runtime</span></span>|
