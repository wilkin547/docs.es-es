---
title: Organizar Windows Forms controles en WPF
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 5e7544dfdbee234bb968c9a7f39814e8749ece15
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735286"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Tutorial: Organizar controles de formularios Windows Forms en WPF

En este tutorial se muestra cómo usar las características de diseño [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para organizar los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en una aplicación híbrida.

Las tareas ilustradas en este tutorial incluyen:

- Crear el proyecto.
- Usar la configuración de diseño predeterminada.
- Ajustar el tamaño al contenido.
- Usar el posicionamiento absoluto.
- Especificar el tamaño explícitamente.
- Establecer las propiedades de diseño.
- Entender las limitaciones del orden Z.
- Acoplar.
- Establecer la visibilidad.
- Hospedar un control que no se ajusta.
- Escala.
- Girar.
- Establecer el relleno y los márgenes.
- Usar contenedores de diseño dinámico.

Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea el [ejemplo de organización de controles Windows Forms en WPF](https://go.microsoft.com/fwlink/?LinkID=159971).

Cuando haya terminado, tendrá conocimientos sobre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] características de diseño en aplicaciones basadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="creating-the-project"></a>Crear el proyecto

Para crear y configurar el proyecto, siga estos pasos:

1. Cree un proyecto de aplicación de WPF denominado `WpfLayoutHostingWf`.

2. En Explorador de soluciones, agregue referencias a los ensamblados siguientes:

    - WindowsFormsIntegration
    - System.Windows.Forms
    - System.Drawing

3. Haga doble clic en *MainWindow. Xaml* para abrirlo en la vista XAML.

4. En el elemento <xref:System.Windows.Window>, agregue la siguiente asignación de espacio de nombres [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. En el elemento <xref:System.Windows.Controls.Grid>, establezca la propiedad <xref:System.Windows.Controls.Grid.ShowGridLines%2A> en `true` y defina cinco filas y tres columnas.

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>Usar la configuración de diseño predeterminada

De forma predeterminada, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> controla el diseño del control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado.

Para usar la configuración de diseño predeterminada, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. Aparece el control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> en la <xref:System.Windows.Controls.Canvas>. El tamaño del control hospedado se basa en su contenido y el tamaño del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se ajusta para alojar el control hospedado.

## <a name="sizing-to-content"></a>Ajustar el tamaño al contenido

El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantiza que el tamaño del control hospedado se ajusta para mostrar su contenido correctamente.

Para ajustar el tamaño al contenido, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. Los dos nuevos controles de botón tienen el tamaño para mostrar la cadena de texto más larga y el tamaño de fuente más grande correctamente, y se cambia el tamaño de los elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> para alojar los controles hospedados.

## <a name="using-absolute-positioning"></a>Usar el posicionamiento absoluto

Puede usar la posición absoluta para colocar el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> en cualquier parte de la interfaz de usuario (UI).

Para usar el posicionamiento absoluto, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se coloca 20 píxeles desde el lado superior de la celda de la cuadrícula y 20 píxeles desde la izquierda.

## <a name="specifying-size-explicitly"></a>Especificar el tamaño explícitamente

Puede especificar el tamaño del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> mediante las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.

Para especificar el tamaño explícitamente, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se establece en un tamaño de 50 píxeles de ancho por 70 píxeles de alto, que es menor que la configuración de diseño predeterminada. El contenido del control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se reorganiza en consecuencia.

## <a name="setting-layout-properties"></a>Establecer las propiedades de diseño

Establezca siempre las propiedades relacionadas con el diseño en el control hospedado mediante las propiedades del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Si establece las propiedades de diseño directamente en el control hospedado se producirán resultados imprevistos.

 Establecer las propiedades relacionadas con el diseño en el control hospedado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no tiene ningún efecto.

Para ver los efectos de establecer las propiedades en el control hospedado, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. En **Explorador de soluciones**, haga doble clic en *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS* para abrirlo en el editor de código.

3. Copie el código siguiente en la definición de clase `MainWindow`:

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.

5. Haga clic en el botón **click me** . El controlador de eventos `button1_Click` establece las propiedades <xref:System.Windows.Forms.Control.Top%2A> y <xref:System.Windows.Forms.Control.Left%2A> en el control hospedado. Esto hace que el control hospedado se cambie de posición dentro del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. El host conserva la misma área de la pantalla, pero el control hospedado se recorta. En su lugar, el control hospedado siempre debe rellenar el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

## <a name="understanding-z-order-limitations"></a>Entender las limitaciones del orden Z

Los elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> visibles siempre se dibujan encima de otros elementos de WPF y no se ven afectados por el orden z. Para ver este comportamiento del orden z, haga lo siguiente:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se dibuja sobre el elemento de etiqueta.

## <a name="docking"></a>Docking

<xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento admite el acoplamiento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Establezca el <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad adjunta para acoplar el control hospedado en un elemento <xref:System.Windows.Controls.DockPanel>.

Para acoplar un control hospedado, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se acopla al lado derecho del elemento <xref:System.Windows.Controls.DockPanel>.

## <a name="setting-visibility"></a>Establecer la visibilidad

Puede hacer que el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sea invisible o contraerlo si establece la propiedad <xref:System.Windows.UIElement.Visibility%2A> en el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Cuando un control es invisible no se muestra, pero ocupa espacio de diseño. Cuando un control está contraído no se muestra ni ocupa espacio de diseño.

Para establecer la visibilidad de un control hospedado, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. En *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS*, copie el código siguiente en la definición de clase:

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.

4. Haga clic en el botón **hacer clic para hacer invisible** para hacer que el elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost> sea invisible.

5. Haga clic en el botón **haga clic para contraer** para ocultar completamente el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> del diseño. Cuando se contrae el control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], los elementos circundantes se reorganizan para ocupar su espacio.

## <a name="hosting-a-control-that-does-not-stretch"></a>Hospedar un control que no se ajusta

Algunos controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen un tamaño fijo y no se ajustan para rellenar el espacio disponible en el diseño. Por ejemplo, el control <xref:System.Windows.Forms.MonthCalendar> muestra un mes en un espacio fijo.

Para hospedar un control que no se ajusta, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se centra en la fila de la cuadrícula, pero no se ajusta para rellenar el espacio disponible. Si la ventana es suficientemente grande, puede ver dos o más meses mostrados por el control de <xref:System.Windows.Forms.MonthCalendar> hospedado, pero se centran en la fila. El motor de diseño [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] centra los elementos que no se pueden ajustar para rellenar el espacio disponible.

## <a name="scaling"></a>Cambiar escala

A diferencia de los elementos de WPF, la mayoría de los controles Windows Forms no son continuamente escalables. Para proporcionar escalado personalizado, invalide el método <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>.

Para escalar un control hospedado con el comportamiento predeterminado, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El control hospedado y sus elementos adyacentes se escalan por un factor de 0,5. A pesar de ello, la fuente del control hospedado no se escala.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Girar

A diferencia de los elementos de WPF, los controles de Windows Forms no admiten la rotación. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> no gira con otros elementos de WPF cuando se aplica una transformación de giro. Cualquier valor de rotación que no sea 180 grados produce el evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.

Para ver el efecto de la rotación en una aplicación híbrida, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El control hospedado no se gira, pero sus elementos adyacentes se giran en un ángulo de 180 grados. Es posible que deba cambiar el tamaño de la ventana para ver los elementos.

## <a name="setting-padding-and-margins"></a>Establecer el relleno y márgenes

El relleno y los márgenes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño son similares al relleno y los márgenes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Simplemente establezca las propiedades <xref:System.Windows.Controls.Control.Padding%2A> y <xref:System.Windows.FrameworkElement.Margin%2A> en el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

Para establecer el relleno y los márgenes de un control hospedado, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. Los valores de relleno y margen se aplican a los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados de la misma manera que se aplicarían en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

## <a name="using-dynamic-layout-containers"></a>Usar contenedores de diseño dinámico

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proporciona dos contenedores de diseño dinámico, <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel>. También puede usar estos contenedores en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseños.

Para usar un contenedor de diseño dinámico, siga estos pasos:

1. Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. En *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS*, copie el código siguiente en la definición de clase:

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Agregue una llamada al método `InitializeFlowLayoutPanel` en el constructor:

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación. El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> rellena el <xref:System.Windows.Controls.DockPanel>y <xref:System.Windows.Forms.FlowLayoutPanel> organiza sus controles secundarios en la <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>predeterminada.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Ejemplo de cómo organizar controles Windows Forms en WPF](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
