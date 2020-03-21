---
title: 'Cómo: Crear y establecer un renderizador personalizado para el ToolStrip Control'
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
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182403"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Cómo: Crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms
<xref:System.Windows.Forms.ToolStrip>los controles dan un fácil apoyo a los temas y estilos. Puede lograr una apariencia y un comportamiento completamente personalizados (aspecto y sensación) estableciendo la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propiedad o la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad en un representador personalizado.  
  
 Puede asignar representadores a <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip>cada <xref:System.Windows.Forms.ContextMenuStrip>control <xref:System.Windows.Forms.StatusStrip> individual, , , <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> o , o puede <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> utilizar <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>la propiedad para afectar a todos los objetos estableciendo la propiedad en .  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>devuelve <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo si <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> el `null`valor de no es .  
  
### <a name="to-create-a-custom-renderer"></a>Para crear un representador personalizado  
  
1. Amplíe <xref:System.Windows.Forms.ToolStripRenderer> la clase.  
  
2. Implemente la representación personalizada deseada reemplazando el *on...* members  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Para establecer el representador personalizado para que sea el representador actual  
  
1. Para establecer el representador personalizado para uno, <xref:System.Windows.Forms.ToolStrip>establezca la propiedad en <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> el representador personalizado.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. O bien, para establecer <xref:System.Windows.Forms.ToolStrip> el representador personalizado para <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> todas las clases <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> contenidas <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>en la aplicación: establezca la propiedad en el representador personalizado y establezca la propiedad en .  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Arquitectura del control ToolStrip](toolstrip-control-architecture.md)
- [Resumen de la tecnología ToolStrip](toolstrip-technology-summary.md)
