---
title: 'Cómo: Reasignar controles existentes en un elemento primario diferente'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: d174492e380130ad35fbc20693e18416c48a50f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533840"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="82a72-102">Cómo: Reasignar controles existentes en un elemento primario diferente</span><span class="sxs-lookup"><span data-stu-id="82a72-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="82a72-103">Puede asignar controles que existen en el formulario a un nuevo control contenedor.</span><span class="sxs-lookup"><span data-stu-id="82a72-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82a72-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="82a72-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="82a72-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="82a72-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="82a72-106">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="82a72-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="82a72-107">Para reasignar los controles existentes en un elemento primario diferente</span><span class="sxs-lookup"><span data-stu-id="82a72-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="82a72-108">Arrastre tres controles <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="82a72-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="82a72-109">Colóquelos cerca entre sí, pero sin alinearlos.</span><span class="sxs-lookup"><span data-stu-id="82a72-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="82a72-110">En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="82a72-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="82a72-111">No arrastre el icono hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="82a72-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="82a72-112">Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="82a72-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="82a72-113">Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.</span><span class="sxs-lookup"><span data-stu-id="82a72-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="82a72-114">Haga clic y mantenga presionado el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="82a72-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="82a72-115">Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="82a72-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="82a72-116">Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="82a72-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="82a72-117">Suelte el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="82a72-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="82a72-118">Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="82a72-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a72-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a72-119">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="82a72-120">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="82a72-120">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="82a72-121">Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="82a72-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="82a72-122">Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="82a72-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
