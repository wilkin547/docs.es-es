---
title: 'Cómo: crear y establecer un representador personalizado para el control ToolStrip'
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
ms.openlocfilehash: ad5ced42754fba6a714452220dd824c4f54fb5e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743409"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Cómo: Crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms
los controles de <xref:System.Windows.Forms.ToolStrip> proporcionan una compatibilidad sencilla con los temas y los estilos. Puede lograr una apariencia y un comportamiento completamente personalizados (aspecto y funcionamiento) estableciendo la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> o la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> en un representador personalizado.  
  
 Puede asignar representadores a cada <xref:System.Windows.Forms.ToolStrip>individual, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>o <xref:System.Windows.Forms.StatusStrip> control, o puede usar la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> para afectar a todos los objetos estableciendo la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> en <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> devuelve <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo si el valor de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> no está `null`.  
  
### <a name="to-create-a-custom-renderer"></a>Para crear un representador personalizado  
  
1. Extienda la clase <xref:System.Windows.Forms.ToolStripRenderer>.  
  
2. Implemente la representación personalizada deseada invalidando adecuado *en...* members  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>Para establecer que el representador personalizado sea el representador actual  
  
1. Para establecer el representador personalizado para un <xref:System.Windows.Forms.ToolStrip>, establezca la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> en el representador personalizado.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. O bien, para establecer el representador personalizado para todas las clases de <xref:System.Windows.Forms.ToolStrip> incluidas en la aplicación: establezca la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> en el representador personalizado y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> en <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
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
