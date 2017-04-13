---
title: "Tutorial: Introducci&#243;n a WPF | Microsoft Docs"
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
  - "introducción, WPF"
  - "WPF, introducción"
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 68
---
# Tutorial: Introducci&#243;n a WPF
<a name="introduction"></a> En este tutorial se proporciona una introducción al desarrollo de aplicaciones de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], que incluye los elementos comunes a la mayoría de las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]: marcado [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos.  
  
 Este tutorial le guiará a lo largo del desarrollo de una aplicación básica de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mediante los pasos siguientes.  
  
-   Definir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para diseñar la apariencia de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación.  
  
-   Escribir código que determine el comportamiento de la aplicación.  
  
-   Crear una definición de aplicación para administrar la aplicación.  
  
-   Agregar controles y crear el diseño para crear la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la aplicación.  
  
-   Crear estilos que aporten una apariencia coherente a toda la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de una aplicación.  
  
-   Enlazar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a datos para rellenar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a partir de datos y mantener los datos sincronizados con la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Cuando termine el tutorial, habrá compilado una aplicación independiente de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] que permitirá a los usuarios ver los informes de gastos de las personas seleccionadas.  La aplicación constará de varias páginas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hospedadas en una ventana del estilo del explorador.  
  
 El código de ejemplo que se utiliza para compilar este tutorial está disponible para [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] y [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)]; vea [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).  
  
<a name="Requirements"></a>   
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]  
  
 Para obtener más información sobre cómo instalar [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], vea [Instalar Visual Studio](../Topic/Install%20Visual%20Studio%202015.md).  
  
<a name="Create_The_Application_Code_Files"></a>   
## Crear el proyecto de aplicación  
 En esta sección, creará la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen.  
  
