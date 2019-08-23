---
title: Procedimiento para usar la información sobre herramientas en los controles ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939731"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="0ce53-102">Procedimiento para usar la información sobre herramientas en los controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0ce53-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="0ce53-103">Puede mostrar un <xref:System.Windows.Forms.ToolTip> para el <xref:System.Windows.Forms.ToolStrip> control que desee estableciendo la propiedad del <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> control en `true`.</span><span class="sxs-lookup"><span data-stu-id="0ce53-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="0ce53-104">Para mostrar una información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="0ce53-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="0ce53-105">Establezca la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> propiedad del control en `true`.</span><span class="sxs-lookup"><span data-stu-id="0ce53-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="0ce53-106">El valor predeterminado de <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> es `true`, y el valor predeterminado de <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="0ce53-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="0ce53-107">Para usar la propiedad ToolTipText para el texto de información sobre herramientas de un ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="0ce53-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="0ce53-108">Establezca la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> propiedad del botón en `true`.</span><span class="sxs-lookup"><span data-stu-id="0ce53-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="0ce53-109">Establezca la <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> propiedad del botón en `false`.</span><span class="sxs-lookup"><span data-stu-id="0ce53-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="0ce53-110">La `AutoToolTip` propiedad es `true` de forma predeterminada <xref:System.Windows.Forms.ToolStripButton>para <xref:System.Windows.Forms.ToolStripDropDownButton>, y <xref:System.Windows.Forms.ToolStripSplitButton>.</span><span class="sxs-lookup"><span data-stu-id="0ce53-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="0ce53-111">Un <xref:System.Windows.Forms.ToolStripButton> utiliza su `Text` propiedad para el <xref:System.Windows.Forms.ToolTip> texto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0ce53-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="0ce53-112">Utilice este procedimiento para mostrar texto personalizado en <xref:System.Windows.Forms.ToolStripButton>. <xref:System.Windows.Forms.ToolTip></span><span class="sxs-lookup"><span data-stu-id="0ce53-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ce53-113">Si establece <xref:System.Windows.Forms.ToolStripItemDisplayStyle> en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no aparecerá ningún texto en el botón, pero la información sobre herramientas sigue apareciendo.</span><span class="sxs-lookup"><span data-stu-id="0ce53-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce53-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ce53-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="0ce53-115">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0ce53-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
