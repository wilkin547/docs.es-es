---
title: Filtrar Crear y establecer a un representador personalizado para el Control ToolStrip de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 379cb8862ce5dda5cfffc625cc72906cf6a2c305
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721013"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Filtrar Crear y establecer a un representador personalizado para el Control ToolStrip de Windows Forms
<xref:System.Windows.Forms.ToolStrip> controles ofrecen una compatibilidad fácil para los temas y estilos. Puede conseguir el aspecto y comportamiento (apariencia) completamente personalizado estableciendo la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propiedad o el <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad a un representador personalizado.  
  
 Puede asignar representadores a cada persona <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, o <xref:System.Windows.Forms.StatusStrip> control, o bien puede usar el <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> propiedad afecte a todos los objetos estableciendo el <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> propiedad a <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Devuelve <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo si el valor de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> no `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Para crear a un representador personalizado  
  
1.  Ampliar la <xref:System.Windows.Forms.ToolStripRenderer> clase.  
  
2.  Implemente la representación personalizada deseada invalidando adecuado *en...* miembros  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Para establecer el representador personalizado para ser el representador actual  
  
1.  Para establecer el representador personalizado para una <xref:System.Windows.Forms.ToolStrip>, establezca el <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propiedad en el representador personalizado.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  O bien para establecer el representador personalizado para todos los <xref:System.Windows.Forms.ToolStrip> las clases contenidas en la aplicación: Establecer el <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad al representador personalizado y establezca el <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> propiedad <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)
- [Resumen de la tecnología ToolStrip](toolstrip-technology-summary.md)
