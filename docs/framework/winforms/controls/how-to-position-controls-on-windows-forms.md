---
title: Filtrar Controles de posición en Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 0503deb3fbb6dc157d8796580ece847bbfb8edfb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723106"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Procedimiento Controles de posición en Windows Forms
Para colocar los controles, utilizar el Diseñador de Windows Forms o especifique el <xref:System.Windows.Forms.Control.Location%2A> propiedad.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Para colocar un control en la superficie de diseño del Diseñador de Windows Forms  
  
-   Arrastre el control a la ubicación adecuada con el mouse.  
  
    > [!NOTE]
    >  Seleccione el control y muévalo teclas con la flecha para colocarlo con más precisión. Además, *las guías de alineación* le ayudarán a colocar controles en el formulario con precisión. Para obtener más información, vea [Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### <a name="to-position-a-control-using-the-properties-window"></a>Para colocar un control mediante la ventana Propiedades  
  
1.  Haga clic en el control que desea colocar.  
  
2.  En el **propiedades** ventana, escriba valores para el <xref:System.Windows.Forms.Control.Location%2A> propiedad, separados por comas, para colocar el control dentro de su contenedor.  
  
     El primer número (X) es la distancia desde el borde izquierdo del contenedor; el segundo número (Y) es la distancia desde el borde superior del área de contenedor, medido en píxeles.  
  
    > [!NOTE]
    >  Puede expandir el <xref:System.Windows.Forms.Control.Location%2A> propiedad al tipo el **X** y **Y** valores individualmente.  
  
### <a name="to-position-a-control-programmatically"></a>Para colocar un control mediante programación  
  
1.  Establecer el <xref:System.Windows.Forms.Control.Location%2A> propiedad del control a un <xref:System.Drawing.Point>.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Cambie la coordenada X de la ubicación del control mediante la <xref:System.Windows.Forms.Control.Left%2A> subpropiedades.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>Para incrementar la ubicación de un control mediante programación  
  
1.  Establecer el <xref:System.Windows.Forms.Control.Left%2A> subpropiedad para incrementar la coordenada X del control.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Use el <xref:System.Windows.Forms.Control.Location%2A> propiedad para establecer un control X e Y se coloca al mismo tiempo. Para establecer una posición individualmente, utilice el control <xref:System.Windows.Forms.Control.Left%2A> (**X**) o <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subpropiedades. No intente establecer implícitamente las coordenadas X e Y de la <xref:System.Drawing.Point> estructura que representa la ubicación del botón, porque esta estructura contiene una copia de las coordenadas del botón.  
  
## <a name="see-also"></a>Vea también
- [Controles de formularios Windows Forms](index.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Organizar controles en formularios Windows Forms](arranging-controls-on-windows-forms.md)
- [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
- [Controles de formularios Windows Forms por función](windows-forms-controls-by-function.md)
- [Cómo: Establecer la ubicación de pantalla de Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
