---
title: "Tutorial: Organizar controles de formularios Windows Forms en WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "organizar controles"
  - "aplicaciones híbridas [interoperabilidad con WPF]"
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 28
---
# Tutorial: Organizar controles de formularios Windows Forms en WPF
En este tutorial se muestra cómo utilizar las características de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para organizar controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en una aplicación híbrida.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto.  
  
-   Utilizar la configuración de diseño predeterminada.  
  
-   Ajustar el tamaño al contenido.  
  
-   Utilizar posiciones absolutas.  
  
-   Especificar explícitamente el tamaño.  
  
-   Establecer las propiedades de diseño.  
  
-   Entender las limitaciones del orden z.  
  
-   Acoplamiento.  
  
-   Establecer la visibilidad.  
  
-   Hospedar un control que no se ajusta.  
  
-   Cambiar la escala.  
  
-   Girar.  
  
-   Establecer relleno y márgenes.  
  
-   Utilizar contenedores de diseño dinámico.  
  
 Para ver una lista de código completa de las tareas mostradas en este tutorial, vea [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).  
  
 Cuando termine, comprenderá las características de diseño de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en aplicaciones basadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Crear el proyecto  
  
#### Para crear y configurar el proyecto  
  
1.  Cree un proyecto de aplicación de WPF denominado `WpfLayoutHostingWf`.  
  
2.  En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  Haga doble clic en MainWindow.xaml para abrirlo en la vista XAML.  
  
4.  En el elemento <xref:System.Windows.Window>, agregue la siguiente asignación de espacio de nombres [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  En el elemento <xref:System.Windows.Controls.Grid>, establezca la propiedad <xref:System.Windows.Controls.Grid.ShowGridLines%2A> en `true` y defina cinco filas y tres columnas.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## Utilizar la configuración de diseño predeterminada  
 De manera predeterminada, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> administra el diseño para el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado.  
  
#### Para utilizar la configuración de diseño predeterminada  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  Aparecerá el control <xref:System.Windows.Forms.Button?displayProperty=fullName> de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en el objeto <xref:System.Windows.Controls.Canvas>.  El control hospedado cambiará de tamaño de acuerdo con su contenido; el tamaño del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se ajustará para alojar el control hospedado.  
  
## Ajustar el tamaño al contenido  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantiza que el tamaño del control hospedado se ajuste para mostrar correctamente su contenido.  
  
#### Para ajustar el tamaño al contenido  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  El tamaño de los dos nuevos controles de botón se ajusta para mostrar correctamente la cadena de texto más larga y el tamaño de fuente mayor, y se cambia el tamaño de los elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> para alojar los controles hospedados.  
  
## Utilizar posiciones absolutas  
 Puede utilizar posiciones absolutas para colocar el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> en cualquier ubicación de la interfaz de usuario.  
  
#### Para utilizar posiciones absolutas  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se coloca a 20 píxeles del lado superior de la celda de la cuadrícula y a 20 píxeles del lado izquierdo.  
  
## Especificar explícitamente el tamaño  
 Puede especificar el tamaño del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> utilizando las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.  
  
#### Para especificar explícitamente el tamaño  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se establece en un tamaño de 50 píxeles de ancho por 70 píxeles de alto, menor que los valores de diseño predeterminados.  El contenido del control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se reorganiza en consecuencia.  
  
## Establecer las propiedades de diseño  
 Establezca siempre las propiedades del control hospedado relacionadas con el diseño mediante las propiedades del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Si establece directamente las propiedades de diseño del control hospedado, se producirán resultados imprevistos.  
  
 Establecer las propiedades relacionadas con el diseño del control hospedado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no tiene ningún efecto.  
  
#### Para ver los efectos de establecer las propiedades en el control hospedado  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  En el Explorador de soluciones haga doble clic en MainWindow.xaml.  vb o MainWindow.xaml.cs para abrirlo en el Editor de código.  
  
3.  Copie el código siguiente en la definición de la clase `MainWindow`.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Presione F5 para compilar y ejecutar la aplicación.  
  
5.  Haga clic en el botón **Click me**.  El controlador de eventos `button1_Click` establece las propiedades <xref:System.Windows.Forms.Control.Top%2A> y <xref:System.Windows.Forms.Control.Left%2A> del control hospedado.  Esto hace que el control hospedado cambie de posición dentro del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  El host mantiene la misma área de pantalla, pero el control hospedado se recorta.  En lugar de ello, el control hospedado siempre debe rellenar el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
## Entender las limitaciones del orden z  
 De forma predeterminada, los elementos visibles de <xref:System.Windows.Forms.Integration.WindowsFormsHost> siempre se dibujan encima de otros elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , y no están afectados por orden z.  Para habilitar la ordenación z, establezca la propiedad de <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> de <xref:System.Windows.Forms.Integration.WindowsFormsHost> en true y la propiedad de <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> a <xref:System.Windows.Interop.CompositionMode.Full> o a <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### Para ver el comportamiento predeterminado del orden z  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se pinta encima del elemento de etiqueta.  
  
#### Para ver el comportamiento del orden z cuando IsRedirected es true  
  
1.  Reemplace el ejemplo anterior del orden z con el XAML siguiente.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     Presione F5 para compilar y ejecutar la aplicación.  El elemento de la etiqueta se pinta encima del elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost> .  
  
## Acoplamiento  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> admite el acoplamiento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Establezca la propiedad <xref:System.Windows.Controls.DockPanel.Dock%2A> adjunta para acoplar el control hospedado en un elemento <xref:System.Windows.Controls.DockPanel>.  
  
#### Para acoplar un control hospedado  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se acopla en el lado derecho del elemento <xref:System.Windows.Controls.DockPanel>.  
  
## Establecer la visibilidad  
 Puede hacer que el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sea invisible o contraerlo estableciendo la propiedad <xref:System.Windows.UIElement.Visibility%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Cuando un control no está visible, no se muestra, pero ocupa espacio en el diseño.  Cuando se contrae un control, no se muestra, ni ocupa el espacio en el diseño.  
  
#### Para establecer la visibilidad de un control hospedado  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
4.  Haga clic en el botón **Click to make invisible** para hacer invisible el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
5.  Haga clic en el botón **Click to collapse** para ocultar completamente el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> del diseño.  Cuando se contrae el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], los elementos circundantes se reorganizan para ocupar su espacio.  
  
