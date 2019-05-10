---
title: Procedimiento para usar la información sobre herramientas en los controles ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: b009d19ed949edbd52ec02252ba1e2271e4cb738
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750561"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Procedimiento para usar la información sobre herramientas en los controles ToolStrip
Puede mostrar un <xref:System.Windows.Forms.ToolTip> para el <xref:System.Windows.Forms.ToolStrip> control que desee estableciendo el control <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> propiedad `true`.  
  
### <a name="to-display-a-tooltip"></a>Para mostrar una información sobre herramientas  
  
- Establecer el <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> propiedad del control a `true`.  
  
     El valor predeterminado de <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> es `true`y el valor predeterminado de <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> es `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>Para utilizar la propiedad ToolTipText para el texto de información sobre herramientas de ToolStripButton  
  
1. Establecer el <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> propiedad del botón en `true`.  
  
2. Establecer el <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> propiedad del botón en `false`.  
  
     El `AutoToolTip` propiedad es `true` de forma predeterminada para <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, y <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     Un <xref:System.Windows.Forms.ToolStripButton> usa su `Text` propiedad para el <xref:System.Windows.Forms.ToolTip> texto de forma predeterminada. Utilice este procedimiento para mostrar el texto personalizado en un <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.  
  
> [!NOTE]
>  Si establece <xref:System.Windows.Forms.ToolStripItemDisplayStyle> a <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> o <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, se mostrará ningún texto en el botón, pero sigue apareciendo la información sobre herramientas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
