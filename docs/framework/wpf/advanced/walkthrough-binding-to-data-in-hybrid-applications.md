---
title: 'Tutorial: Enlazar a datos en aplicaciones híbridas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: ef5f14cdbecab8bc780cb7b2a642429970a25316
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972276"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Tutorial: Enlazar a datos en aplicaciones híbridas

Enlazar un origen de datos a un control es esencial para proporcionar a los usuarios acceso a los datos subyacentes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] , [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]independientemente de si se usa o. En este tutorial se muestra cómo se puede usar el enlace de datos en aplicaciones [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] híbridas que incluyen controles y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .

Las tareas ilustradas en este tutorial incluyen:

- Crear el proyecto.

- Definir la plantilla de datos.

- Especificar el diseño del formulario.

- Especificar los enlaces de datos.

- Mostrar los datos mediante la interoperación.

- Agregar el origen de datos al proyecto.

- Enlazar al origen de datos.

Para obtener una lista de código completa de las tareas ilustradas en este tutorial, consulte [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).

Cuando acabe, entenderá mejor las características de enlace de datos en aplicaciones híbridas.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio.

- Acceso a la base de datos de ejemplo Northwind que se ejecuta en Microsoft SQL Server.

## <a name="creating-the-project"></a>Crear el proyecto

### <a name="to-create-and-set-up-the-project"></a>Para crear y configurar el proyecto

1. Cree un proyecto de aplicación de `WPFWithWFAndDatabinding`WPF denominado.

2. En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Abra MainWindow. XAML en [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

4. En el <xref:System.Windows.Window> elemento, agregue la siguiente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] asignación de espacios de nombres.

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. Asigne un nombre <xref:System.Windows.Controls.Grid> al `mainGrid` elemento predeterminado asignando la <xref:System.Windows.FrameworkElement.Name%2A> propiedad.

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a>Definir la plantilla de datos

La lista maestra de clientes se muestra en un <xref:System.Windows.Controls.ListBox> control. En el ejemplo de código siguiente <xref:System.Windows.DataTemplate> se define `ListItemsTemplate` un objeto denominado que controla <xref:System.Windows.Controls.ListBox> el árbol visual del control. Esto <xref:System.Windows.DataTemplate> se asigna a la <xref:System.Windows.Controls.ListBox> propiedad del <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> control.

### <a name="to-define-the-data-template"></a>Para definir la plantilla de datos

- Copie el código XAML siguiente en <xref:System.Windows.Controls.Grid> la declaración del elemento.

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a>Especificar el diseño del formulario

El diseño del formulario se define mediante una cuadrícula con tres filas y tres columnas. <xref:System.Windows.Controls.Label>se proporcionan controles para identificar cada columna de la tabla customers.

### <a name="to-set-up-the-grid-layout"></a>Para configurar el diseño de cuadrícula

- Copie el código XAML siguiente en <xref:System.Windows.Controls.Grid> la declaración del elemento.

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a>Para configurar los controles de etiqueta

- Copie el código XAML siguiente en <xref:System.Windows.Controls.Grid> la declaración del elemento.

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a>Especificar los enlaces de datos

La lista maestra de clientes se muestra en un <xref:System.Windows.Controls.ListBox> control. El adjunto `ListItemsTemplate` enlaza un <xref:System.Windows.Controls.TextBlock> control al `ContactName` campo de la base de datos.

Los detalles de cada registro de cliente se muestran en <xref:System.Windows.Controls.TextBox> varios controles.

### <a name="to-specify-data-bindings"></a>Para especificar los enlaces de datos

- Copie el código XAML siguiente en <xref:System.Windows.Controls.Grid> la declaración del elemento.

     La <xref:System.Windows.Data.Binding> clase enlaza los <xref:System.Windows.Controls.TextBox> controles a los campos adecuados en la base de datos.

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a>Mostrar los datos mediante la interoperación

Los pedidos correspondientes al cliente seleccionado se muestran en un <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control denominado. `dataGridView1` El `dataGridView1` control está enlazado al origen de datos en el archivo de código subyacente. Un <xref:System.Windows.Forms.Integration.WindowsFormsHost> control es el elemento primario de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] este control.

### <a name="to-display-data-in-the-datagridview-control"></a>Para mostrar los datos en el control DataGridView

- Copie el código XAML siguiente en <xref:System.Windows.Controls.Grid> la declaración del elemento.

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a>Agregar el origen de datos al proyecto

Con Visual Studio, puede agregar fácilmente un origen de datos al proyecto. Este procedimiento agrega un conjunto de datos fuertemente tipados a su proyecto. También se agregan otras clases de compatibilidad, como adaptadores de tabla para cada una de las tablas elegidas.

### <a name="to-add-the-data-source"></a>Para agregar el origen de datos

1. En el menú **datos** , seleccione **Agregar nuevo origen de datos**.

2. En el **Asistente para la configuración de orígenes de datos**, cree una conexión a la base de datos Northwind mediante un conjunto de datos. Para obtener más información, consulte [Cómo Conectarse a los datos de una](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))base de datos.

3. Cuando el **Asistente para la configuración de orígenes de datos**le pida, guarde la cadena de `NorthwindConnectionString`conexión como.

4. Cuando se le pida que elija los objetos de base de datos, `Customers` seleccione `Orders` las tablas y y asigne un nombre al `NorthwindDataSet`conjunto de datos generado.

## <a name="binding-to-the-data-source"></a>Enlazar al origen de datos

El <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> componente proporciona una interfaz uniforme para el origen de datos de la aplicación. El enlace al origen de datos se implementa en el archivo de código subyacente.

### <a name="to-bind-to-the-data-source"></a>Para enlazar al origen de datos

1. Abra el archivo de código subyacente, denominado MainWindow.xaml.vb o MainWindow.xaml.cs.

2. Copie el código siguiente en la `MainWindow` definición de clase.

     Este código declara el <xref:System.Windows.Forms.BindingSource> componente y las clases auxiliares asociadas que se conectan a la base de datos.

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. Copie el siguiente código en el constructor.

     Este código crea e inicializa el <xref:System.Windows.Forms.BindingSource> componente.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. Abra MainWindow.xaml.

5. En vista de diseño o en la vista XAML, <xref:System.Windows.Window> Seleccione el elemento.

6. En el ventana Propiedades, haga clic en la pestaña **eventos** .

7. Haga doble clic en <xref:System.Windows.FrameworkElement.Loaded> el evento.

8. Copie el código siguiente en el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.

     Este código asigna el <xref:System.Windows.Forms.BindingSource> componente como contexto de datos y rellena los `Customers` objetos de adaptador y `Orders` .

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Copie el código siguiente en la `MainWindow` definición de clase.

     Este método controla el <xref:System.Windows.Data.CollectionView.CurrentChanged> evento y actualiza el elemento actual del enlace de datos.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. Presione F5 para compilar y ejecutar la aplicación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Ejemplo de enlace de datos en aplicaciones híbridas](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Tutorial: Hospedar un control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