## Hospedar un control que no se ajusta  
 Algunos controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen un tamaño fijo y no se ajustan para rellenar el espacio disponible en el diseño.  Por ejemplo, el control <xref:System.Windows.Forms.MonthCalendar> muestra un mes en un espacio fijo.  
  
#### Para hospedar un control que no se ajusta  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se centra en la fila de la cuadrícula, pero no se ajusta para rellenar el espacio disponible.  Si la ventana es lo bastante grande, puede que vea dos o más meses mostrados por el control <xref:System.Windows.Forms.MonthCalendar> hospedado, pero éstos están centrados en la fila.  El motor de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] centra los elementos cuyo tamaño no se puede ajustar para rellenar el espacio disponible.  
  
## Ajustar la escala  
 A diferencia de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la escala de la mayoría de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se puede cambiar continuamente.  De forma predeterminada, el elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost> escala el control hospedado cuando es posible.  Para habilitar el ajuste de escala hechos y derecho, establezca la propiedad de <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> de <xref:System.Windows.Forms.Integration.WindowsFormsHost> en true y la propiedad de <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> a <xref:System.Windows.Interop.CompositionMode.Full> o a <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### Escalar un control hospedado utilizando el comportamiento predeterminado  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  La escala del control hospedado y de los elementos que lo rodean se ajusta mediante un factor de 0,5.  Sin embargo, no se ajusta el tamaño de la fuente del control hospedado.  
  
#### Escalar un control hospedado estableciendo IsRedirected en true  
  
1.  Reemplace el ejemplo anterior de escala con el XAML siguiente.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  El control hospedado, los elementos que lo rodean, y la fuente del control hospedado son escalados por un factor de 0,5.  
  
## Girar  
 A diferencia de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten el giro.  De forma predeterminada, el elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost> no gira con otros elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando se aplica una transformación de giro.  Cualquier valor de giro distinto de 180 grados provoca el evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.  Para habilitar girar a cualquier ángulo, establezca la propiedad de <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> de <xref:System.Windows.Forms.Integration.WindowsFormsHost> en true y la propiedad de <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> a <xref:System.Windows.Interop.CompositionMode.Full> o a <xref:System.Windows.Interop.CompositionMode.OutputOnly>.  
  
#### Para ver el efecto del giro en una aplicación híbrida  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  No se gira el control hospedado, pero los elementos que lo rodean se giran en un ángulo de 180 grados.  Es posible que deba cambiar de tamaño la ventana para ver los elementos.  
  
#### Para ver el efecto del giro en una aplicación híbrida cuando IsRedirected es true  
  
1.  Reemplace el ejemplo anterior de giro con el XAML siguiente.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  Gira el control hospedado.  Observe que la propiedad de <xref:System.Windows.Media.RotateTransform.Angle%2A> se puede establecer en cualquier valor.  Es posible que deba cambiar de tamaño la ventana para ver los elementos.  
  
## Establecer relleno y márgenes  
 El relleno y los márgenes en el diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son similares a los de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Basta con establecer las propiedades <xref:System.Windows.Controls.Control.Padding%2A> y <xref:System.Windows.FrameworkElement.Margin%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
#### Para establecer el relleno y los márgenes para un control hospedado  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  La configuración de los márgenes y del relleno se aplica a los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados de la misma manera que se aplicarían en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## Utilizar contenedores de diseño dinámico  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proporciona dos contenedores de diseño dinámico, <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel>.  También puede utilizar estos contenedores en diseños de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
#### Para utilizar un contenedor de diseño dinámico  
  
1.  Copie el XAML siguiente en el elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Agregue una llamada al método `InitializeFlowLayoutPanel` en el constructor.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Presione F5 para compilar y ejecutar la aplicación.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> rellena <xref:System.Windows.Controls.DockPanel>, y <xref:System.Windows.Forms.FlowLayoutPanel> organiza sus controles secundarios de acuerdo con la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> predeterminada.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Consideraciones sobre el diseño del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Ejemplo Arranging Windows Forms Controls in WPF](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)