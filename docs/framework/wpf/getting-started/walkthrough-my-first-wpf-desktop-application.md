---
title: Cree su primera aplicación WPF en Visual Studio 2019 - .NET Framework
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 65b6fe31e86380162e90820c2cf118a9d1b96b4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186585"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Tutorial: Crear la primera aplicación WPF en Visual Studio 2019

En este artículo se muestra cómo desarrollar una aplicación de escritorio de Windows Presentation Foundation (WPF) que incluye los elementos que son comunes a la mayoría de las aplicaciones WPF: marcado de Lenguaje XAML (Extensible Application Markup Language) extensible, código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos. Para desarrollar la aplicación, usará Visual Studio.

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Cree un proyecto WPFWPF.
> - Use XAML para diseñar la apariencia de la interfaz de usuario (UI) de la aplicación.
> - Escribir código para compilar el comportamiento de la aplicación.
> - Cree una definición de aplicación para administrar la aplicación.
> - Agregue controles y cree el diseño para componer la interfaz de usuario de la aplicación.
> - Cree estilos para una apariencia coherente en toda la interfaz de usuario de la aplicación.
> - Enlazar la interfaz de usuario a los datos, tanto para rellenar la interfaz de usuario a partir de datos y para mantener los datos y la interfaz de usuario sincronizados.

Al final del tutorial, habrá creado una aplicación independiente de Windows que permite a los usuarios ver informes de gastos para personas seleccionadas. La aplicación se compone de varias páginas WPFWPF que se hospedan en una ventana de estilo explorador.

