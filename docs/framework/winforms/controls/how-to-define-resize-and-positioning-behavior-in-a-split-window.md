---
title: Filtrar para definir el comportamiento de cambio de tamaño y colocación de una ventana dividida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 4ed1d2a5230502bc598906da0db5164396986e66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217073"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Filtrar para definir el comportamiento de cambio de tamaño y colocación de una ventana dividida
Los paneles de la <xref:System.Windows.Forms.SplitContainer> control se prestan bien a la que se va a cambiar el tamaño y manipulados por usuarios. Sin embargo, habrá veces cuando desee controlar mediante programación el divisor, donde se coloca y hasta qué punto se puede mover.  
  
 El <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad y otras propiedades en el <xref:System.Windows.Forms.SplitContainer> control proporcionan un control preciso sobre el comportamiento de la interfaz de usuario para satisfacer sus necesidades. Estas propiedades se muestran en la tabla siguiente.  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> propiedad|Determina si el divisor es móvil mediante el teclado o mouse.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> propiedad|Determina la distancia en píxeles desde el borde izquierdo o superior a la barra de división movible.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad|Determina la distancia mínima en píxeles, que el usuario puede mover el divisor.|  
  
 El ejemplo siguiente se modifica el <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad para crear un efecto "divisor con ajuste"; cuando el usuario arrastra el separador, incrementa en unidades de 10 píxeles en lugar de con el valor predeterminado 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>Para definir el comportamiento de cambio de tamaño de SplitContainer  
  
1.  En un procedimiento, establezca el <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad tenga el tamaño deseado, por lo que se consigue el comportamiento 'ajuste' del divisor.  
  
     En el ejemplo de código siguiente dentro del formulario <xref:System.Windows.Forms.Form.Load> evento, el divisor dentro del <xref:System.Windows.Forms.SplitContainer> control se establece para saltar 10 píxeles cuando arrastra.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     (Visual C#) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Mover el divisor ligeramente a la izquierda o derecha no tendrá ningún efecto apreciable; Sin embargo, cuando el puntero del mouse deja de 10 píxeles en cualquier dirección, el divisor se ajustará a la nueva posición.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
