---
title: Procedimiento para reasignar los controles existentes en un elemento primario diferente
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: a65b3c2b596a2d88ce4236aeadd86993bb268aa6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039787"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="159be-102">Procedimiento para reasignar los controles existentes en un elemento primario diferente</span><span class="sxs-lookup"><span data-stu-id="159be-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="159be-103">Puede asignar controles que existen en el formulario a un nuevo control contenedor.</span><span class="sxs-lookup"><span data-stu-id="159be-103">You can assign controls that exist on your form to a new container control.</span></span>

## <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="159be-104">Para reasignar los controles existentes en un elemento primario diferente</span><span class="sxs-lookup"><span data-stu-id="159be-104">To reassign existing controls to a different parent</span></span>

1. <span data-ttu-id="159be-105">Arrastre tres controles <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="159be-105">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>

     <span data-ttu-id="159be-106">Colóquelos cerca entre sí, pero sin alinearlos.</span><span class="sxs-lookup"><span data-stu-id="159be-106">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="159be-107">En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="159be-107">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>

     <span data-ttu-id="159be-108">No arrastre el icono hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="159be-108">Do not drag the icon onto the form.</span></span>

3. <span data-ttu-id="159be-109">Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="159be-109">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

     <span data-ttu-id="159be-110">Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.</span><span class="sxs-lookup"><span data-stu-id="159be-110">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="159be-111">Haga clic y mantenga presionado el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="159be-111">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="159be-112">Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="159be-112">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="159be-113">Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="159be-113">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="159be-114">Suelte el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="159be-114">Release the mouse button.</span></span>

     <span data-ttu-id="159be-115">Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="159be-115">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="159be-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="159be-116">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="159be-117">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="159be-117">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="159be-118">Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="159be-118">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="159be-119">Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="159be-119">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
