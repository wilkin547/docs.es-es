---
title: Filtrar Alinear un Control con los bordes de formularios en tiempo de diseño
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b81cb839664499d69710d81b7b0c8a479966d569
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724952"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="4ff23-102">Filtrar Alinear un Control con los bordes de formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="4ff23-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>
<span data-ttu-id="4ff23-103">Puede hacer que el control se alinea el elemento en el borde de los formularios estableciendo la <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ff23-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A>.</span></span> <span data-ttu-id="4ff23-104">Esta propiedad designa el lugar en el que se encuentra el control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="4ff23-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="4ff23-105">La propiedad <xref:System.Windows.Forms.Control.Dock%2A> puede establecerse en los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ff23-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="4ff23-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="4ff23-106">Setting</span></span>|<span data-ttu-id="4ff23-107">Efecto en el control</span><span class="sxs-lookup"><span data-stu-id="4ff23-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="4ff23-108">Lo acopla en la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="4ff23-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="4ff23-109">Llena todo el espacio restante del formulario.</span><span class="sxs-lookup"><span data-stu-id="4ff23-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="4ff23-110">Lo acopla en el lado izquierdo del formulario.</span><span class="sxs-lookup"><span data-stu-id="4ff23-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="4ff23-111">No lo acopla en cualquier lugar y aparece en la ubicación especificada por su <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ff23-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="4ff23-112">Lo acopla en el lado derecho del formulario.</span><span class="sxs-lookup"><span data-stu-id="4ff23-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="4ff23-113">Lo acopla en la parte superior del formulario.</span><span class="sxs-lookup"><span data-stu-id="4ff23-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="4ff23-114">Estos valores también se pueden establecer en el código.</span><span class="sxs-lookup"><span data-stu-id="4ff23-114">These values can also be set in code.</span></span> <span data-ttu-id="4ff23-115">Para obtener más información, vea [Cómo: Alinear un Control con los bordes de formularios](how-to-align-a-control-to-the-edges-of-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4ff23-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ff23-116">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="4ff23-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4ff23-117">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="4ff23-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4ff23-118">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4ff23-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="4ff23-119">Para establecer la propiedad Dock en su control en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="4ff23-119">To set the Dock property for your control at design time</span></span>  
  
1.  <span data-ttu-id="4ff23-120">En el Diseñador de formularios de Windows, seleccione el control.</span><span class="sxs-lookup"><span data-stu-id="4ff23-120">In the Windows Forms Designer, select your control.</span></span>  
  
2.  <span data-ttu-id="4ff23-121">En el **propiedades** ventana, haga clic en cuadro de lista desplegable situado junto a la <xref:System.Windows.Forms.Control.Dock%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4ff23-121">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="4ff23-122">Una interfaz gráfica que representa los seis posibles <xref:System.Windows.Forms.Control.Dock%2A> se muestra la configuración.</span><span class="sxs-lookup"><span data-stu-id="4ff23-122">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>  
  
3.  <span data-ttu-id="4ff23-123">Elija la configuración apropiada.</span><span class="sxs-lookup"><span data-stu-id="4ff23-123">Choose the appropriate setting.</span></span>  
  
4.  <span data-ttu-id="4ff23-124">El control se acoplará la manera especificada por la configuración.</span><span class="sxs-lookup"><span data-stu-id="4ff23-124">Your control will now dock in the manner specified by the setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ff23-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ff23-125">See also</span></span>
- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4ff23-126">Cómo: Alinear un Control con los bordes de formularios</span><span class="sxs-lookup"><span data-stu-id="4ff23-126">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="4ff23-127">Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="4ff23-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="4ff23-128">Cómo: Delimitar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ff23-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="4ff23-129">Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4ff23-129">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="4ff23-130">Cómo: Delimitar y acoplar controles secundarios en un Control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4ff23-130">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="4ff23-131">Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4ff23-131">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="4ff23-132">Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4ff23-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="4ff23-133">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="4ff23-133">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
