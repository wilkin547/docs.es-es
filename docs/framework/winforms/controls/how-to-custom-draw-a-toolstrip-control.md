---
title: 'Cómo: Dibujar un control ToolStrip de manera personalizada'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: a9f603efdb4b4a5f68154da9c6a8bd05b55b8f46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182224"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a>Cómo: Dibujar un control ToolStrip de manera personalizada
Los controles <xref:System.Windows.Forms.ToolStrip> tienen las siguientes clases de representación (dibujo) asociadas:  
  
- <xref:System.Windows.Forms.ToolStripSystemRenderer> proporciona la apariencia y el estilo del sistema operativo.  
  
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer> proporciona la apariencia y el estilo de Microsoft Office.  
  
- <xref:System.Windows.Forms.ToolStripRenderer> es la clase base abstracta para las otras dos clases de representación.  
  
 Para dibujar de forma personalizada un <xref:System.Windows.Forms.ToolStrip> (lo que también se conoce como dibujado por el propietario), puede invalidar una de las clases del representador y cambiar algún aspecto de la lógica de representación.  
  
 Los procedimientos siguientes describen distintos aspectos del dibujo personalizado.  
  
### <a name="to-switch-between-the-provided-renderers"></a>Para cambiar entre los representadores proporcionados  
  
- Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> en el valor <xref:System.Windows.Forms.ToolStripRenderMode> que desee.  
  
     Con <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, el <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> estático determina el representador de su aplicación. Los demás valores de <xref:System.Windows.Forms.ToolStripRenderMode> son <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> y <xref:System.Windows.Forms.ToolStripRenderMode.System>.  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a>Para cambiar los bordes de estilo Microsoft Office por rectos  
  
- Invalide <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, pero no llame a la clase base.  
  
> [!NOTE]
> Hay una versión de este método para <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
### <a name="to-change-the-professionalcolortable"></a>Para cambiar la clase ProfessionalColorTable  
  
- Invalide <xref:System.Windows.Forms.ProfessionalColorTable> y cambie los colores que desee.  
  
    ```vb  
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
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a>Para cambiar la representación de todos los controles ToolStrip de su aplicación  
  
1. Use la propiedad <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> para elegir uno de los representadores proporcionados.  
  
2. Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> para asignar un representador personalizado.  
  
3. Asegúrese de que <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> está establecido en el valor predeterminado de <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a>Para desactivar los colores de Microsoft Office para toda la aplicación  
  
- Establezca <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> en `false`.  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a>Para desactivar los colores de Microsoft Office para un control ToolStrip  
  
- Use código similar al ejemplo de código siguiente.  
  
    ```vb  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
    ```  
  
    ```csharp  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [Controles compatibles con dibujos propietarios integrados](controls-with-built-in-owner-drawing-support.md)
- [Cómo: Crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
