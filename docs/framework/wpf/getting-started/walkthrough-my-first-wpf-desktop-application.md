---
title: 'Tutorial: Mi primera aplicación de escritorio WPF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3725e96b514b0204f10f6b5c45ed2bbec1d892de
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a>Tutorial: Mi primera aplicación de escritorio WPF
Este tutorial proporciona una introducción al desarrollo de un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplicación que incluye los elementos que son comunes a la mayoría [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado, código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos. 
  
Este tutorial le guía a través del desarrollo de un sencillo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación siguiendo estos pasos. 
  
-   Definir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para diseñar el aspecto de la aplicación [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. 
  
-   Escribir código para crear el comportamiento de la aplicación. 
  
-   Crear una definición de aplicación para administrar la aplicación. 
  
-   Agregar controles y crear un diseño para crear la aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Creación de estilos para crear una apariencia coherente en toda una aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. 
  
-   Enlace el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a los datos en ambos rellenar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de datos y mantener los datos y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sincronizado. 
  
Al final del tutorial, habrá creado una independiente [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] aplicación que permite a los usuarios ver informes de gastos para los usuarios seleccionados. La aplicación podría estar compuesta por varios [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] páginas que se hospedan en una ventana del estilo del explorador. 
  
El código de ejemplo que se utiliza para compilar este tutorial está disponible para [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] y [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] en [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008). 

## <a name="prerequisites"></a>Requisitos previos  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)] o posterior

Para obtener más información acerca de cómo instalar la versión más reciente de Visual Studio, vea [instalar Visual Studio](/visualstudio/install/install-visual-studio).
  
## <a name="creating-the-application-project"></a>Creación del proyecto de la aplicación  
En esta sección, va a crear la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen. 
  
1. Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `ExpenseIt`. Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82). 
  
    > [!NOTE]
    >  Este tutorial se utiliza el <xref:System.Windows.Controls.DataGrid> control que está disponible en .NET Framework 4. Estar seguro de que su proyecto tiene como destino .NET Framework 4 o posterior. Para obtener más información, consulte [Cómo: Usar como destino una versión de .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
2. Abra Application.xaml (Visual Basic) o App.xaml (C#). 
  
     Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo define un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación y los recursos de la aplicación. También usa este archivo para especificar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que automáticamente se muestra cuando se inicia la aplicación; en este caso, MainWindow.xaml. 
  
     El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     O a este en C#:  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. Abra MainWindow.xaml. 
  
     Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo es la ventana principal de la aplicación y muestra el contenido creado en páginas. La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono y controla los eventos, por ejemplo, cerrar u ocultar. 
  
4. Cambiar el <xref:System.Windows.Window> elemento a una <xref:System.Windows.Navigation.NavigationWindow>. 
  
     Esta aplicación irá a contenido diferente según la interacción del usuario. Por lo tanto, el método main <xref:System.Windows.Window> debe cambiarse a un <xref:System.Windows.Navigation.NavigationWindow>. <xref:System.Windows.Navigation.NavigationWindow> hereda todas las propiedades de <xref:System.Windows.Window>. El <xref:System.Windows.Navigation.NavigationWindow> elemento en el archivo XAML crea una instancia de la <xref:System.Windows.Navigation.NavigationWindow> clase. Para obtener más información, consulte [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md). 
  
5. Cambie las propiedades siguientes en el <xref:System.Windows.Navigation.NavigationWindow> elemento:  
  
    -   Establecer el <xref:System.Windows.Window.Title%2A> propiedad en "ExpenseIt". 
  
    -   Establecer el <xref:System.Windows.FrameworkElement.Width%2A> propiedad en 500 píxeles. 
  
    -   Establecer el <xref:System.Windows.FrameworkElement.Height%2A> propiedad a 350 píxeles. 
  
    -   Quitar el <xref:System.Windows.Controls.Grid> elementos entre el <xref:System.Windows.Navigation.NavigationWindow> etiquetas. 
  
     El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     O a este en C#:  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. Abra MainWindow.xaml.vb o MainWindow.xaml.cs. 
  
     Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en MainWindow.xaml. Este archivo contiene una clase parcial para la ventana definida en código XAML. 
  
7. Si está utilizando C#, cambie la `MainWindow` clase se deriva de <xref:System.Windows.Navigation.NavigationWindow>. 
  
     En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en código XAML. 
  
     El código debe ser similar al siguiente. 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a>Adición de archivos a la aplicación  
En esta sección, va a agregar dos páginas y una imagen a la aplicación. 
  
1. Agregar una nueva página (WPF) al proyecto denominado `ExpenseItHome.xaml`. Para obtener más información, consulte [Cómo: agregar nuevos elementos a un proyecto de WPF](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad). 
  
     Esta página es la primera que se muestra cuando se inicia la aplicación. Mostrará una lista de personas entre las que un usuario puede seleccionar una para mostrar el informe de gastos. 
  
2. Abra ExpenseItHome.xaml. 
  
3. Establecer el <xref:System.Windows.Controls.Page.Title%2A> a "ExpenseIt - Home". 
  
     El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     O a este en C#:  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. Abra MainWindow.xaml. 
  
5. Establecer el <xref:System.Windows.Navigation.NavigationWindow.Source%2A> propiedad en el <xref:System.Windows.Navigation.NavigationWindow> en "ExpenseItHome.xaml". 
  
     Así se establece ExpenseItHome.xaml como la primera página que se abre al iniciar la aplicación. El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     O a este en C#:  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. Agregar una nueva página (WPF) al proyecto denominado `ExpenseReportPage.xaml`. 
  
     Esta página mostrará el informe de gastos de la persona que se haya seleccionado en ExpenseItHome.xaml. 
  
7. Abra ExpenseReportPage.xaml. 
  
8. Establecer el <xref:System.Windows.Controls.Page.Title%2A> en "ExpenseIt - ver gastos". 
  
     El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     O a este en C#:  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. Abra ExpenseItHome.xaml.vb y ExpenseReportPage.xaml.vb o ExpenseItHome.xaml.cs y ExpenseReportPage.xaml.cs. 
  
     Cuando se crea un archivo de página, Visual Studio crea automáticamente un archivo de código subyacente. Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario. 
  
     El código debe ser similar al siguiente. 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. Agregue una imagen denominada *watermark.png* al proyecto. Puede crear su propia imagen o copiar el archivo del código de ejemplo. Para obtener más información, consulte [Cómo: agregar elementos existentes a un proyecto](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)). 

## <a name="building-and-running-the-application"></a>Compilar y ejecutar la aplicación  
En esta sección, va a compilar y ejecutar la aplicación. 
  
1. Compile y ejecute la aplicación presionando F5 o seleccionando **Iniciar depuración** desde el **depurar** menú. 
  
     En la siguiente ilustración muestra la aplicación con el <xref:System.Windows.Navigation.NavigationWindow> botones. 
  
     ![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")  
  
2. Cierre la aplicación para volver a [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]. 
  
## <a name="creating-the-layout"></a>Crear un diseño  
Diseño proporciona una manera ordenada para colocar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos y también administra el tamaño y la posición de dichos elementos cuando un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se cambia el tamaño. Normalmente, se crea un diseño con uno de los controles de diseño siguientes:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
Cada uno de estos controles de diseño admite un tipo especial de diseño para sus elementos secundarios. Puede cambiar el tamaño de las páginas de ExpenseIt, y cada página tiene elementos organizados en horizontal y vertical junto con otros elementos. Por lo tanto, el <xref:System.Windows.Controls.Grid> es el elemento de diseño ideal para la aplicación. 
  
> [!NOTE]
>  Para obtener más información acerca de <xref:System.Windows.Controls.Panel> elementos, consulte [paneles de información general sobre](../../../../docs/framework/wpf/controls/panels-overview.md). Para obtener más información acerca del diseño, vea [diseño](../../../../docs/framework/wpf/advanced/layout.md). 
  
En la sección, se crea una tabla de una sola columna con tres filas y un margen de 10 píxeles agregando definiciones de columna y fila a la <xref:System.Windows.Controls.Grid> en ExpenseItHome.xaml. 
  
1. Abra ExpenseItHome.xaml. 
  
2. Establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad en el <xref:System.Windows.Controls.Grid> elemento a "10,0,10,10", que corresponde a los márgenes izquierdo, superior, derecho e inferior. 
  
3. Agregue el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] entre el <xref:System.Windows.Controls.Grid> etiquetas para crear las definiciones de fila y columna. 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     El <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas se establece en <xref:System.Windows.GridLength.Auto%2A> lo que significa que se dimensionarán las filas se base en el contenido de las filas. El valor predeterminado <xref:System.Windows.Controls.RowDefinition.Height%2A> es <xref:System.Windows.GridUnitType.Star> ajuste de tamaño, lo que significa que la fila será una proporción ponderada del espacio disponible. Por ejemplo, si dos filas tienen un alto de "*", ambas tendrán un alto que sea la mitad del espacio disponible.  
  
     Su <xref:System.Windows.Controls.Grid> debería ser ahora similar el siguiente código XAML:  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a>Agregar controles  
En esta sección, la página principal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se actualiza para mostrar una lista de personas que los usuarios pueden seleccionar para mostrar el informe de gastos para un rol seleccionado. Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación. Para obtener más información, consulte [Controles](../../../../docs/framework/wpf/controls/index.md). 
  
Para crear esta [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], se agregan los elementos siguientes a ExpenseItHome.xaml:  
  
-   <xref:System.Windows.Controls.ListBox> (para obtener la lista de personas). 
  
-   <xref:System.Windows.Controls.Label> (para el encabezado de lista). 
  
-   <xref:System.Windows.Controls.Button> (debe hacer clic para ver el informe de gastos de la persona que está seleccionada en la lista). 
  
Cada control se coloca en una fila de la <xref:System.Windows.Controls.Grid> estableciendo el <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> propiedad adjunta. Para obtener más información acerca de las propiedades asociadas, consulte [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md). 
  
1. Abra ExpenseItHome.xaml. 
  
2. Agregue el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] entre el <xref:System.Windows.Controls.Grid> etiquetas. 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. Compile y ejecute la aplicación. 
  
En la siguiente ilustración se muestran los controles creados por el código XAML en esta sección. 
  
![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")  
  
## <a name="adding-an-image-and-a-title"></a>Agregar una imagen y un título  
En esta sección, la página principal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se actualiza con una imagen y un título de página. 
  
1. Abra ExpenseItHome.xaml. 
  
2. Agregue otra columna a la <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un fijo <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de 230 píxeles. 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. Agregue otra fila a la <xref:System.Windows.Controls.Grid.RowDefinitions%2A>. 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. Mover los controles a la segunda columna estableciendo <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> en 1. Baje cada control una fila aumentando el <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> en 1. 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. Establecer el <xref:System.Windows.Controls.Panel.Background%2A> de la <xref:System.Windows.Controls.Grid> sea el archivo de imagen watermark.png. 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. Antes de la <xref:System.Windows.Controls.Border>, agregue un <xref:System.Windows.Controls.Label> con el contenido "View Expense Report" para que sea el título de la página. 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. Compile y ejecute la aplicación. 
  
En la ilustración siguiente se muestran los resultados de esta sección. 
  
![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")  
  
## <a name="adding-code-to-handle-events"></a>Agregar código para controlar eventos  
  
1. Abra ExpenseItHome.xaml. 
  
2. Agregar un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para el <xref:System.Windows.Controls.Button> elemento. Para obtener más información, consulte [Cómo: crear un controlador de eventos Simple](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480). 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. Abra el archivo ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs. 
  
4. Agregue el código siguiente a la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> el controlador de eventos, lo que hace que la ventana para navegar hasta el archivo ExpenseReportPage.xaml. 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a>Crear la interfaz de usuario para ExpenseReportPage  
ExpenseReportPage.xaml muestra el informe de gastos de la persona que se seleccionó en ExpenseItHome.xaml. En esta sección se agregan controles y se crea el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para ExpenseReportPage.xaml. En esta sección también agrega los colores de fondo y relleno a los distintos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos. 
  
1. Abra ExpenseReportPage.xaml. 
  
2. Agregue el código XAML siguiente entre las etiquetas <xref:System.Windows.Controls.Grid>. 
  
     Esta interfaz de usuario es similar a la interfaz de usuario creada en ExpenseItHome.xaml salvo los datos del informe se muestran en un <xref:System.Windows.Controls.DataGrid>. 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. Compile y ejecute la aplicación. 
  
    > [!NOTE]
    >  Si se produce un error que el <xref:System.Windows.Controls.DataGrid> no se encontró o no existe, asegúrese de que el proyecto tiene como destino .NET Framework 4 o posterior. Para obtener más información, consulte [Cómo: Usar como destino una versión de .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework). 
  
4. Haga clic en el **vista** botón. 
  
     Se mostrará la página de informe de gastos 
  
La siguiente ilustración muestra el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos agregados a ExpenseReportPage.xaml. Observe que el botón de navegación hacia atrás está habilitado. 
  
![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")  
  
## <a name="styling-controls"></a>Aplicar estilos a controles  
La apariencia de varios elementos a menudo puede ser el mismo para todos los elementos del mismo tipo en un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utiliza estilos para permitir que las apariencias sean reutilizables en varios elementos. La reutilización de estilos ayuda a simplificar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la creación y administración. Para obtener más información sobre los estilos, consulte [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md). En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos. 
  
1. Abra Application.xaml o App.xaml. 
  
2. Agregue el código XAML siguiente entre las <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> etiquetas:  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] agrega los estilos siguientes:  
  
    -  `headerTextStyle`: para dar formato al título de la página <xref:System.Windows.Controls.Label>. 
  
    -  `labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> . 
  
    -  `columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>. 
  
    -  `listHeaderStyle`: para dar formato a los controles del encabezado de lista <xref:System.Windows.Controls.Border> . 
  
    -  `listHeaderTextStyle`: Para dar formato al encabezado de lista <xref:System.Windows.Controls.Label>. 
  
    -  `buttonStyle`: Para dar formato a la <xref:System.Windows.Controls.Button> en ExpenseItHome.xaml. 
  
     Tenga en cuenta que los estilos son recursos y elementos secundarios de la <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento property. En esta ubicación, los estilos se aplican a todos los elementos de una aplicación. Para obtener un ejemplo del uso de recursos en un [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] aplicación, consulte [recursos de la aplicación de uso](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md). 
  
3. Abra ExpenseItHome.xaml. 
  
4. Reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente. 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos. Por ejemplo, el `headerTextStyle` se aplica a "View Expense Report" <xref:System.Windows.Controls.Label>. 
  
5. Abra ExpenseReportPage.xaml. 
  
6. Reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente. 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     Esto agrega estilos a los elementos <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Border> . 
  
7. Compile y ejecute la aplicación. 
  
     Después de agregar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en esta sección, la aplicación tiene el mismo aspecto igual que antes de que se actualiza con los estilos. 
  
## <a name="binding-data-to-a-control"></a>Enlazar datos a un control  
En esta sección, creará el [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] datos que está enlazados a varios controles. 
  
1. Abra ExpenseItHome.xaml. 
  
2. Después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue el siguiente código XAML para crear un <xref:System.Windows.Data.XmlDataProvider> que contiene los datos de cada persona. 
  
     Los datos se crean como un <xref:System.Windows.Controls.Grid> recursos. Normalmente esto se cargaría como archivo, pero los datos se agregan en línea para simplificar. 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. En el <xref:System.Windows.Controls.Grid> recursos, agregue el siguiente <xref:System.Windows.DataTemplate>, que define cómo mostrar los datos en el <xref:System.Windows.Controls.ListBox>. Para más información sobre las plantillas de datos, consulte [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md). 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. Reemplazar el existente <xref:System.Windows.Controls.ListBox> con el código XAML siguiente. 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     Este código XAML enlaza la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.ListBox> al origen de datos y aplica la plantilla de datos como el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>. 
  
## <a name="connecting-data-to-controls"></a>Conectar los datos a controles  
En esta sección, se escribe el código que recupera el elemento actual que está seleccionado en la lista de personas en la página ExpenseItHome.xaml y pasa su referencia al constructor de `ExpenseReportPage` durante la creación de instancias. `ExpenseReportPage` establece el contexto de datos con el elemento pasado, que es a lo que los controles definidos en ExpenseReportPage.xaml se enlazarán. 
  
1. Abra ExpenseReportPage.xaml.vb o ExpenseReportPage.xaml.cs. 
  
2. Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada. 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. Abra el archivo ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs. 
  
4. Cambiar el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para llamar al constructor nuevo pasar los datos de informe de gastos de la persona seleccionada. 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a>Datos de aplicación de estilos con las plantillas de datos  
En esta sección, se actualiza el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para cada elemento de los datos enlazados listas mediante el uso de plantillas de datos. 
  
1. Abra ExpenseReportPage.xaml. 
  
2. Enlazar el contenido de la "Name" y "Departamento" <xref:System.Windows.Controls.Label> propiedad de origen de elementos a los datos apropiados. Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md). 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. Después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue las siguientes plantillas de datos, que definen cómo se muestran los datos de informe de gastos.  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. Aplicar las plantillas a la <xref:System.Windows.Controls.DataGrid> datos de informe de las columnas que muestran el gasto. 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. Compile y ejecute la aplicación. 
  
6. Seleccione una persona y haga clic en el **vista** botón. 
  
 La ilustración siguiente muestra ambas páginas de la aplicación ExpenseIt con los controles, el diseño, los estilos, el enlace de datos y las plantillas de datos aplicadas. 
  
 ![Capturas de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")  
  
## <a name="best-practices"></a>Procedimientos recomendados  
En este ejemplo, se ilustra una característica específica de WPF y, por consiguiente, no sigue los procedimientos recomendados para el desarrollo de aplicaciones. Para una completa cobertura de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] prácticas recomendadas de desarrollo de aplicaciones, vea los temas siguientes según corresponda:  
  
-   Accesibilidad: [Procedimientos de accesibilidad recomendados](../../../../docs/framework/ui-automation/accessibility-best-practices.md)  
  
-   Seguridad - [seguridad](../../../../docs/framework/wpf/security-wpf.md)  
  
-   Localización: [Información general sobre la globalización y la localización de WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)  
  
-   Rendimiento: [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
  
## <a name="whats-next"></a>Pasos adicionales  
Ahora tiene una serie de técnicas a su disposición para crear un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Ahora debería tener un amplio conocimiento de los bloques de creación básicos de un enlace de datos [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] aplicación. Este tema no pretende ser exhaustivo, pero espero que ya tenga una idea de las posibilidades que puede descubrir por sí mismo además de las técnicas descritas en este tema. 
  
 Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:  
  
-   [Arquitectura de WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [Diseño](../../../../docs/framework/wpf/advanced/layout.md)  
  
 Para más información sobre la creación de aplicaciones, vea los temas siguientes:  
  
-   [Desarrollo de aplicaciones](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [Controles](../../../../docs/framework/wpf/controls/index.md)  
  
-   [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Estilos y plantillas](../../../../docs/framework/wpf/controls/styles-and-templates.md)