> [!TIP]
> El código de ejemplo que se usa en este tutorial está disponible tanto para Visual Basic como para C. en [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).
>
> Puede alternar el idioma de código del código de ejemplo entre C- y Visual Basic mediante el selector de idioma en la parte superior de esta página.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo de desarrollo de **escritorio de .NET** instalada.

   Para obtener más información acerca de la instalación de la versión más reciente de Visual Studio, vea [Instalar Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Crear el proyecto de aplicación

El primer paso es crear la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen.

1. Cree un nuevo proyecto de aplicación WPF **`ExpenseIt`** en Visual Basic o Visual C. denominado:

   1. Abra Visual Studio y seleccione **Crear un nuevo proyecto** en el menú **Introducción.**

      Se abre el cuadro de diálogo **Crear un nuevo proyecto.**

   2. En la lista desplegable **Idioma,** seleccione **C o** **Visual Basic**.

   3. Seleccione la plantilla **Aplicación WPF (.NET Framework)** y, a continuación, seleccione **Siguiente**.

      ![Cuadro de diálogo Crear un proyecto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      Se abre el cuadro de diálogo **Configurar el nuevo proyecto.**

   4. Escriba el **`ExpenseIt`** nombre del proyecto y, a continuación, seleccione **Crear**.

      ![Configurar un nuevo cuadro de diálogo de proyecto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio crea el proyecto y abre el diseñador para la ventana de aplicación predeterminada denominada **MainWindow.xaml**.

2. Abra *Application.xaml* (Visual Basic) o *App.xaml* (C-).

    Este archivo XAML define una aplicación WPFWPF y cualquier recurso de aplicación. También se usa este archivo para especificar la interfaz de usuario, en este caso *MainWindow.xaml*, que se muestra automáticamente cuando se inicia la aplicación.

    El XAML debe tener el siguiente aspecto en Visual Basic:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Y, como lo siguiente, en C-:

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Abra *MainWindow.xaml*.

    Este archivo XAML es la ventana principal de la aplicación y muestra el contenido creado en las páginas. La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono, y controla eventos, como cerrar u ocultar.

4. Cambie <xref:System.Windows.Window> el elemento <xref:System.Windows.Navigation.NavigationWindow>a un , como se muestra en el siguiente XAML:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Esta aplicación navega a contenido diferente dependiendo de la entrada del usuario. Esta es la <xref:System.Windows.Window> razón por la <xref:System.Windows.Navigation.NavigationWindow>que el principal necesita ser cambiado a un archivo . <xref:System.Windows.Navigation.NavigationWindow>hereda todas las <xref:System.Windows.Window>propiedades de . El <xref:System.Windows.Navigation.NavigationWindow> elemento del archivo XAML crea <xref:System.Windows.Navigation.NavigationWindow> una instancia de la clase. Para obtener más información, consulte [Información general sobre la navegación](../app-development/navigation-overview.md).

5. Elimine <xref:System.Windows.Controls.Grid> los elementos <xref:System.Windows.Navigation.NavigationWindow> de entre las etiquetas.

6. Cambie las siguientes propiedades en <xref:System.Windows.Navigation.NavigationWindow> el código XAML para el elemento:

    - Establezca <xref:System.Windows.Window.Title%2A> la propiedad`ExpenseIt`en " ".

    - Establezca <xref:System.Windows.FrameworkElement.Height%2A> la propiedad en 350 píxeles.

    - Establezca <xref:System.Windows.FrameworkElement.Width%2A> la propiedad en 500 píxeles.

    El XAML debe tener el siguiente aspecto para Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    Y de la siguiente manera para C-:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Abra *MainWindow.xaml.vb* o *MainWindow.xaml.cs*.

    Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en *MainWindow.xaml*. Este archivo contiene una clase parcial para la ventana definida en código XAML.

8. Si está utilizando C,, `MainWindow` cambie la <xref:System.Windows.Navigation.NavigationWindow>clase para derivar de . (En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en XAML.) Ahora, el código de CTM debería tener este aspecto:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Añadir archivos a la aplicación

En esta sección, agregará dos páginas y una imagen a la aplicación.

1. Agregue una nueva página al proyecto *`ExpenseItHome.xaml`* y asígnelle el nombre :

   1. En **el Explorador**de soluciones **`ExpenseIt`** , haga clic con el botón derecho en el nodo del proyecto y elija **Agregar** > **página**.

   1. En el cuadro de diálogo **Agregar nuevo elemento,** la plantilla **Página (WPF)** ya está seleccionada. Escriba el **`ExpenseItHome`** nombre y, a continuación, seleccione **Agregar**.

    Esta página es la primera página que se muestra cuando se inicia la aplicación. Mostrará una lista de personas para las que seleccionar, para mostrar un informe de gastos.

1. Abrir *`ExpenseItHome.xaml`*.

1. Establezca <xref:System.Windows.Controls.Page.Title%2A> el`ExpenseIt - Home`botón en " ".

1. Establezca `DesignHeight` los 350 píxeles y los `DesignWidth` 500 píxeles.

    El XAML ahora aparece de la siguiente manera para Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    Y de la siguiente manera para C-:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Abra *MainWindow.xaml*.

1. Agregue <xref:System.Windows.Navigation.NavigationWindow.Source%2A> una propiedad <xref:System.Windows.Navigation.NavigationWindow> al elemento y`ExpenseItHome.xaml`establézquela en " ".

    Esto *`ExpenseItHome.xaml`* establece que será la primera página abierta cuando se inicia la aplicación.

    Ejemplo xaml en Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    Y en C-:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > También puede establecer la propiedad **Source** en la categoría **Varios** de la ventana **Propiedades.**
   >
   > ![Propiedad de origen en la ventana Propiedades](./media/properties-source.png)

1. Agregue otra nueva página WPF al proyecto y asígnelse el nombre *ExpenseReportPage.xaml*::

   1. En **el Explorador**de soluciones **`ExpenseIt`** , haga clic con el botón derecho en el nodo del proyecto y elija **Agregar** > **página**.

   1. En el cuadro de diálogo **Agregar nuevo elemento,** seleccione la plantilla **Página (WPF).** Escriba el nombre **ExpenseReportPage**y, a continuación, seleccione **Agregar**.

    Esta página mostrará el informe de gastos **`ExpenseItHome`** de la persona seleccionada en la página.

1. Abra *ExpenseReportPage.xaml*.

1. Establezca <xref:System.Windows.Controls.Page.Title%2A> el`ExpenseIt - View Expense`botón en " ".

1. Establezca `DesignHeight` los 350 píxeles y los `DesignWidth` 500 píxeles.

    *ExpenseReportPage.xaml* ahora tiene el siguiente aspecto en Visual Basic:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Y, como lo siguiente, en C-:

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Abra *ExpenseItHome.xaml.vb* y *ExpenseReportPage.xaml.vb*o *ExpenseItHome.xaml.cs* y *ExpenseReportPage.xaml.cs*.

    Al crear un nuevo archivo de página, Visual Studio crea automáticamente su archivo *de código subyacente.* Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.

    El código debe tener **`ExpenseItHome`** el siguiente aspecto para:

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Y como lo siguiente para **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Agregue una imagen denominada *watermark.png* al proyecto. Puede crear su propia imagen, copiar el archivo del código de ejemplo u obtenerlo desde el repositorio GitHub [de microsoft/WPF-Samples.](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)

    1. Haga clic con el botón derecho en el nodo del proyecto y seleccione **Agregar** > **elemento existente**o pulse **Mayús**+**Alt**+**A**.

    2. En el cuadro de diálogo **Agregar elemento existente,** establezca el filtro de archivos en **Todos los archivos** o **Archivos**de imagen , busque el archivo de imagen que desea usar y, a continuación, seleccione **Agregar**.

## <a name="build-and-run-the-application"></a>Compilación y ejecución de la aplicación

1. Para compilar y ejecutar la aplicación, presione **F5** o seleccione **Iniciar depuración** en el menú **Depurar.**

    La siguiente ilustración muestra <xref:System.Windows.Navigation.NavigationWindow> la aplicación con los botones:

    ![Aplicación después de compilarla y ejecutarla.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Cierre la aplicación para volver a Visual Studio.

## <a name="create-the-layout"></a>Crear el diseño

Layout proporciona una forma ordenada de colocar elementos de interfaz de usuario y también administra el tamaño y la posición de esos elementos cuando se cambia el tamaño de una interfaz de usuario. Normalmente, se crea un diseño con uno de los controles de diseño siguientes:

- <xref:System.Windows.Controls.Canvas>- Define un área dentro de la cual puede colocar explícitamente los elementos secundarios mediante coordenadas relativas al área Canvas.
- <xref:System.Windows.Controls.DockPanel>- Define un área donde puede organizar los elementos secundarios horizontal o verticalmente, en relación entre sí.
- <xref:System.Windows.Controls.Grid>- Define un área de cuadrícula flexible que consta de columnas y filas.
- <xref:System.Windows.Controls.StackPanel>- Organiza los elementos secundarios en una sola línea que se puede orientar horizontal o verticalmente.
- <xref:System.Windows.Controls.VirtualizingStackPanel>- Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.
- <xref:System.Windows.Controls.WrapPanel>- Coloca los elementos secundarios en posición secuencial de izquierda a derecha, rompiendo el contenido a la siguiente línea en el borde del cuadro contenedor. El orden posterior se realiza secuencialmente de arriba a abajo o de derecha a izquierda, dependiendo del valor de la Propiedad Orientation.

Cada uno de estos controles de diseño admite un tipo determinado de diseño para sus elementos secundarios. `ExpenseIt`las páginas se pueden cambiar de tamaño y cada página tiene elementos que se organizan horizontal y verticalmente junto con otros elementos. En este ejemplo, se <xref:System.Windows.Controls.Grid> utiliza como elemento de diseño para la aplicación.

> [!TIP]
> Para obtener <xref:System.Windows.Controls.Panel> más información acerca de los elementos, consulte [Introducción a los paneles](../controls/panels-overview.md). Para obtener más información sobre el diseño, consulte [Diseño](../advanced/layout.md).

En esta sección, creará una tabla de una sola columna con tres filas y un <xref:System.Windows.Controls.Grid> *`ExpenseItHome.xaml`* margen de 10 píxeles agregando definiciones de columna y fila al archivo in .

1. En *`ExpenseItHome.xaml`*, <xref:System.Windows.FrameworkElement.Margin%2A> establezca la <xref:System.Windows.Controls.Grid> propiedad del elemento en "10,0,10,10", que corresponde a los márgenes izquierdo, superior, derecho e inferior:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > También puede establecer los valores **de Margen** en la ventana **Propiedades,** en la categoría **Diseño:**
   >
   > ![Valores de margen en la ventana Propiedades](./media/properties-margin.png)

2. Agregue el siguiente <xref:System.Windows.Controls.Grid> XAML entre las etiquetas para crear las definiciones de fila y columna:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    El <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas <xref:System.Windows.GridLength.Auto%2A>se establece en , lo que significa que el tamaño de las filas se basa en el contenido de las filas. El <xref:System.Windows.Controls.RowDefinition.Height%2A> valor <xref:System.Windows.GridUnitType.Star> predeterminado es el tamaño, lo que significa que la altura de la fila es una proporción ponderada del espacio disponible. Por ejemplo, si dos <xref:System.Windows.Controls.RowDefinition.Height%2A> filas tienen cada una de "*", cada una tiene una altura que es la mitad del espacio disponible.

    Ahora <xref:System.Windows.Controls.Grid> debe contener el siguiente XAML:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Agregar controles

En esta sección, actualizará la interfaz de usuario de la página principal para mostrar una lista de personas, donde selecciona una persona para mostrar su informe de gastos. Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación. Para obtener más información, consulte [Controles](../controls/index.md).

Para crear esta interfaz de usuario, *`ExpenseItHome.xaml`* agregará los siguientes elementos a:

- A <xref:System.Windows.Controls.ListBox> (para la lista de personas).
- A <xref:System.Windows.Controls.Label> (para el encabezado de lista).
- A <xref:System.Windows.Controls.Button> (para hacer clic para ver el informe de gastos de la persona seleccionada en la lista).

Cada control se coloca en <xref:System.Windows.Controls.Grid> una <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> fila de la estableciendo la propiedad adjunta. Para obtener más información acerca de las propiedades adjuntas, vea [Información general sobre propiedades adjuntas](../advanced/attached-properties-overview.md).

1. En *`ExpenseItHome.xaml`*, agregue el siguiente <xref:System.Windows.Controls.Grid> XAML en algún lugar entre las etiquetas:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > También puede crear los controles arrastrándolos desde la ventana Cuadro de **herramientas** a la ventana de diseño y, a continuación, estableciendo sus propiedades en la ventana **Propiedades.**

2. Compile y ejecute la aplicación.

    En la ilustración siguiente se muestran los controles que ha creado:

![Captura de pantalla de ejemplo de ExpenseIt que muestra una lista de nombres](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Añadir una imagen y un título

En esta sección, actualizará la interfaz de usuario de la página principal con una imagen y un título de página.

1. En *`ExpenseItHome.xaml`*, agregue otra <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> columna <xref:System.Windows.Controls.ColumnDefinition.Width%2A> a la con un fijo de 230 píxeles:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. Agregue otra fila <xref:System.Windows.Controls.Grid.RowDefinitions%2A>a la , para un total de cuatro filas:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. Mueva los controles a la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> segunda columna estableciendo la propiedad en 1 en cada uno de los tres controles (Border, ListBox y Button).

4. Mueva cada control hacia abajo <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> una fila incrementando su valor en 1 para cada uno de los tres controles (Border, ListBox y Button) y para el Border elemento.

   El XAML para los tres controles ahora tiene el siguiente aspecto:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Establezca <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> la propiedad en el archivo de imagen *watermark.png,* agregando el siguiente XAML en cualquier lugar entre las `<Grid>` etiquetas y: `</Grid>`

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Antes <xref:System.Windows.Controls.Border> del elemento, <xref:System.Windows.Controls.Label> agregue a con el contenido "Ver informe de gastos". Esta etiqueta es el título de la página.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Compile y ejecute la aplicación.

La siguiente ilustración muestra los resultados de lo que acaba de agregar:

![Captura de pantalla de ejemplo de ExpenseIt que muestra el nuevo fondo de la imagen y el título de la página](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Agregar código para controlar eventos

1. En *`ExpenseItHome.xaml`*, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> agregue un <xref:System.Windows.Controls.Button> controlador de eventos al elemento. Para obtener más información, vea [Cómo: crear un controlador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))de eventos simple .

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Abrir *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .

3. Agregue el código `ExpenseItHome` siguiente a la clase para agregar un controlador de eventos de clic de botón. El controlador de eventos abre el **ExpenseReportPage** página.

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Cree la interfaz de usuario para ExpenseReportPage

*ExpenseReportPage.xaml* muestra el informe de gastos de **`ExpenseItHome`** la persona seleccionada en la página. En esta sección, creará la interfaz de usuario para **ExpenseReportPage**. También agregará colores de fondo y relleno a los distintos elementos de la interfaz de usuario.

1. Abra *ExpenseReportPage.xaml*.

2. Agregue el siguiente <xref:System.Windows.Controls.Grid> XAML entre las etiquetas:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Esta interfaz *`ExpenseItHome.xaml`* de usuario es similar a <xref:System.Windows.Controls.DataGrid>, excepto que los datos del informe se muestran en un archivo .

3. Compile y ejecute la aplicación.

4. Seleccione el botón **Ver.**

    Se mostrará la página de informe de gastos Observe también que el botón de navegación hacia atrás está habilitado.

En la ilustración siguiente se muestran los elementos de interfaz de usuario agregados a *ExpenseReportPage.xaml*.

![ExpenseIt captura de pantalla de ejemplo que muestra la interfaz de usuario que acaba de crear para el ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Controles de estilo

La apariencia de varios elementos suele ser la misma para todos los elementos del mismo tipo en una interfaz de usuario. La interfaz de usuario usa [estilos](../controls/styling-and-templating.md) para que las apariencias sean reutilizables en varios elementos. La reutilización de estilos ayuda a simplificar la creación y administración de XAML. En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.

1. Abra *Application.xaml* o *App.xaml*.

2. Agregue el siguiente <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> XAML entre las etiquetas:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Este código XAML agrega los estilos siguientes:

    - `headerTextStyle`: para dar formato al título de la página <xref:System.Windows.Controls.Label>.

    - `labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> .

    - `columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: para dar formato a los controles del encabezado de lista <xref:System.Windows.Controls.Border> .

    - `listHeaderTextStyle`: Para formatear <xref:System.Windows.Controls.Label>el encabezado de lista .

    - `buttonStyle`: Para <xref:System.Windows.Controls.Button> formatear `ExpenseItHome.xaml`el archivo .

    Observe que los estilos son <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> recursos y elementos secundarios del elemento de propiedad. En esta ubicación, los estilos se aplican a todos los elementos de una aplicación. Para obtener un ejemplo del uso de recursos en una aplicación .NET, vea [Usar](../advanced/how-to-use-application-resources.md)recursos de aplicación .

3. En *`ExpenseItHome.xaml`*, reemplace <xref:System.Windows.Controls.Grid> todo entre los elementos con el siguiente XAML:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos. Por ejemplo, `headerTextStyle` se aplica al "Ver <xref:System.Windows.Controls.Label>informe de gastos".

4. Abra *ExpenseReportPage.xaml*.

5. Reemplace todo <xref:System.Windows.Controls.Grid> entre los elementos con el siguiente XAML:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Este XAML agrega estilos a los <xref:System.Windows.Controls.Label> elementos y. <xref:System.Windows.Controls.Border>

6. Compile y ejecute la aplicación. La apariencia de la ventana es la misma que anteriormente.

    ![Captura de pantalla de ejemplo ExpenseIt con la misma apariencia que en la última sección.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Cierre la aplicación para volver a Visual Studio.

## <a name="bind-data-to-a-control"></a>Enlazar datos a un control

En esta sección, creará los datos XML que están enlazados a varios controles.

1. En *`ExpenseItHome.xaml`*, después del elemento de apertura, <xref:System.Windows.Controls.Grid> agregue el siguiente XAML para crear un <xref:System.Windows.Data.XmlDataProvider> que contenga los datos de cada persona:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    Los datos se <xref:System.Windows.Controls.Grid> crean como un recurso. Normalmente, estos datos se cargan como un archivo, pero para simplificar los datos se agregan en línea.

2. Dentro `<Grid.Resources>` del elemento, `<xref:System.Windows.DataTemplate>` agregue el siguiente elemento, que <xref:System.Windows.Controls.ListBox>define cómo `<XmlDataProvider>` mostrar los datos en el , después del elemento:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Para obtener más información acerca de las plantillas de datos, consulte [Introducción](../data/data-templating-overview.md)a la creación de plantillas de datos .

3. Reemplace el <xref:System.Windows.Controls.ListBox> existente con el siguiente XAML:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Este XAML enlaza <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> la <xref:System.Windows.Controls.ListBox> propiedad del origen de datos y <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>aplica la plantilla de datos como el archivo .

## <a name="connect-data-to-controls"></a>Conectar datos a controles

A continuación, agregará código para recuperar el nombre **`ExpenseItHome`** seleccionado en la página y pasarlo al constructor de **ExpenseReportPage**. **ExpenseReportPage** establece su contexto de datos con el elemento pasado, que es a lo que se enlazan los controles definidos en *ExpenseReportPage.xaml.*

1. Abra *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.

2. Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Abrir *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .

4. Cambie <xref:System.Windows.Controls.Primitives.ButtonBase.Click> el controlador de eventos para llamar al nuevo constructor pasando los datos del informe de gastos de la persona seleccionada.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Estilo de datos con plantillas de datos

En esta sección, actualizará la interfaz de usuario para cada elemento de las listas enlazadas a datos mediante plantillas de datos.

1. Abra *ExpenseReportPage.xaml*.

2. Enlazar el contenido de los elementos <xref:System.Windows.Controls.Label> "Name" y "Department" a la propiedad de origen de datos adecuada. Para obtener más información sobre el enlace de datos, vea [Introducción al enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos .

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Después <xref:System.Windows.Controls.Grid> del elemento de apertura, agregue las siguientes plantillas de datos, que definen cómo mostrar los datos del informe de gastos:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Reemplace <xref:System.Windows.Controls.DataGridTextColumn> los <xref:System.Windows.Controls.DataGridTemplateColumn> elementos <xref:System.Windows.Controls.DataGrid> por debajo del elemento y aplíqueles las plantillas.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Compile y ejecute la aplicación.

6. Seleccione una persona y, a continuación, seleccione el botón **Ver.**

En la ilustración siguiente `ExpenseIt` se muestran ambas páginas de la aplicación con controles, diseño, estilos, enlace de datos y plantillas de datos aplicadas:

![Ambas páginas de la aplicación que muestran la lista de nombres y un informe de gastos.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> En este ejemplo se muestra una característica específica de WPFWPF y no se siguen todas las prácticas recomendadas para aspectos como la seguridad, la localización y la accesibilidad. Para obtener una cobertura completa de WPFWPF y las prácticas recomendadas de desarrollo de aplicaciones .NET, consulte los temas siguientes:
>
> - [Accesibilidad](../../ui-automation/accessibility-best-practices.md)
> - [Seguridad](../security-wpf.md)
> - [Globalización y localización de WPF](../advanced/wpf-globalization-and-localization-overview.md)
> - [Rendimiento de WPF](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido varias técnicas para crear una interfaz de usuario mediante Windows Presentation Foundation (WPF). Ahora debe tener una comprensión básica de los bloques de creación de una aplicación .NET enlazada a datos. Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:

- [Arquitectura WPF](../advanced/wpf-architecture.md)
- [Información general de XAML (WPF)](../advanced/xaml-overview-wpf.md)
- [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md)
- [Diseño](../advanced/layout.md)

Para más información sobre la creación de aplicaciones, vea los temas siguientes:

- [Desarrollo de aplicaciones](../app-development/index.md)
- [Controles](../controls/index.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Gráficos y multimedia](../graphics-multimedia/index.md)
- [Documentos en WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Consulte también

- [Visión general de los paneles](../controls/panels-overview.md)
- [Visión general de la plantillas de datos](../data/data-templating-overview.md)
- [Crear una aplicación WPF](../app-development/building-a-wpf-application-wpf.md)
- [Estilos y plantillas](../controls/styles-and-templates.md)