1.  Cree un nuevo proyecto de aplicación WPF en Visual Basic o Visual C\# denominado `ExpenseIt`.  Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/es-es/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
    > [!NOTE]
    >  En este tutorial se utiliza el control <xref:System.Windows.Controls.DataGrid> que está disponible en .NET Framework 4.  Asegúrese de que el proyecto tiene como destino .NET Framework 4.  Para obtener más información, vea [Cómo: Usar como destino una versión de .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
2.  Abra Application.xaml \(Visual Basic\) o App.xaml \(C\#\).  
  
     Este archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] define una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y los recursos de la aplicación. También se utiliza este archivo para especificar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se muestra automáticamente cuando se inicia la aplicación; en este caso, MainWindow.xaml.  
  
     Su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se debería parecer a lo siguiente en Visual Basic:  
  
     [!code-xml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     O así en C\#:  
  
     [!code-xml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3.  Abra MainWindow.xaml.  
  
     Este archivo de código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es la ventana principal de la aplicación y muestra contenido creado en páginas.  La clase <xref:System.Windows.Window> define las propiedades de una ventana, como su título, tamaño o icono, y controla los eventos, como cerrarse u ocultarse.  
  
4.  Cambie el elemento <xref:System.Windows.Window> por <xref:System.Windows.Navigation.NavigationWindow>.  
  
     Esta aplicación navegará a contenido diferente según la interacción del usuario.  Por consiguiente, <xref:System.Windows.Window> principal necesita cambiar a <xref:System.Windows.Navigation.NavigationWindow>.  <xref:System.Windows.Navigation.NavigationWindow> hereda todas las propiedades de <xref:System.Windows.Window>.  El elemento <xref:System.Windows.Navigation.NavigationWindow> del archivo XAML crea una instancia de la clase <xref:System.Windows.Navigation.NavigationWindow>.  Para obtener más información, consulte [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
5.  Cambie las siguientes propiedades en el elemento <xref:System.Windows.Navigation.NavigationWindow>:  
  
    -   Establezca la propiedad <xref:System.Windows.Window.Title%2A> en "ExpenseIt".  
  
    -   Establezca la propiedad <xref:System.Windows.FrameworkElement.Width%2A> en 500 píxeles.  
  
    -   Establezca la propiedad <xref:System.Windows.FrameworkElement.Height%2A> en 350 píxeles.  
  
    -   Quite los elementos <xref:System.Windows.Controls.Grid> entre las etiquetas <xref:System.Windows.Navigation.NavigationWindow>.  
  
     Su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se debería parecer a lo siguiente en Visual Basic:  
  
     [!code-xml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     O así en C\#:  
  
     [!code-xml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6.  Abra MainWindow.xaml.vb o MainWindow.xaml.cs.  
  
     Este archivo es un archivo de código subyacente que contiene el código para controlar los eventos declarados en MainWindow.xaml.  Este archivo contiene una clase parcial para la ventana definida en XAML.  
  
7.  Si está utilizando C\#, cambie la clase `MainWindow` para que se derive de <xref:System.Windows.Navigation.NavigationWindow>.  
  
     En Visual Basic, esto sucede automáticamente al cambiar la ventana en XAML.  
  
     El código debe ser similar al que se muestra a continuación.  
  
     [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
     [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
<a name="add_files_to_the_application"></a>   
## Agregar archivos a la aplicación  
 En esta sección, agregará dos páginas y una imagen a la aplicación.  
  
1.  Agregue una nueva página \(WPF\) al proyecto denominada `ExpenseItHome.xaml`.  Para obtener más información, consulte [Cómo: Agregar nuevos elementos a un proyecto de WPF](http://msdn.microsoft.com/es-es/17e6b238-fc32-4385-98ef-2f66ca09d9ad).  
  
     Esta página es la primera página que se muestra cuando se inicia la aplicación.  Mostrará una lista de personas y el usuario podrá seleccionar en esa lista la persona cuyo informe de gastos desee mostrar.  
  
2.  Abra ExpenseItHome.xaml.  
  
3.  Establezca <xref:System.Windows.Controls.Page.Title%2A> en "ExpenseIt \- Home".  
  
     Su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se debería parecer a lo siguiente en Visual Basic:  
  
     [!code-xml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     O a esto en C\#:  
  
     [!code-xml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4.  Abra MainWindow.xaml.  
  
5.  Establezca la propiedad <xref:System.Windows.Navigation.NavigationWindow.Source%2A> de <xref:System.Windows.Navigation.NavigationWindow> en "ExpenseItHome.xaml".  
  
     Esto establece ExpenseItHome.xaml como la primera página que se abre cuando se inicia la aplicación.  Su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se debería parecer a lo siguiente en Visual Basic:  
  
     [!code-xml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     O a esto en C\#:  
  
     [!code-xml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6.  Agregue una nueva página \(WPF\) al proyecto denominada `ExpenseReportPage.xaml`.  
  
     Esta página mostrará el informe de gastos de la persona que esté seleccionada en ExpenseItHome.xaml.  
  
7.  Abra ExpenseReportPage.xaml.  
  
8.  Establezca <xref:System.Windows.Controls.Page.Title%2A> en "ExpenseIt \- View Expense".  
  
     Su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se debería parecer a lo siguiente en Visual Basic:  
  
     [!code-xml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     O a esto en C\#:  
  
     [!code-xml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. Abra ExpenseItHome.xaml.vb y ExpenseReportPage.xaml.vb o ExpenseItHome.xaml.cs y ExpenseReportPage.xaml.cs.  
  
     Al crear un nuevo archivo de paginación, Visual Studio crea automáticamente un código subyacente.  Estos archivos de código subyacente controlan la lógica para responder a los datos proporcionados por el usuario.  
  
     El código debe ser similar al que se muestra a continuación.  
  
     [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
     [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
     [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
     [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. Agregue una imagen denominada watermark.png al proyecto.  Puede crear su propia imagen o copiar el archivo del código de ejemplo.  Para obtener más información, vea [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/es-es/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
<a name="Build_The_Application"></a>   
## Compilar y ejecutar la aplicación  
 En esta sección, se compila y ejecuta la aplicación.  
  
1.  Compile y ejecute la aplicación presionando F5 o seleccione **Iniciar depuración** en el menú **Debug**.  
  
     La siguiente ilustración muestra la aplicación con los botones <xref:System.Windows.Navigation.NavigationWindow>.  
  
     ![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2.  Cierre la aplicación para volver a [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
<a name="Add_Layout"></a>   
## Crear el diseño  
 El diseño proporciona un modo ordenado de colocar los elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], y también controla el tamaño y la posición de los mismos cuando la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] cambia de tamaño.  Normalmente se crea un diseño con uno de los controles de diseño siguientes:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 Cada uno de estos controles de diseño admite un tipo de diseño especial para sus elementos secundarios.  Es posible cambiar de tamaño las páginas de ExpenseIt, y cada página tiene elementos organizados horizontal y verticalmente junto con otros elementos.  Por lo tanto, <xref:System.Windows.Controls.Grid> es el elemento de diseño ideal para la aplicación.  
  
> [!NOTE]
>  Para obtener más información sobre los elementos <xref:System.Windows.Controls.Panel>, vea [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md).  Para obtener más información sobre diseño, vea [Diseño](../../../../docs/framework/wpf/advanced/layout.md).  
  
 En la sección, cree una tabla con una columna única con tres filas y un margen de 10 píxeles agregando definiciones de columna y de fila a la <xref:System.Windows.Controls.Grid> de ExpenseItHome.xaml.  
  
1.  Abra ExpenseItHome.xaml.  
  
2.  Establezca la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> en el elemento <xref:System.Windows.Controls.Grid> en "10,0,10,10", que corresponde a los márgenes izquierdo, superior, derecho e inferior.  
  
3.  Agregue el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] entre las etiquetas <xref:System.Windows.Controls.Grid> para crear las definiciones de columna y fila.  
  
     [!code-xml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     El <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas está establecido en <xref:System.Windows.GridLength.Auto%2A>, lo que quiere decir que las filas se dimensionarán según su contenido.  El <xref:System.Windows.Controls.RowDefinition.Height%2A> predeterminado es <xref:System.Windows.GridUnitType>, que significa que la fila será una proporción ponderada del espacio disponible.  Por ejemplo si cada una de dos filas tiene un alto de "\*", ambas tendrán un alto que es la mitad del espacio disponible.  
  
     Su <xref:System.Windows.Controls.Grid> debe tener la apariencia siguiente:  
  
     [!code-xml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
<a name="Add_Controls"></a>   
## Agregar controles  
 En esta sección, se actualiza la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la página principal para mostrar una lista de personas y los usuarios pueden seleccionar el nombre de la persona cuyo informe de gastos desean ver.  Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con una aplicación.  Para obtener más información, vea [Controles](../../../../docs/framework/wpf/controls/index.md).  
  
 Para crear esta [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], se han agregado los elementos siguientes a ExpenseItHome.xaml:  
  
-   Un control <xref:System.Windows.Controls.ListBox> \(para la lista de personas\).  
  
-   Un control <xref:System.Windows.Controls.Label> \(para el encabezado de la lista\).  
  
-   Un control <xref:System.Windows.Controls.Button> \(para hacer clic con objeto de ver el informe de gastos de la persona que está seleccionada en la lista\).  
  
 Cada control se coloca en una fila de la <xref:System.Windows.Controls.Grid> estableciendo la propiedad adjunta <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=fullName>.  Para obtener más información sobre propiedades adjuntas, vea [Información general sobre propiedades asociadas](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
1.  Abra ExpenseItHome.xaml.  
  
2.  Agregue el código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] siguiente entre las etiquetas <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3.  Compile y ejecute la aplicación.  
  
 La siguiente ilustración muestra los controles que crea el XAML en esta sección.  
  
 ![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
<a name="Add_an_Image"></a>   
## Agregar una imagen y un título  
 En esta sección, la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de la página principal se actualiza con una imagen y un título de página.  
  
1.  Abra ExpenseItHome.xaml.  
  
2.  Agregue otra columna a <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un <xref:System.Windows.Controls.ColumnDefinition.Width%2A> fijo de 230 píxeles.  
  
     [!code-xml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3.  Agregue otra fila a <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.  
  
     [!code-xml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4.  Mueva los controles a la segunda columna estableciendo <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=fullName> en 1.  Baje cada control una fila aumentando <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=fullName> en 1.  
  
     [!code-xml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5.  Establezca <xref:System.Windows.Controls.Panel.Background%2A> de <xref:System.Windows.Controls.Grid> para que sea el archivo de imagen watermark.png.  
  
     [!code-xml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6.  Antes de <xref:System.Windows.Controls.Border>, agregue <xref:System.Windows.Controls.Label> con el contenido "View Expense Report" para que sea el título de la página.  
  
     [!code-xml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7.  Compile y ejecute la aplicación.  
  
 En la ilustración siguiente se muestra el resultado de esta sección.  
  
 ![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
<a name="Add_Code_to_Process_Events"></a>   
## Agregar código para controlar eventos  
  
1.  Abra ExpenseItHome.xaml.  
  
2.  Agregue el controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> al elemento <xref:System.Windows.Controls.Button>.  Para obtener más información, vea [Cómo: Crear controladores de eventos simples](http://msdn.microsoft.com/es-es/b1456e07-9dec-4354-99cf-18666b64f480).  
  
     [!code-xml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3.  Abra ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs.  
  
4.  Agregue el siguiente código al controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, que hace que la ventana navegue hasta el archivo ExpenseReportPage.xaml.  
  
     [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
     [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
<a name="Create_the_UI_for_Pane2"></a>   
## Crear la interfaz de usuario para ExpenseReportPage  
 ExpenseReportPage.xaml muestra el informe de gastos de la persona que se seleccionó en ExpenseItHome.xaml.  En esta sección se agregan los controles y se crea la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para ExpenseReportPage.xaml.  También se agrega un fondo y colores de relleno a los distintos elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
1.  Abra ExpenseReportPage.xaml.  
  
2.  Agregue el código XAML siguiente entre las etiquetas <xref:System.Windows.Controls.Grid>.  
  
     Esta interfaz de usuario es similar a la interfaz de usuario creada en ExpenseItHome.xaml, con la salvedad de que los datos del informe se muestran en <xref:System.Windows.Controls.DataGrid>.  
  
     [!code-xml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3.  Compile y ejecute la aplicación.  
  
    > [!NOTE]
    >  Si obtiene un error que indica que <xref:System.Windows.Controls.DataGrid> no se encuentra o no existe, asegúrese de que el proyecto tiene como destino .NET Framework 4.  Para obtener más información, vea [Cómo: Usar como destino una versión de .NET Framework](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
4.  Haga clic en el botón **Ver**.  
  
     Aparecerá la página de informe de gastos.  
  
 La ilustración siguiente muestra los elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] agregados a ExpenseReportPage.xaml.  Observe que el botón de navegación hacia atrás está habilitado.  
  
 ![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
<a name="Add_Code_to_Style_a_Control"></a>   
## Estilo de los controles  
 Es habitual que todos los elementos del mismo tipo de una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] presenten la misma apariencia.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utiliza estilos para permitir la reutilización de las distintas apariencias en diversos elementos.  Esta posibilidad de reutilizar los estilos ayuda a simplificar la creación y la administración de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Para obtener más información acerca de los estilos, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  En esta sección se reemplazan por estilos los atributos que se definieron en pasos anteriores para los distintos elementos.  
  
1.  Abra Application.xaml o App.xaml.  
  
2.  Agregue el código XAML siguiente entre las etiquetas <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>:  
  
     [!code-xml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     Este [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] agrega los estilos siguientes:  
  
    -   `headerTextStyle`: para dar formato al control <xref:System.Windows.Controls.Label> de título de página.  
  
    -   `labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label>.  
  
    -   `columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
    -   `listHeaderStyle`: para dar formato a los controles <xref:System.Windows.Controls.Border> de encabezado de lista.  
  
    -   `listHeaderTextStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> de encabezado de lista.  
  
    -   `buttonStyle`: para dar formato a <xref:System.Windows.Controls.Button> en "ExpenseItHome.xaml".  
  
     Observe que los estilos son recursos y elementos secundarios del elemento de propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>.  En esta ubicación, los estilos se aplican a todos los elementos de una aplicación.  Para obtener un ejemplo del uso de los recursos en una aplicación de [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], consulte [Usar recursos de aplicaciones](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).  
  
3.  Abra ExpenseItHome.xaml.  
  
4.  Reemplace todo lo que hay entre los elementos <xref:System.Windows.Controls.Grid> por el siguiente XAML.  
  
     [!code-xml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos.  Por ejemplo `headerTextStyle` se aplica a <xref:System.Windows.Controls.Label> "View Expense Report".  
  
5.  Abra ExpenseReportPage.xaml.  
  
6.  Reemplace todo lo que hay entre los elementos <xref:System.Windows.Controls.Grid> por el siguiente XAML.  
  
     [!code-xml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     Esto agrega estilos a los elementos <xref:System.Windows.Controls.Border> y <xref:System.Windows.Controls.Label>.  
  
7.  Compile y ejecute la aplicación.  
  
     Después de agregar el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de esta sección, la aplicación presenta la misma apariencia que tenía antes de actualizarla con los estilos.  
  
<a name="Bind_Data_to_a_Control"></a>   
## Enlazar datos a controles  
 En esta sección se crean los datos [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] que se enlazan a varios controles.  
  
1.  Abra ExpenseItHome.xaml.  
  
2.  Después del elemento inicial <xref:System.Windows.Controls.Grid>, agregue el siguiente XAML para crear un <xref:System.Windows.Data.XmlDataProvider> que contenga los datos de cada persona.  
  
     Los datos se crean como un recurso <xref:System.Windows.Controls.Grid>.  Normalmente esto se cargaría como un archivo, pero por sencillez los datos se agregan alineados.  
  
     [!code-xml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3.  En el recurso <xref:System.Windows.Controls.Grid>, agregue la siguiente <xref:System.Windows.DataTemplate>, que define cómo mostrar los datos en <xref:System.Windows.Controls.ListBox>.  Para obtener más información sobre plantillas de datos, vea [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
     [!code-xml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4.  Reemplace <xref:System.Windows.Controls.ListBox> por el siguiente XAML.  
  
     [!code-xml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     Este XAML enlaza la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.ListBox> al origen de datos y aplica la plantilla de datos como <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.  
  
<a name="Connect_Data_to_Controls"></a>   
## Conectar los datos a los controles  
 En esta sección, escribirá el código que recupera el elemento actual que está seleccionado en la lista de personas de la página ExpenseItHome.xaml y que pasa su referencia al constructor de `ExpenseReportPage` durante la creación de instancias.  `ExpenseReportPage` establece su contexto de datos con el elemento que se pasa, que es el elemento con el que se enlazarán los controles definidos en ExpenseReportPage.xaml.  
  
1.  Abra ExpenseReportPage.xaml.vb o ExpenseReportPage.xaml.cs.  
  
2.  Agregue un constructor que tome un objeto de modo que pueda pasar los datos del informe de gastos de la persona seleccionada.  
  
     [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
     [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3.  Abra ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs.  
  
4.  Cambie el controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> para llamar al nuevo constructor que pasa los datos del informe de gastos de la persona seleccionada.  
  
     [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
     [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
<a name="Add_Style_to_Data"></a>   
## Dar estilos a los datos con plantillas de datos  
 En esta sección, actualizará la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para cada elemento de las listas enlazadas a datos utilizando las plantillas de datos.  
  
1.  Abra ExpenseReportPage.xaml.  
  
2.  Enlace el contenido de elementos <xref:System.Windows.Controls.Label> "Department" y "Name" a la propiedad de origen de datos adecuada.  Para obtener más información sobre el enlace de datos, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     [!code-xml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3.  Después de abrir el elemento <xref:System.Windows.Controls.Grid>, agregue las siguientes plantillas de datos, que definen cómo mostrar los datos del informe de gastos.  
  
     [!code-xml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4.  Aplique las plantillas a las columnas de <xref:System.Windows.Controls.DataGrid> que muestran los datos del informe de gastos.  
  
     [!code-xml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5.  Compile y ejecute la aplicación.  
  
6.  Seleccione una persona y haga clic en el botón **Ver**.  
  
 En la siguiente ilustración se muestran las dos páginas de la aplicación ExpenseIt con los controles, el diseño, los estilos, el enlace de datos y las plantillas de datos aplicados.  
  
 ![Capturas de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
<a name="Best_Practices"></a>   
## Procedimientos recomendados  
 En este ejemplo se muestra una característica específica de WPF y, por consiguiente, no sigue las recomendaciones de desarrollo de aplicaciones.  Para obtener información completa sobre los procedimientos recomendados de desarrollo de aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], consulte los temas siguientes según corresponda:  
  
-   Accesibilidad: [Procedimientos de accesibilidad recomendados](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   Seguridad: [Seguridad](../../../../docs/framework/wpf/security-wpf.md)  
  
-   Localización: [Información general sobre la localización y globalización de WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   Rendimiento: [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
<a name="Whats_Next"></a>   
## Pasos adicionales  
 Ahora tiene a su disposición varias técnicas para crear una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mediante [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Ya debería tener una idea general de los bloques de creación necesarios para la creación de una aplicación [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] enlazada a datos.  Este tema no pretende ser exhaustivo, pero se supone que ahora ya conoce algunas de las posibilidades que puede descubrir por sí mismo además de las técnicas que se tratan en este tema.  
  
 Para obtener más información sobre la arquitectura y los modelos de programación WPF, consulte los siguientes temas:  
  
-   [Arquitectura de WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [Diseño](../../../../docs/framework/wpf/advanced/layout.md)  
  
 Para obtener información sobre la creación de aplicaciones, vea los siguientes temas:  
  
-   [Desarrollo de aplicaciones](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [Controles](../../../../docs/framework/wpf/controls/index.md)  
  
-   [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## Vea también  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Estilos y plantillas](../../../../docs/framework/wpf/controls/styles-and-templates.md)