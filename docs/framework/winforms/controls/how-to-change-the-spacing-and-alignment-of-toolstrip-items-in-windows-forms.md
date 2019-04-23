---
title: Procedimiento para cambiar el espaciado y la alineación de los elementos ToolStrip en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: bed943466348447e30947c170e27027f324342c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323179"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="669fa-102">Procedimiento para cambiar el espaciado y la alineación de los elementos ToolStrip en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="669fa-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="669fa-103">El <xref:System.Windows.Forms.ToolStrip> control es totalmente compatible con las características de diseño, como cambiar el tamaño, el espaciado de <xref:System.Windows.Forms.ToolStripItem> controles relacionados entre sí, la disposición de los controles en el <xref:System.Windows.Forms.ToolStrip>y el espaciado de los controles relativa a la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="669fa-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="669fa-104">Dado que el valor predeterminado de la <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> propiedad es `true`, controles de tamaño se ajusta automáticamente a menos que establezca el <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> propiedad a `false`.</span><span class="sxs-lookup"><span data-stu-id="669fa-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="669fa-105">Para cambiar manualmente el tamaño de un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="669fa-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="669fa-106">Establecer el <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> propiedad `false` para el control asociado.</span><span class="sxs-lookup"><span data-stu-id="669fa-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="669fa-107">Establecer el <xref:System.Windows.Forms.ToolStripItem.Size%2A> como quiera para el asociado de la propiedad <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="669fa-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="669fa-108">Para establecer el espaciado de un elemento ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="669fa-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="669fa-109">Inserte los valores deseados, en píxeles, en el <xref:System.Windows.Forms.ToolStripItem.Margin%2A> propiedad del control asociado.</span><span class="sxs-lookup"><span data-stu-id="669fa-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="669fa-110">Los valores de la <xref:System.Windows.Forms.ToolStripItem.Margin%2A> propiedad especifica el espaciado entre el elemento y los elementos adyacentes en este orden: Izquierda, superior, derecho e inferior.</span><span class="sxs-lookup"><span data-stu-id="669fa-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="669fa-111">Para alinear un control ToolStripItem en el lado derecho de la franja de herramientas</span><span class="sxs-lookup"><span data-stu-id="669fa-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="669fa-112">Establecer el <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> propiedad <xref:System.Windows.Forms.ToolStripItemAlignment.Right> para el control asociado.</span><span class="sxs-lookup"><span data-stu-id="669fa-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="669fa-113">De forma predeterminada, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> está establecido en <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, lo que alinea los controles en el lado izquierdo de la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="669fa-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="669fa-114">Para organizar los elementos ToolStrip en el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="669fa-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="669fa-115">Establecer el <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> en el valor de <xref:System.Windows.Forms.ToolStripLayoutStyle> que desee.</span><span class="sxs-lookup"><span data-stu-id="669fa-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="669fa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="669fa-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="669fa-117">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="669fa-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="669fa-118">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="669fa-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="669fa-119">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="669fa-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
