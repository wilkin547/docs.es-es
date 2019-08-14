---
title: 'Tutorial: Organizar controles de formularios Windows Forms en WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972306"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Tutorial: Organizar controles de formularios Windows Forms en WPF

En este tutorial se muestra cómo usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las características de diseño [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] para organizar los controles en una aplicación híbrida.

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

- Ajustar la escala.

- Girar.

- Establecer el relleno y los márgenes.

- Usar contenedores de diseño dinámico.

Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea el [ejemplo de organización de controles Windows Forms en WPF](https://go.microsoft.com/fwlink/?LinkID=159971).

Cuando haya terminado, tendrá conocimientos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sobre las características de diseño de las aplicaciones basadas en. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="creating-the-project"></a>Crear el proyecto

### <a name="to-create-and-set-up-the-project"></a>Para crear y configurar el proyecto

1. Cree un proyecto de aplicación de `WpfLayoutHostingWf`WPF denominado.

2. En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.

    - WindowsFormsIntegration

    - System.Windows.Forms

    - System.Drawing

3. Haga doble clic en MainWindow.xaml para abrirlo en la vista XAML.

4. En el <xref:System.Windows.Window> elemento, agregue la siguiente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] asignación de espacio de nombres.

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. En el <xref:System.Windows.Controls.Grid> elemento, establezca <xref:System.Windows.Controls.Grid.ShowGridLines%2A> la propiedad `true` en y defina cinco filas y tres columnas.

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a>Usar la configuración de diseño predeterminada

De forma predeterminada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> el elemento controla el diseño del control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado.

### <a name="to-use-default-layout-settings"></a>Para usar la configuración de diseño predeterminada

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. Presione F5 para compilar y ejecutar la aplicación. El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Controls.Canvas>control apareceen.<xref:System.Windows.Forms.Button?displayProperty=nameWithType> El tamaño del control hospedado se basa en su contenido y <xref:System.Windows.Forms.Integration.WindowsFormsHost> el elemento se ajusta para alojar el control hospedado.

## <a name="sizing-to-content"></a>Ajuste del tamaño al contenido

El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantiza que el tamaño del control hospedado se ajusta para mostrar su contenido correctamente.

### <a name="to-size-to-content"></a>Para ajustar al contenido

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. Presione F5 para compilar y ejecutar la aplicación. Los dos nuevos controles de botón tienen el tamaño para mostrar la cadena de texto más larga y el tamaño de <xref:System.Windows.Forms.Integration.WindowsFormsHost> fuente más grande correctamente, y se cambia el tamaño de los elementos para alojar los controles hospedados.

## <a name="using-absolute-positioning"></a>Usar el posicionamiento absoluto

Puede usar la posición absoluta para colocar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento en cualquier parte de la interfaz de usuario (UI).

### <a name="to-use-absolute-positioning"></a>Para usar el posicionamiento absoluto

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se coloca 20 píxeles desde el lado superior de la celda de la cuadrícula y 20 píxeles desde la izquierda.

## <a name="specifying-size-explicitly"></a>Especificar el tamaño explícitamente

Puede especificar el tamaño del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento mediante las <xref:System.Windows.FrameworkElement.Width%2A> propiedades y <xref:System.Windows.FrameworkElement.Height%2A> .

### <a name="to-specify-size-explicitly"></a>Para especificar el tamaño explícitamente

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se establece en un tamaño de 50 píxeles de ancho por 70 píxeles de alto, que es menor que la configuración de diseño predeterminada. El contenido del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se reorganiza en consecuencia.

## <a name="setting-layout-properties"></a>Establecer las propiedades de diseño

