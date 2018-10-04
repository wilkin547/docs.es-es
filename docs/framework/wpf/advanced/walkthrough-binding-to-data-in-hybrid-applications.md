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
ms.openlocfilehash: 7128b23790588a604989cb18918a7a7e8b598191
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584230"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Tutorial: Enlazar a datos en aplicaciones híbridas
Enlazar un origen de datos a un control es esencial para proporcionar a los usuarios con acceso a datos subyacentes, si usas [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En este tutorial se muestra cómo puede usar el enlace de datos en aplicaciones híbridas que incluyen ambos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto.  
  
-   Definir la plantilla de datos.  
  
-   Especificar el diseño del formulario.  
  
-   Especificar los enlaces de datos.  
  
-   Mostrar los datos mediante la interoperación.  
  
-   Agregar el origen de datos al proyecto.  
  
-   Enlazar al origen de datos.  
  
 Para obtener una lista de código completo de las tareas ilustradas en este tutorial, vea [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).  
  
 Cuando acabe, entenderá mejor las características de enlace de datos en aplicaciones híbridas.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   Visual Studio.  
  
-   Acceso a la base de datos de ejemplo Northwind que se ejecutan en Microsoft SQL Server.  
  
## <a name="creating-the-project"></a>Crear el proyecto  
  
#### <a name="to-create-and-set-up-the-project"></a>Para crear y configurar el proyecto  
  
1.  Cree un proyecto de aplicación WPF denominado `WPFWithWFAndDatabinding`.  
  
2.  En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Abra MainWindow.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  En el <xref:System.Windows.Window> elemento, agregue las siguientes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] asignación de espacios de nombres.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  El valor predeterminado el nombre <xref:System.Windows.Controls.Grid> elemento `mainGrid` asignando el <xref:System.Windows.FrameworkElement.Name%2A> propiedad.  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a>Definir la plantilla de datos  
 Se muestra la lista maestra de clientes en un <xref:System.Windows.Controls.ListBox> control. En el ejemplo de código siguiente se define un <xref:System.Windows.DataTemplate> objeto denominado `ListItemsTemplate` que controla el árbol visual de la <xref:System.Windows.Controls.ListBox> control. Esto <xref:System.Windows.DataTemplate> se asigna a la <xref:System.Windows.Controls.ListBox> del control <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> propiedad.  
  
#### <a name="to-define-the-data-template"></a>Para definir la plantilla de datos  
  
-   Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> declaración del elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a>Especificar el diseño del formulario  
 El diseño del formulario se define mediante una cuadrícula con tres filas y tres columnas. <xref:System.Windows.Controls.Label> se proporcionan controles para identificar cada columna en la tabla Customers.  
  
#### <a name="to-set-up-the-grid-layout"></a>Para configurar el diseño de cuadrícula  
  
-   Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> declaración del elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a>Para configurar los controles de etiqueta  
  
-   Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> declaración del elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a>Especificar los enlaces de datos  
 Se muestra la lista maestra de clientes en un <xref:System.Windows.Controls.ListBox> control. El archivo adjunto `ListItemsTemplate` enlaza un <xref:System.Windows.Controls.TextBlock> el control a la `ContactName` arrastrándolo desde la base de datos.  
  
 Se muestran los detalles de cada registro de cliente en varios <xref:System.Windows.Controls.TextBox> controles.  
  
#### <a name="to-specify-data-bindings"></a>Para especificar los enlaces de datos  
  
-   Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> declaración del elemento.  
  
     El <xref:System.Windows.Data.Binding> clase enlaza el <xref:System.Windows.Controls.TextBox> controles a los campos adecuados en la base de datos.  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a>Mostrar los datos mediante la interoperación  
 Los pedidos correspondientes al cliente seleccionado se muestran en un <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control denominado `dataGridView1`. El `dataGridView1` está enlazado al origen de datos en el archivo de código subyacente. Un <xref:System.Windows.Forms.Integration.WindowsFormsHost> control es el elemento primario de este [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
#### <a name="to-display-data-in-the-datagridview-control"></a>Para mostrar los datos en el control DataGridView  
  
-   Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> declaración del elemento.  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a>Agregar el origen de datos al proyecto  
 Con Visual Studio, puede agregar fácilmente un origen de datos al proyecto. Este procedimiento agrega un conjunto de datos fuertemente tipados a su proyecto. También se agregan otras clases de compatibilidad, como adaptadores de tabla para cada una de las tablas elegidas.  
  
#### <a name="to-add-the-data-source"></a>Para agregar el origen de datos  
  
1.  Desde el **datos** menú, seleccione **Agregar nuevo origen de datos**.  
  
2.  En el **Asistente para configuración de origen de datos**, crear una conexión a la base de datos Northwind mediante el uso de un conjunto de datos. Para obtener más información, consulte [Cómo: conectarse a datos en una base de datos](https://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).  
  
3.  Cuando se le solicite en el **Asistente para configuración de origen de datos**, guardar la cadena de conexión como `NorthwindConnectionString`.  
  
4.  Cuando se le pida que elija los objetos de base de datos, seleccione el `Customers` y `Orders` tablas y el nombre del conjunto de datos generado `NorthwindDataSet`.  
  
## <a name="binding-to-the-data-source"></a>Enlazar al origen de datos  
 El <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> componente proporciona una interfaz uniforme para el origen de datos de la aplicación. El enlace al origen de datos se implementa en el archivo de código subyacente.  
  
#### <a name="to-bind-to-the-data-source"></a>Para enlazar al origen de datos  
  
1.  Abra el archivo de código subyacente, denominado MainWindow.xaml.vb o MainWindow.xaml.cs.  
  
2.  Copie el código siguiente en el `MainWindow` definición de clase.  
  
     Este código declara los <xref:System.Windows.Forms.BindingSource> componente y las clases auxiliares asociadas que se conectan a la base de datos.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3.  Copie el siguiente código en el constructor.

     Este código crea e inicializa el <xref:System.Windows.Forms.BindingSource> componente.

     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4.  Abra MainWindow.xaml.

5.  En la vista Diseño o la vista XAML, seleccione el <xref:System.Windows.Window> elemento.

6.  En la ventana Propiedades, haga clic en el **eventos** ficha.

7.  Haga doble clic en el <xref:System.Windows.FrameworkElement.Loaded> eventos.

8.  Copie el código siguiente en el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.

     Este código asigna el <xref:System.Windows.Forms.BindingSource> componente como el contexto de datos y rellena el `Customers` y `Orders` objetos de adaptador.

     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Copie el código siguiente en el `MainWindow` definición de clase.

     Este método controla el <xref:System.Windows.Data.CollectionView.CurrentChanged> eventos y actualiza el elemento actual del enlace de datos.

     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Presione F5 para compilar y ejecutar la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983)  
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
