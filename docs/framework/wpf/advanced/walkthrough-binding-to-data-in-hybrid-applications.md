---
title: "Tutorial: Enlazar a datos en aplicaciones h&#237;bridas | Microsoft Docs"
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
  - "enlace de datos [interoperabilidad con WPF]"
  - "aplicaciones híbridas [interoperabilidad con WPF]"
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
caps.latest.revision: 39
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# Tutorial: Enlazar a datos en aplicaciones h&#237;bridas
Enlazar un origen de datos a un control es esencial para proporcionar a los usuarios acceso a los datos subyacentes, tanto si se está utilizando [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] como [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Este tutorial muestra cómo puede utilizar el enlace de datos en aplicaciones híbridas que incluyan tanto controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] como controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto.  
  
-   Definir la plantilla de datos.  
  
-   Especificar el diseño del formulario.  
  
-   Especificar los enlaces de datos.  
  
-   Mostrar los datos utilizando interoperatividad.  
  
-   Agregar el origen de datos al proyecto.  
  
-   Establecer el enlace con el origen de datos.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [Data Binding in Hybrid Applications Sample](http://go.microsoft.com/fwlink/?LinkID=159983).  
  
 Cuando termine, comprenderá las características de enlace de datos en aplicaciones híbridas.  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Acceso a la base de datos de ejemplo Northwind ejecutándose en SQL Server.  
  
## Crear el proyecto  
  
#### Para crear y configurar el proyecto  
  
1.  Cree un proyecto Aplicación WPF denominado `WPFWithWFAndDatabinding`.  
  
2.  En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Abra MainWindow.xaml en [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  En el elemento <xref:System.Windows.Window>, agregue la siguiente asignación de espacio de nombres [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Nombre el elemento <xref:System.Windows.Controls.Grid> `mainGrid` predeterminado asignando la propiedad <xref:System.Windows.FrameworkElement.Name%2A>.  
  
     [!code-xml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## Definir la plantilla de datos  
 La lista maestra de clientes se muestra en un control <xref:System.Windows.Controls.ListBox>.  En el ejemplo de código siguiente se define un objeto <xref:System.Windows.DataTemplate> denominado `ListItemsTemplate` que controla el árbol visual del control <xref:System.Windows.Controls.ListBox>.  Este objeto <xref:System.Windows.DataTemplate> se asigna a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> del control <xref:System.Windows.Controls.ListBox>.  
  
#### Para definir la plantilla de datos  
  
-   Copie el siguiente código XAML en la declaración del elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## Especificar el diseño del formulario  
 El diseño del formulario lo define una cuadrícula con tres filas y tres columnas.  Se proporcionan controles <xref:System.Windows.Controls.Label> para identificar cada columna de la tabla Customers.  
  
#### Para configurar el diseño de la cuadrícula  
  
-   Copie el siguiente código XAML en la declaración del elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### Para configurar los controles de etiqueta  
  
-   Copie el siguiente código XAML en la declaración del elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## Especificar enlaces de datos  
 La lista maestra de clientes se muestra en un control <xref:System.Windows.Controls.ListBox>.  El objeto `ListItemsTemplate` asociado enlaza un control <xref:System.Windows.Controls.TextBlock> al campo `ContactName` de la base de datos.  
  
 Los detalles de cada registro de cliente se muestran en varios controles <xref:System.Windows.Controls.TextBox>.  
  
#### Para especificar enlaces de datos  
  
-   Copie el siguiente código XAML en la declaración del elemento <xref:System.Windows.Controls.Grid>.  
  
     La clase <xref:System.Windows.Data.Binding> enlaza los controles <xref:System.Windows.Controls.TextBox> a los campos adecuados de la base de datos.  
  
     [!code-xml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## Mostrar datos utilizando interoperatividad.  
 Los pedidos correspondientes al cliente seleccionado se muestran en un control <xref:System.Windows.Forms.DataGridView?displayProperty=fullName> denominado `dataGridView1`.  El control `dataGridView1` se enlaza al origen de datos en el archivo de código subyacente.  Un control <xref:System.Windows.Forms.Integration.WindowsFormsHost> es el elemento primario de este control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
#### Para mostrar datos en el control DataGridView  
  
-   Copie el siguiente código XAML en la declaración del elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## Agregar el origen de datos al proyecto  
 Con [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], puede agregar con facilidad un origen de datos al proyecto.  Este procedimiento agrega un conjunto de datos fuertemente tipado al proyecto.  También se agregan otras diversas clases de soporte, tales como adaptadores de tabla para cada una de las tablas elegidas.  
  
#### Para agregar el origen de datos  
  
1.  En el menú **Datos**, seleccione **Agregar nuevo origen de datos**.  
  
2.  En el **Asistente para la configuración de orígenes de datos**, cree una conexión a la base de datos Northwind utilizando un conjunto de datos.  Para obtener más información, vea [Cómo: Conectarse a los datos de una base de datos](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md).  
  
3.  Cuando se lo pida el **Asistente para la configuración de orígenes de datos**, guarde la cadena de conexión como `NorthwindConnectionString`.  
  
4.  Cuando le pidan que elija los objetos de base de datos, seleccione las tablas `Customers` y `Orders`, y asigne el nombre `NorthwindDataSet` al conjunto de datos generado.  
  
## Establecer el enlace con el origen de datos  
 El componente <xref:System.Windows.Forms.BindingSource?displayProperty=fullName> proporciona una interfaz uniforme para el origen de datos de la aplicación.  El enlace al origen de datos se implementa en el archivo de código subyacente.  
  
#### Para enlazar con el origen de datos  
  
1.  Abra el archivo de código subyacente, que se denomina MainWindow.xaml.vb o MainWindow.xaml.cs.  
  
2.  Copie el código siguiente en la definición de la clase `MainWindow`.  
  
     Este código declara el componente <xref:System.Windows.Forms.BindingSource> y las clases auxiliares asociadas que conectan con la base de datos.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  Copie el código siguiente en el constructor.  
  
     Este código crea e inicializa el componente <xref:System.Windows.Forms.BindingSource>.  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  Abra MainWindow.xaml.  
  
5.  En la vista Diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.  
  
6.  En la ventana Propiedades, haga clic en la pestaña **Eventos**.  
  
7.  Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
8.  Copie el código siguiente en el controlador de eventos <xref:System.Windows.FrameworkElement.Loaded>.  
  
     Este código asigna el componente <xref:System.Windows.Forms.BindingSource> como el contexto de datos y rellena los objetos de adaptador `Customers` y `Orders`.  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. Copie el código siguiente en la definición de la clase `MainWindow`.  
  
     Este método administra el evento <xref:System.Windows.Data.CollectionView.CurrentChanged> y actualiza el elemento actual del enlace de datos.  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Presione F5 para compilar y ejecutar la aplicación.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Data Binding in Hybrid Applications Sample](http://go.microsoft.com/fwlink/?LinkID=159983)   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)