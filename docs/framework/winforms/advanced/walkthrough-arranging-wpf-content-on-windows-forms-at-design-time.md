---
title: "Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de dise&#241;o | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "interoperabilidad [WPF]"
  - "Windows Forms, delimitar y acoplar contenido WPF"
  - "Windows Forms, organizar contenido de WPF en tiempo de diseño"
  - "contenido WPF [Windows Forms], organizar en tiempo de diseño"
  - "contenido WPF, hospedar en Windows Forms"
  - "control de usuario WPF [Windows Forms], hospedar en un panel de diseño"
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de dise&#241;o
Este tutorial muestra cómo usar las características de diseño de Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation \(WPF\).  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear el control WPF.  
  
-   Hospedar controles WPF en un panel de diseño.  
  
-   Usar líneas de ajuste para alinear os controles WPF.  
  
-   Delimitar y acoplar controles WPF.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, se admiten solo proyectos de C\# y Visual Basic.  
  
#### Para crear el proyecto  
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C\# llamado `ArrangeElementHost`.  
  
## Crear el control WPF  
 Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.  
  
#### Para crear controles WPF  
  
1.  Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto.  Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.  Para obtener más información, consulte [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.  Para obtener más información, consulte [Cómo: Seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/es-es/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  En la ventana **Propiedades**, establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en `200`.  
  
4.  Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Azul`.  
  
5.  Compile el proyecto.  
  
## Hospedar controles WPF en un panel de diseño  
 Puede usar controles WPF en paneles de diseño de la misma forma que usa otros controles de Windows Forms.  
  
#### Para hospedar controles WPF en un panel de diseño  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> al formulario.  
  
3.  En el panel de etiquetas inteligentes del control <xref:System.Windows.Forms.TableLayoutPanel>, seleccione **Quitar la última fila**.  
  
4.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho y alto mayor.  
  
5.  En el **Cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en la primera celda del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
6.  En el **Cuadro de herramientas**, haga doble clic en `UserControl1` para crear otra instancia de la segunda celda del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
7.  En la ventana **Esquema del documento**, seleccione `tableLayoutPanel1`.  Para obtener más información, consulte [Document Outline Window](http://msdn.microsoft.com/es-es/9054f2bc-f6f8-4242-9fe0-be71089b12f8).  
  
8.  En la ventana **Propiedades**, establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Padding%2A> en `10, 10, 10, 10`.  
  
     Ambos controles <xref:System.Windows.Forms.Integration.ElementHost> cambian de tamaño para ajustarse al nuevo diseño.  
  
## Usar líneas de ajuste para alinear controles WPF  
 Las líneas de ajuste permiten alinear fácilmente los controles en un formulario.  Puede usar líneas de ajuste para alinear también controles WPF.  Para obtener más información, consulte [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
#### Para usar líneas de ajuste para alinear controles WPF  
  
1.  En el **Cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario y colóquela en el espacio debajo del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost3`.  
  
2.  Use las líneas de ajuste para alinear el borde izquierdo de `elementHost3` con el borde izquierdo del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Use las líneas de ajuste para ajustar el tamaño de `elementHost3` al mismo ancho que el control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
4.  Mueva `elementHost3` hacia el control <xref:System.Windows.Forms.TableLayoutPanel> hasta que aparezca una línea de ajuste central entre los controles.  
  
5.  En la ventana **Propiedades**, establezca el valor de la propiedad Margin en `20, 20, 20, 20`.  
  
6.  Aleje `elementHost3` del control <xref:System.Windows.Forms.TableLayoutPanel> hasta que la línea de ajuste central aparezca de nuevo.  Ahora, la línea de ajuste central indica un margen de 20.  
  
7.  Mueva `elementHost3` hacia la derecha, hasta que su borde izquierdo quede alineado con el borde izquierdo de `elementHost1`.  
  
8.  Cambie el ancho de `elementHost3` hasta que su borde derecho quede alineado con el borde derecho de `elementHost2`.  
  
## Delimitar y acoplar controles WPF  
 La delimitación y el acoplamiento de un control WPF hospedado en un formulario se comportan igual que los de otros controles de Windows Forms.  
  
#### Para delimitar y acoplar controles WPF  
  
1.  Seleccione `elementHost1`.  
  
2.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> en **Superior, Inferior, Izquierda, Derecha**.  
  
3.  Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un tamaño mayor.  
  
     El control `elementHost1` cambia de tamaño para llenar la celda.  
  
4.  Seleccione `elementHost2`.  
  
5.  En la ventana **Propiedades**, establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
     El control `elementHost2` cambia de tamaño para llenar la celda.  
  
6.  Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
7.  Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
8.  Seleccione `elementHost3`.  
  
9. Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
     El control `elementHost3` cambia de tamaño para llenar el espacio restante en el formulario.  
  
10. Cambie de tamaño el formulario.  
  
     Los tres controles <xref:System.Windows.Forms.Integration.ElementHost> ajustan su tamaño correctamente.  
  
     Para obtener más información, consulte [Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)