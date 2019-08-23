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
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Procedimiento para usar la información sobre herramientas en los controles ToolStrip
Puede mostrar un <xref:System.Windows.Forms.ToolTip> para el <xref:System.Windows.Forms.ToolStrip> control que desee estableciendo la propiedad del <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> control en `true`.  
  
### <a name="to-display-a-tooltip"></a>Para mostrar una información sobre herramientas  
  
- Establezca la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> propiedad del control en `true`.  
  
     El valor predeterminado de <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> es `true`, y el valor predeterminado de <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> es `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>Para usar la propiedad ToolTipText para el texto de información sobre herramientas de un ToolStripButton  
  
1. Establezca la <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> propiedad del botón en `true`.  
  
2. Establezca la <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> propiedad del botón en `false`.  
  
     La `AutoToolTip` propiedad es `true` de forma predeterminada <xref:System.Windows.Forms.ToolStripButton>para <xref:System.Windows.Forms.ToolStripDropDownButton>, y <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     Un <xref:System.Windows.Forms.ToolStripButton> utiliza su `Text` propiedad para el <xref:System.Windows.Forms.ToolTip> texto de forma predeterminada. Utilice este procedimiento para mostrar texto personalizado en <xref:System.Windows.Forms.ToolStripButton>. <xref:System.Windows.Forms.ToolTip>  
  
> [!NOTE]
> Si establece <xref:System.Windows.Forms.ToolStripItemDisplayStyle> en <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no aparecerá ningún texto en el botón, pero la información sobre herramientas sigue apareciendo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
