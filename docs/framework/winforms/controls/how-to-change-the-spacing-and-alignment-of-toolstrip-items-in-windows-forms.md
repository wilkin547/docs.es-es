---
title: 'Cómo: Cambiar el espaciado y la alineación de los elementos ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182232"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="4cc5d-102">Cómo: Cambiar el espaciado y la alineación de los elementos ToolStrip en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cc5d-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="4cc5d-103">El <xref:System.Windows.Forms.ToolStrip> control admite completamente las características de <xref:System.Windows.Forms.ToolStripItem> diseño, como el tamaño, el <xref:System.Windows.Forms.ToolStrip>espaciado de los controles en <xref:System.Windows.Forms.ToolStrip>relación entre sí, la disposición de los controles en el , y el espaciado de los controles en relación con el archivo .</span><span class="sxs-lookup"><span data-stu-id="4cc5d-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="4cc5d-104">Dado que el <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> valor `true`predeterminado de la propiedad es <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> , `false`los controles se dimensionan automáticamente a menos que establezca la propiedad en .</span><span class="sxs-lookup"><span data-stu-id="4cc5d-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="4cc5d-105">Para cambiar manualmente el tamaño de un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="4cc5d-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="4cc5d-106">Establezca <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> la `false` propiedad en para el control asociado.</span><span class="sxs-lookup"><span data-stu-id="4cc5d-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="4cc5d-107">Establezca <xref:System.Windows.Forms.ToolStripItem.Size%2A> la propiedad de la <xref:System.Windows.Forms.ToolStripItem>manera que desee para el archivo .</span><span class="sxs-lookup"><span data-stu-id="4cc5d-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="4cc5d-108">Para establecer el espaciado de un ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="4cc5d-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="4cc5d-109">Inserte los valores deseados, <xref:System.Windows.Forms.ToolStripItem.Margin%2A> en píxeles, en la propiedad del control asociado.</span><span class="sxs-lookup"><span data-stu-id="4cc5d-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="4cc5d-110">Los valores <xref:System.Windows.Forms.ToolStripItem.Margin%2A> de la propiedad especifican el espaciado entre el elemento y los elementos adyacentes en este orden: Izquierda, Superior, Derecha e Inferior.</span><span class="sxs-lookup"><span data-stu-id="4cc5d-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="4cc5d-111">Para alinear un ToolStripItem al lado derecho de la ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4cc5d-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="4cc5d-112">Establezca <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> la <xref:System.Windows.Forms.ToolStripItemAlignment.Right> propiedad en para el control asociado.</span><span class="sxs-lookup"><span data-stu-id="4cc5d-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="4cc5d-113">De forma <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> predeterminada, <xref:System.Windows.Forms.ToolStripItemAlignment.Left>se establece en , que <xref:System.Windows.Forms.ToolStrip>alinea los controles al lado izquierdo del archivo .</span><span class="sxs-lookup"><span data-stu-id="4cc5d-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="4cc5d-114">Para organizar los elementos ToolStrip en El ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4cc5d-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="4cc5d-115">Establezca <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> la propiedad en <xref:System.Windows.Forms.ToolStripLayoutStyle> el valor que desee.</span><span class="sxs-lookup"><span data-stu-id="4cc5d-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4cc5d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4cc5d-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="4cc5d-117">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4cc5d-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="4cc5d-118">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4cc5d-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="4cc5d-119">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4cc5d-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
