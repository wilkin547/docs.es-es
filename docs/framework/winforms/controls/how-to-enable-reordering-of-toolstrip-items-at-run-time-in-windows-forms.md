---
title: 'Cómo: Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en un formulario Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: e3f4510071c83b9d1baab358d4962b54fb7361ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531627"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Cómo: Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en un formulario Windows Forms
Puede permitir al usuario para volver a organizar <xref:System.Windows.Forms.ToolStripItem> a los controles de la <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>Para habilitar la reorganización de ToolStripItem en tiempo de ejecución  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> en `true`. De forma predeterminada, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> es `false`.  
  
     En tiempo de ejecución, el usuario mantiene presionada la tecla ALT y el botón primario del mouse para arrastrar un <xref:System.Windows.Forms.ToolStripItem> a una ubicación diferente en el <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>  
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
