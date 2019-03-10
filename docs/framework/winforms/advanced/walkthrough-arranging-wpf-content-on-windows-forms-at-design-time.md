---
title: 'Tutorial: Organizar el contenido WPF en Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: 0738d1522c8ade8f026a3bf69fbff0bc2c2d6d85
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712466"
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a>Tutorial: Organizar el contenido WPF en Windows Forms en tiempo de diseño
Este tutorial muestra cómo usar las características de diseño de Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation (WPF).

 En este tutorial, realizará las tareas siguientes:

-   Crear el proyecto.

-   Crear el control WPF.

-   Hospedar controles WPF en un panel de diseño.

-   Usar líneas de ajuste para alinear os controles WPF.

-   Delimitar y acoplar controles WPF.

> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   Visual Studio 2012.  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `ArrangeElementHost`.  
  
## <a name="creating-the-wpf-control"></a>Crear el control WPF  
 Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.  
  
#### <a name="to-create-wpf-controls"></a>Para crear controles WPF  
  
1.  Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto. Use el nombre predeterminado del tipo de control, `UserControl1.xaml`. Para obtener más información, vea [Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado. Para obtener más información, vea [Cómo: Seleccionar y mover elementos en la superficie de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).  
  
3.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.  
  
4.  Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Blue`.  
  
5.  Compile el proyecto.  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a>Hospedar controles WPF en un panel de diseño  
 Puede usar controles WPF en paneles de diseño de la misma forma que usa otros controles de Windows Forms.  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a>Para hospedar controles WPF en un panel de diseño  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.TableLayoutPanel> al formulario.  
  
3.  En el <xref:System.Windows.Forms.TableLayoutPanel> panel de etiquetas inteligentes del control, seleccione **quitar la última fila**.  
  
4.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho y alto mayor.  
  
5.  En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en la primera celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
6.  En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear otra instancia en la segunda celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
7.  En el **esquema del documento** ventana, seleccione `tableLayoutPanel1`. Para obtener más información, consulte [ventana Esquema del documento](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).  
  
8.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad `10, 10, 10, 10`.  
  
     Ambos controles <xref:System.Windows.Forms.Integration.ElementHost> cambian de tamaño para ajustarse al nuevo diseño.  
  
## <a name="using-snaplines-to-align-wpf-controls"></a>Usar líneas de ajuste para alinear controles WPF  
 Las líneas de ajuste permiten alinear fácilmente los controles en un formulario. Puede usar líneas de ajuste para alinear también controles WPF. Para obtener más información, vea [Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a>Para usar líneas de ajuste para alinear controles WPF  
  
1.  Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario y colóquelo en el espacio debajo el <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost3`.  
  
2.  Use las líneas de ajuste para alinear el borde izquierdo de `elementHost3` con el borde izquierdo del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Use las líneas de ajuste para ajustar el tamaño de `elementHost3` al mismo ancho que el control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
4.  Mueva `elementHost3` hacia el control <xref:System.Windows.Forms.TableLayoutPanel> hasta que aparezca una línea de ajuste central entre los controles.  
  
5.  En el **propiedades** ventana, establezca el valor de la propiedad Margin en `20, 20, 20, 20`.  
  
6.  Aleje `elementHost3` del control <xref:System.Windows.Forms.TableLayoutPanel> hasta que la línea de ajuste central aparezca de nuevo. Ahora, la línea de ajuste central indica un margen de 20.  
  
7.  Mueva `elementHost3` hacia la derecha, hasta que su borde izquierdo quede alineado con el borde izquierdo de `elementHost1`.  
  
8.  Cambie el ancho de `elementHost3` hasta que su borde derecho quede alineado con el borde derecho de `elementHost2`.  
  
## <a name="anchoring-and-docking-wpf-controls"></a>Delimitar y acoplar controles WPF  
 La delimitación y el acoplamiento de un control WPF hospedado en un formulario se comportan igual que los de otros controles de Windows Forms.  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a>Para delimitar y acoplar controles WPF  
  
1.  Seleccione `elementHost1`.  
  
2.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad **superior, inferior, izquierda, derecha**.  
  
3.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un tamaño mayor.  
  
     El control `elementHost1` cambia de tamaño para llenar la celda.  
  
4.  Seleccione `elementHost2`.  
  
5.  En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     El control `elementHost2` cambia de tamaño para llenar la celda.  
  
6.  Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
7.  Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Top>.  
  
8.  Seleccione `elementHost3`.  
  
9. Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     El control `elementHost3` cambia de tamaño para llenar el espacio restante en el formulario.  
  
10. Cambie de tamaño el formulario.  
  
     Los tres controles <xref:System.Windows.Forms.Integration.ElementHost> ajustan su tamaño correctamente.  
  
     Para obtener más información, vea [Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Cómo: Alinear un Control con los bordes de formularios en tiempo de diseño](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Migración e interoperabilidad](../../wpf/advanced/migration-and-interoperability.md)
- [Utilizar controles WPF](using-wpf-controls.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
