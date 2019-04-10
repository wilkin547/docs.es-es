---
title: Filtrar para alinear un control con los bordes de los formularios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: beb8881dbd2aedaefe66510c2942ce6c082b9729
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329978"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a><span data-ttu-id="c5a60-102">Filtrar para alinear un control con los bordes de los formularios</span><span class="sxs-lookup"><span data-stu-id="c5a60-102">How to: Align a Control to the Edges of Forms</span></span>
<span data-ttu-id="c5a60-103">Puede alinear el control con el borde de los formularios estableciendo la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5a60-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="c5a60-104">Esta propiedad designa el lugar en el que se encuentra el control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c5a60-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="c5a60-105">La propiedad <xref:System.Windows.Forms.Control.Dock%2A> puede establecerse en los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5a60-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="c5a60-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c5a60-106">Setting</span></span>|<span data-ttu-id="c5a60-107">Efecto en el control</span><span class="sxs-lookup"><span data-stu-id="c5a60-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="c5a60-108">Lo acopla en la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="c5a60-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="c5a60-109">Llena todo el espacio restante del formulario.</span><span class="sxs-lookup"><span data-stu-id="c5a60-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="c5a60-110">Lo acopla en el lado izquierdo del formulario.</span><span class="sxs-lookup"><span data-stu-id="c5a60-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="c5a60-111">No lo acopla en ningún lugar y aparece en la ubicación especificada por su propiedad <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5a60-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="c5a60-112">Lo acopla en el lado derecho del formulario.</span><span class="sxs-lookup"><span data-stu-id="c5a60-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="c5a60-113">Lo acopla en la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="c5a60-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="c5a60-114">Hay compatibilidad en tiempo de diseño para esta característica en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c5a60-114">There is design-time support for this feature in Visual Studio.</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a><span data-ttu-id="c5a60-115">Para establecer la propiedad Dock en su control en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c5a60-115">To set the Dock property for your control at run time</span></span>  
  
1. <span data-ttu-id="c5a60-116">Establezca un valor adecuado en el código para la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5a60-116">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to the appropriate value in code.</span></span>  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c5a60-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5a60-117">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c5a60-118">Desarrollar controles personalizados de formularios Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c5a60-118">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="c5a60-119">Filtrar para delimitar y acoplar controles secundarios en un control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c5a60-119">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="c5a60-120">Filtrar para delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c5a60-120">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="c5a60-121">Información general sobre la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="c5a60-121">AutoSize Property Overview</span></span>](autosize-property-overview.md)