Establezca siempre las propiedades relacionadas con el diseño en el control hospedado mediante las propiedades <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento. Si establece las propiedades de diseño directamente en el control hospedado se producirán resultados imprevistos.

 Establecer las propiedades relacionadas con el diseño en el control [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hospedado en no tiene ningún efecto.

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Para ver los efectos de establecer las propiedades en el control hospedado

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. En el Explorador de soluciones, haga doble clic en MainWindow.xaml. vb o MainWindow.xaml.cs para abrirlo en el Editor de código.

3. Copie el código siguiente en la `MainWindow` definición de clase.

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. Presione F5 para compilar y ejecutar la aplicación.

5. Haga clic en el botón **click me** . El `button1_Click` controlador de eventos establece <xref:System.Windows.Forms.Control.Top%2A> las <xref:System.Windows.Forms.Control.Left%2A> propiedades y en el control hospedado. Esto hace que el control hospedado se cambie de posición dentro <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento. El host conserva la misma área de la pantalla, pero el control hospedado se recorta. En su lugar, el control hospedado siempre debe <xref:System.Windows.Forms.Integration.WindowsFormsHost> rellenar el elemento.

## <a name="understanding-z-order-limitations"></a>Entender las limitaciones del orden Z

Los <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos visibles siempre se dibujan encima de otros elementos de WPF y no se ven afectados por el orden z. Para ver este comportamiento del orden z, haga lo siguiente:

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se dibuja sobre el elemento de etiqueta.

## <a name="docking"></a>Acoplamiento

<xref:System.Windows.Forms.Integration.WindowsFormsHost>el elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite el acoplamiento. Establezca la <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad adjunta para acoplar el control hospedado <xref:System.Windows.Controls.DockPanel> en un elemento.

### <a name="to-dock-a-hosted-control"></a>Para acoplar un control hospedado

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento está acoplado al lado derecho <xref:System.Windows.Controls.DockPanel> del elemento.

## <a name="setting-visibility"></a>Establecer la visibilidad

Puede hacer que el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control sea invisible o contraerlo si <xref:System.Windows.UIElement.Visibility%2A> establece la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost> en el elemento. Cuando un control es invisible no se muestra, pero ocupa espacio de diseño. Cuando un control está contraído no se muestra ni ocupa espacio de diseño.

### <a name="to-set-the-visibility-of-a-hosted-control"></a>Para establecer la visibilidad de un control hospedado

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. Presione F5 para compilar y ejecutar la aplicación.

4. Haga clic en el botón **hacer clic para hacer invisible** para hacer que el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento sea invisible.

5. Haga clic en el botón **haga clic para contraer** para ocultar completamente el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento del diseño. Cuando se [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] contrae el control, los elementos circundantes se reorganizan para ocupar su espacio.

## <a name="hosting-a-control-that-does-not-stretch"></a>Hospedar un control que no se ajusta

Algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles tienen un tamaño fijo y no se ajustan para rellenar el espacio disponible en el diseño. Por ejemplo, el <xref:System.Windows.Forms.MonthCalendar> control muestra un mes en un espacio fijo.

### <a name="to-host-a-control-that-does-not-stretch"></a>Para hospedar un control que no se ajusta

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se centra en la fila de la cuadrícula, pero no se ajusta para rellenar el espacio disponible. Si la ventana es suficientemente grande, puede ver dos o más meses mostrados por el control <xref:System.Windows.Forms.MonthCalendar> hospedado, pero se centran en la fila. El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motor de diseño centra los elementos que no se pueden ajustar para rellenar el espacio disponible.

## <a name="scaling"></a>Cambiar escala

A diferencia de los elementos de WPF, la mayoría de los controles Windows Forms no son continuamente escalables. Para proporcionar escalado personalizado, invalide el <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> método.

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Para escalar un control hospedado mediante el comportamiento predeterminado

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. Presione F5 para compilar y ejecutar la aplicación. El control hospedado y sus elementos adyacentes se escalan por un factor de 0,5. A pesar de ello, la fuente del control hospedado no se escala.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Girar

A diferencia de los elementos de WPF, los controles de Windows Forms no admiten la rotación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento no gira con otros elementos de WPF cuando se aplica una transformación de giro. Cualquier valor de rotación que no sea 180 grados <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> genera el evento.

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Para ver el efecto del giro en una aplicación híbrida

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. Presione F5 para compilar y ejecutar la aplicación. El control hospedado no se gira, pero sus elementos adyacentes se giran en un ángulo de 180 grados. Es posible que deba cambiar el tamaño de la ventana para ver los elementos.

## <a name="setting-padding-and-margins"></a>Establecer el relleno y márgenes

El relleno y los márgenes del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño son similares al relleno y los márgenes de. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Simplemente establezca las <xref:System.Windows.Controls.Control.Padding%2A> propiedades <xref:System.Windows.FrameworkElement.Margin%2A> y en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Para establecer el relleno y los márgenes de un control hospedado

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. Presione F5 para compilar y ejecutar la aplicación. Los valores de relleno y margen se aplican a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles hospedados de la misma manera en que [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]se aplicarían en.

## <a name="using-dynamic-layout-containers"></a>Usar contenedores de diseño dinámico

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]proporciona dos contenedores de diseño dinámico <xref:System.Windows.Forms.FlowLayoutPanel> , <xref:System.Windows.Forms.TableLayoutPanel>y. También puede usar estos contenedores en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los diseños.

### <a name="to-use-a-dynamic-layout-container"></a>Para usar un contenedor de diseño dinámico

1. Copie el siguiente código XAML en <xref:System.Windows.Controls.Grid> el elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. Agregue una llamada al método `InitializeFlowLayoutPanel` en el constructor.

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento rellena <xref:System.Windows.Controls.DockPanel>y <xref:System.Windows.Forms.FlowLayoutPanel> organiza sus controles secundarios en el valor predeterminado <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Consideraciones sobre el diseño del elemento WindowsFormsHost](layout-considerations-for-the-windowsformshost-element.md)
- [Ejemplo de cómo organizar controles Windows Forms en WPF](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Tutorial: Hospedar un control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
