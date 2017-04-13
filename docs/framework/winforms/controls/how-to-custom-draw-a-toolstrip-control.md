---
title: "C&#243;mo: Dibujar un control ToolStrip de manera personalizada | Microsoft Docs"
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
  - "dibujo personalizado"
  - "dibujar, personalizado"
  - "dibujar, propietario"
  - "ejemplos [Windows Forms], barras de herramientas"
  - "dibujo del propietario"
  - "ProfessionalColorTable (clase), reemplazar"
  - "RenderMode (propiedad)"
  - "barras de herramientas [Windows Forms], cambiar colores"
  - "barras de herramientas [Windows Forms], dibujo personalizado"
  - "ToolStrip (control) [Windows Forms], cambiar colores"
  - "ToolStrip (control) [Windows Forms], dibujar"
  - "ToolStripProfessionalRenderer (clase)"
  - "ToolStripRenderer (clase)"
  - "ToolStripRenderMode (clase)"
  - "ToolStripSystemRenderer (clase)"
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Dibujar un control ToolStrip de manera personalizada
Los controles <xref:System.Windows.Forms.ToolStrip> tienen las siguientes clases de representación \(dibujo\) asociadas:  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> proporciona la apariencia y el estilo del sistema operativo.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> proporciona la apariencia y el estilo de Microsoft Office.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> es la clase base abstracta para las otras dos clases de representación.  
  
 Para dibujar de forma personalizada un <xref:System.Windows.Forms.ToolStrip> \(lo que también se conoce como dibujado por el propietario\), puede invalidar una de las clases del representador y cambiar algún aspecto de la lógica de representación.  
  
 Los procedimientos siguientes describen distintos aspectos del dibujo personalizado.  
  
### Para cambiar entre los representadores proporcionados  
  
-   Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> en el valor <xref:System.Windows.Forms.ToolStripRenderMode> que desee.  
  
     Con <xref:System.Windows.Forms.ToolStripRenderMode>, el <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> estático determina el representador de su aplicación.  Los demás valores de <xref:System.Windows.Forms.ToolStripRenderMode> son <xref:System.Windows.Forms.ToolStripRenderMode>, <xref:System.Windows.Forms.ToolStripRenderMode> y <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
### Para cambiar los bordes de estilo Microsoft Office por rectos  
  
-   Invalide <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=fullName>, pero no llame a la clase base.  
  
> [!NOTE]
>  Hay una versión de este método para <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
### Para cambiar la clase ProfessionalColorTable  
  
-   Invalide <xref:System.Windows.Forms.ProfessionalColorTable> y cambie los colores que desee.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable   
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
  
    ```  
  
### Para cambiar la representación de todos los controles ToolStrip de su aplicación  
  
1.  Use la propiedad <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=fullName> para elegir uno de los representadores proporcionados.  
  
2.  Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> para asignar un representador personalizado.  
  
3.  Asegúrese de que <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=fullName> está establecido en el valor predeterminado de <xref:System.Windows.Forms.ToolStripRenderMode>.  
  
### Para desactivar los colores de Microsoft Office para toda la aplicación  
  
-   Establezca <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=fullName> en `false`.  
  
### Para desactivar los colores de Microsoft Office para un control ToolStrip  
  
-   Use código similar al ejemplo de código siguiente.  
  
     \[Visual Basic\]  
  
    ```  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
  
    ```  
  
     \[C\#\]  
  
    ```  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 <xref:System.Windows.Forms.ToolStripRenderer>   
 [Controles compatibles con dibujos propietarios integrados](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)   
 [Cómo: Crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)