---
title: Procedimiento para crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms
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
ms.openlocfilehash: c354ace3a7d3ce43f549dd1295a85fbee004eb22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929739"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>Procedimiento para crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms
<xref:System.Windows.Forms.ToolStrip>los controles proporcionan una compatibilidad sencilla con los temas y estilos. Puede lograr una apariencia y un comportamiento completamente personalizados (aspecto y funcionamiento) estableciendo la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> propiedad o la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad en un representador personalizado.  
  
 Puede asignar representadores a cada control <xref:System.Windows.Forms.ToolStrip>individual <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip>,, o <xref:System.Windows.Forms.StatusStrip> , o puede usar la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> propiedad para afectar a todos los objetos estableciendo la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> propiedad en <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>Devuelve <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo si el valor de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> no `null`es.  
  
### <a name="to-create-a-custom-renderer"></a>Para crear un representador personalizado  
  
1. Extienda la <xref:System.Windows.Forms.ToolStripRenderer> clase.  
  
2. Implemente la representación personalizada deseada invalidando adecuado *en...* miembros  
  
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
  
1. Para establecer el representador personalizado para <xref:System.Windows.Forms.ToolStrip>uno, establezca <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> la propiedad en el representador personalizado.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. O bien, para establecer el representador <xref:System.Windows.Forms.ToolStrip> personalizado para todas las clases incluidas en la aplicación: Establezca la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> propiedad en el representador personalizado y establezca <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> la propiedad <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>en.  
  
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
