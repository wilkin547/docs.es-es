---
title: "C&#243;mo: Crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], barras de herramientas"
  - "barras de herramientas [Windows Forms], representar"
  - "ToolStrip (control) [Windows Forms], representación personalizada"
  - "ToolStrip (control) [Windows Forms], representar"
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms
Los controles <xref:System.Windows.Forms.ToolStrip> ofrecen una compatibilidad fácil para los temas y estilos.  Puede conseguir un aspecto y comportamiento personalizado completamente \(apariencia y percepción\) estableciendo tanto la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> como <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> en un representador personalizado.  
  
 Puede asignar representadores a cada control <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip> o <xref:System.Windows.Forms.StatusStrip> particular, o utilizar la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> que afecta a todos los objetos estableciendo la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=fullName> en <xref:System.Windows.Forms.ToolStripRenderMode?displayProperty=fullName>.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> sólo devuelve <xref:System.Windows.Forms.ToolStripRenderMode> si el valor de <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> no es `null`.  
  
### Para crear un representador personalizado  
  
1.  Extienda la clase <xref:System.Windows.Forms.ToolStripRenderer>.  
  
2.  Implemente la representación personalizada deseada invalidando los miembros *En…* adecuados  
  
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
  
     \[C\#\]  
  
    ```  
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
  
### Para establecer el representador personalizado que va a ser el representador actual  
  
1.  Para establecer el representador personalizado para un <xref:System.Windows.Forms.ToolStrip>, establezca la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> en el representador personalizado.  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.Renderer = new RedTextRenderer();  
  
    ```  
  
2.  O establezca el representador personalizado para todas las clases <xref:System.Windows.Forms.ToolStrip> contenidas en su aplicación: Establezca la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> en el representador personalizado y la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> en <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)   
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)