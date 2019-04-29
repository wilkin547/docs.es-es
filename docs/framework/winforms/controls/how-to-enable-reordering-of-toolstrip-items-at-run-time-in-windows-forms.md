---
title: Procedimiento Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en Windows Forms
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
ms.openlocfilehash: daff9d6d351db514d552225853f977775f8e3204
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941445"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Procedimiento Habilitar la reordenación de elementos ToolStrip en tiempo de ejecución en Windows Forms
Puede permitir que el usuario desea reorganizar <xref:System.Windows.Forms.ToolStripItem> controla en el <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>Para habilitar la reorganización de ToolStripItem en tiempo de ejecución  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> en `true`. De forma predeterminada, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> es `false`.  
  
     En tiempo de ejecución, el usuario mantiene presionada la tecla ALT y el botón primario del mouse para arrastrar un <xref:System.Windows.Forms.ToolStripItem> a una ubicación diferente en el <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)
- [Resumen de la tecnología ToolStrip](toolstrip-technology-summary.md)
