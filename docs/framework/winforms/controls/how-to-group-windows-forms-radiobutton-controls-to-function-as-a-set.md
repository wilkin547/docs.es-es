---
title: Procedimiento para agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 857e61bc89e072aebcf34793d7e8504ece3318c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307276"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="5eaf6-102">Procedimiento para agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto</span><span class="sxs-lookup"><span data-stu-id="5eaf6-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="5eaf6-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controles están diseñados para proporcionar a los usuarios una opción entre dos o más configuraciones, de los cuales sólo uno puede asignarse a un procedimiento u objeto.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="5eaf6-104">Por ejemplo, un grupo de <xref:System.Windows.Forms.RadioButton> controles pueden mostrar una serie de transporte para un pedido, pero solo uno de los transportistas se usará.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="5eaf6-105">Por lo tanto, solo un <xref:System.Windows.Forms.RadioButton> a la vez puede seleccionarse, incluso si forma parte de un grupo funcional.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="5eaf6-106">Agrupar botones de radio, dibuje dentro de un contenedor, como un <xref:System.Windows.Forms.Panel> (control), un <xref:System.Windows.Forms.GroupBox> control o formulario.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="5eaf6-107">Todos los botones de radio que se agregan directamente a un grupo de un formulario se convierten en.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="5eaf6-108">Para agregar grupos independientes, debe colocarlos dentro de paneles o cuadros de grupo.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="5eaf6-109">Para obtener más información acerca de los paneles o cuadros de grupo, consulte [información general del Control Panel](panel-control-overview-windows-forms.md) o [información general del Control GroupBox](groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5eaf6-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="5eaf6-110">Para agrupar controles RadioButton en un conjunto para que funcionen de forma independiente</span><span class="sxs-lookup"><span data-stu-id="5eaf6-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="5eaf6-111">Arrastre un <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controlar desde la **Windows Forms** ficha la **cuadro de herramientas** hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="5eaf6-112">Dibujar <xref:System.Windows.Forms.RadioButton> a los controles de la <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> control.</span><span class="sxs-lookup"><span data-stu-id="5eaf6-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eaf6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5eaf6-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="5eaf6-114">Información general sobre el control RadioButton</span><span class="sxs-lookup"><span data-stu-id="5eaf6-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="5eaf6-115">Información general del control Panel</span><span class="sxs-lookup"><span data-stu-id="5eaf6-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="5eaf6-116">Información general sobre el control GroupBox</span><span class="sxs-lookup"><span data-stu-id="5eaf6-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="5eaf6-117">Información general sobre el control CheckBox</span><span class="sxs-lookup"><span data-stu-id="5eaf6-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="5eaf6-118">RadioButton (control)</span><span class="sxs-lookup"><span data-stu-id="5eaf6-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)
