---
title: Procedimiento Cambiar el diseño de un Control DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: 3389daa6383444b48faab4c5383b281e44349bce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625606"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a><span data-ttu-id="1b065-102">Procedimiento Cambiar el diseño de un Control DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="1b065-102">How to: Change the Layout of a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="1b065-103">El <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control puede mostrarse en una vertical (elementos de desplazamiento vertical) o en horizontal (elementos de desplazamiento horizontal) orientación.</span><span class="sxs-lookup"><span data-stu-id="1b065-103">The <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control can be displayed in either a vertical (items scroll vertically) or horizontal (items scroll horizontally) orientation.</span></span> <span data-ttu-id="1b065-104">Puede cambiar la orientación en tiempo de diseño o en tiempo de ejecución, cambie el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1b065-104">You can change the orientation at design time or at run time by changing the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property.</span></span> <span data-ttu-id="1b065-105">Si cambia el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad en tiempo de ejecución, también puede cambiar el tamaño de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> y la posición de los controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="1b065-105">If you change the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property at run time, you may also want to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and reposition the child controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b065-106">Si cambia la posición de los controles en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> en tiempo de ejecución, deberá llamar a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> y <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> métodos al principio y al final del bloque de código que cambia de posición los controles.</span><span class="sxs-lookup"><span data-stu-id="1b065-106">If you reposition controls on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> at run time, you will need to call the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> and <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> methods at the beginning and end of the code block that repositions the controls.</span></span>  
  
### <a name="to-change-the-layout-at-design-time"></a><span data-ttu-id="1b065-107">Para cambiar el diseño en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="1b065-107">To change the layout at design time</span></span>  
  
1.  <span data-ttu-id="1b065-108">En el Diseñador de Windows Forms, seleccione el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="1b065-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b065-109">Debe seleccionar el borde exterior de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control haciendo clic en la región inferior del control, no en la esquina superior <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> región.</span><span class="sxs-lookup"><span data-stu-id="1b065-109">You must select the outer border of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control by clicking in the lower region of the control, not in the upper <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> region.</span></span>  
  
2.  <span data-ttu-id="1b065-110">En la ventana Propiedades, establezca la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> propiedad como <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> o <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="1b065-110">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property to either <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> or <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.</span></span>  
  
### <a name="to-change-the-layout-at-run-time"></a><span data-ttu-id="1b065-111">Para cambiar el diseño en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1b065-111">To change the layout at run time</span></span>  
  
1.  <span data-ttu-id="1b065-112">Agregue el código siguiente a un botón o menú `Click` controlador de eventos:</span><span class="sxs-lookup"><span data-stu-id="1b065-112">Add the following code to a button or menu `Click` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  <span data-ttu-id="1b065-113">En la mayoría de los casos, desea agregar código similar al que se muestra en la sección ejemplo para cambiar el tamaño de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> y reorganizar los controles para ajustarse a la nueva orientación.</span><span class="sxs-lookup"><span data-stu-id="1b065-113">In most cases, you will want to add code similar to that shown in the Example section to resize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> and rearrange controls to fit the new orientation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b065-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b065-114">Example</span></span>  
 <span data-ttu-id="1b065-115">El ejemplo siguiente muestra cómo responder a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> eventos en un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="1b065-115">The following example shows how to respond to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> event in an event handler.</span></span> <span data-ttu-id="1b065-116">En este ejemplo requiere que haya un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control denominado `DataRepeater1` en un formulario y que su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contienen dos <xref:System.Windows.Forms.TextBox> controles denominados `TextBox1` y `TextBox2`.</span><span class="sxs-lookup"><span data-stu-id="1b065-116">This example requires that you have a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control named `DataRepeater1` on a form and that its <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> contain two <xref:System.Windows.Forms.TextBox> controls named `TextBox1` and `TextBox2`.</span></span>  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1b065-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b065-117">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [<span data-ttu-id="1b065-118">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="1b065-118">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="1b065-119">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="1b065-119">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="1b065-120">Cómo: Cambiar la apariencia de un Control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="1b065-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
