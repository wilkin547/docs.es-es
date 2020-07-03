---
title: Cree su primera aplicación de WPF en Visual Studio 2019-.NET Framework
titleSuffix: ''
description: Desarrolle una aplicación de escritorio Windows Presentation Foundation (WPF) que incluya elementos comunes a la mayoría de las aplicaciones de WPF.
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
ms.openlocfilehash: c9af988bcf291325b11df4fd22827b47090c0b48
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853886"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a>Tutorial: crear su primera aplicación de WPF en Visual Studio 2019

En este artículo se muestra cómo desarrollar una aplicación de escritorio Windows Presentation Foundation (WPF) que incluya los elementos que son comunes a la mayoría de las aplicaciones de WPF: marcado de lenguaje XAML (XAML), código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos. Para desarrollar la aplicación, usará Visual Studio.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> - Cree un proyecto de WPF.
> - Use XAML para diseñar la apariencia de la interfaz de usuario (UI) de la aplicación.
> - Escriba código para compilar el comportamiento de la aplicación.
> - Cree una definición de aplicación para administrar la aplicación.
> - Agregue controles y cree el diseño para crear la interfaz de usuario de la aplicación.
> - Cree estilos para un aspecto coherente en la interfaz de usuario de la aplicación.
> - Enlace la interfaz de usuario a los datos, para rellenar la interfaz de usuario a partir de los datos y para mantener sincronizados los datos y la interfaz de usuario.

Al final del tutorial, habrá creado una aplicación de Windows independiente que permite a los usuarios ver informes de gastos para personas seleccionadas. La aplicación se compone de varias páginas de WPF que se hospedan en una ventana de estilo de explorador.

> [!TIP]
> El código de ejemplo que se usa en este tutorial está disponible para Visual Basic y C# en el [tutorial ejemplo de aplicación WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).
>
> Puede alternar el lenguaje de código del código de ejemplo entre C# y Visual Basic mediante el selector de idioma situado en la parte superior de esta página.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo de **desarrollo de escritorio de .net** instalada.

   Para obtener más información sobre cómo instalar la versión más reciente de Visual Studio, vea [instalar Visual Studio](/visualstudio/install/install-visual-studio).

## <a name="create-the-application-project"></a>Crear el proyecto de aplicación

El primer paso es crear la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen.

1. Cree un nuevo proyecto de aplicación de WPF en Visual Basic o Visual C# llamado **`ExpenseIt`** :

   1. Abra Visual Studio y seleccione **crear un nuevo proyecto** **en el menú introducción.**

      Se abre el cuadro de diálogo **crear nuevo proyecto** .

   2. En la lista desplegable **lenguaje** , seleccione **C#** o **Visual Basic**.

   3. Seleccione la plantilla **aplicación WPF (.NET Framework)** y, después, seleccione **siguiente**.

      ![Cuadro de diálogo Crear un proyecto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      Se abre el cuadro de diálogo **configurar el nuevo proyecto** .

   4. Escriba el nombre del proyecto **`ExpenseIt`** y, a continuación, seleccione **crear**.

      ![Cuadro de diálogo Configurar un nuevo proyecto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      Visual Studio crea el proyecto y abre el diseñador de la ventana de la aplicación predeterminada denominada **MainWindow. Xaml**.

2. Abra *Application. Xaml* (Visual Basic) o *app. Xaml* (C#).

    Este archivo XAML define una aplicación WPF y los recursos de la aplicación. También se usa este archivo para especificar la interfaz de usuario, en este caso *MainWindow. Xaml*, que se muestra automáticamente cuando se inicia la aplicación.

    El código XAML debe tener un aspecto similar al siguiente en Visual Basic:

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    Y similar al siguiente en C#:

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. Abra *MainWindow. Xaml*.

    Este archivo XAML es la ventana principal de la aplicación y muestra el contenido creado en las páginas. La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono, y controla los eventos, como cerrar u ocultar.

4. Cambie el <xref:System.Windows.Window> elemento a <xref:System.Windows.Navigation.NavigationWindow> , como se muestra en el código XAML siguiente:

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   Esta aplicación navega a contenido diferente en función de los datos proporcionados por el usuario. Este es el motivo por el que el principal <xref:System.Windows.Window> debe cambiarse a <xref:System.Windows.Navigation.NavigationWindow> . <xref:System.Windows.Navigation.NavigationWindow>hereda todas las propiedades de <xref:System.Windows.Window> . El <xref:System.Windows.Navigation.NavigationWindow> elemento del archivo XAML crea una instancia de la <xref:System.Windows.Navigation.NavigationWindow> clase. Para obtener más información, vea [información general sobre navegación](../app-development/navigation-overview.md).

5. Quite los <xref:System.Windows.Controls.Grid> elementos de entre las <xref:System.Windows.Navigation.NavigationWindow> etiquetas.

6. Cambie las siguientes propiedades en el código XAML para el <xref:System.Windows.Navigation.NavigationWindow> elemento:

    - Establezca la <xref:System.Windows.Window.Title%2A> propiedad en " `ExpenseIt` ".

    - Establezca la <xref:System.Windows.FrameworkElement.Height%2A> propiedad en 350 píxeles.

    - Establezca la <xref:System.Windows.FrameworkElement.Width%2A> propiedad en 500 píxeles.

    El código XAML debe tener un aspecto similar al siguiente para Visual Basic:

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    Y similar a lo siguiente para C#:

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. Abra *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS*.

    Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en *MainWindow. Xaml*. Este archivo contiene una clase parcial para la ventana definida en código XAML.

8. Si usa C#, cambie la `MainWindow` clase para que se derive de <xref:System.Windows.Navigation.NavigationWindow> . (En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en XAML). El código de C# debería tener ahora el siguiente aspecto:

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a>Agregar archivos a la aplicación

En esta sección, agregará dos páginas y una imagen a la aplicación.

1. Agregue una nueva página al proyecto y asígnele el nombre *`ExpenseItHome.xaml`* :

   1. En **Explorador de soluciones**, haga clic con el botón secundario en el **`ExpenseIt`** nodo del proyecto y elija **Agregar**  >  **Página**.

   1. En el cuadro de diálogo **Agregar nuevo elemento** , la plantilla **página (WPF)** ya está seleccionada. Escriba el nombre **`ExpenseItHome`** y, a continuación, seleccione **Agregar**.

    Esta página es la primera página que se muestra cuando se inicia la aplicación. Se mostrará una lista de personas de las que seleccionar, para mostrar un informe de gastos.

1. Abra *`ExpenseItHome.xaml`* .

1. Establezca <xref:System.Windows.Controls.Page.Title%2A> en " `ExpenseIt - Home` ".

1. Establezca el `DesignHeight` en 350 píxeles y el `DesignWidth` en 500 píxeles.

    El XAML aparece ahora como se indica a continuación para Visual Basic:

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    Y similar a lo siguiente para C#:

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. Abra *MainWindow. Xaml*.

1. Agregue una <xref:System.Windows.Navigation.NavigationWindow.Source%2A> propiedad al <xref:System.Windows.Navigation.NavigationWindow> elemento y establézcala en " `ExpenseItHome.xaml` ".

    Esto establece *`ExpenseItHome.xaml`* como la primera página que se abre cuando se inicia la aplicación.

    XAML de ejemplo en Visual Basic:

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    Y en C#:

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > También puede establecer la propiedad **origen** en la categoría **varios** de la ventana **propiedades** .
   >
   > ![Propiedad de origen en ventana Propiedades](./media/properties-source.png)

1. Agregue otra página de WPF nueva al proyecto y asígnele el nombre *ExpenseReportPage. Xaml*::

   1. En **Explorador de soluciones**, haga clic con el botón secundario en el **`ExpenseIt`** nodo del proyecto y elija **Agregar**  >  **Página**.

   1. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla **página (WPF)** . Escriba el nombre **ExpenseReportPage**y, a continuación, seleccione **Agregar**.

    Esta página mostrará el informe de gastos de la persona que está seleccionada en la **`ExpenseItHome`** página.

1. Abra *ExpenseReportPage. Xaml*.

1. Establezca <xref:System.Windows.Controls.Page.Title%2A> en " `ExpenseIt - View Expense` ".

1. Establezca el `DesignHeight` en 350 píxeles y el `DesignWidth` en 500 píxeles.

    *ExpenseReportPage. Xaml* tiene ahora el siguiente aspecto en Visual Basic:

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    Y similar al siguiente en C#:

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. Abra *ExpenseItHome. Xaml. VB* y *ExpenseReportPage. Xaml. VB*o *ExpenseItHome.Xaml.CS* y *ExpenseReportPage.Xaml.CS*.

    Cuando se crea un nuevo archivo de paginación, Visual Studio crea automáticamente el archivo *de código subyacente* . Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.

    El código debe tener un aspecto similar al siguiente para **`ExpenseItHome`** :

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    Y similar a lo siguiente para **ExpenseReportPage**:

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. Agregue una imagen denominada *watermark.png* al proyecto. Puede crear su propia imagen, copiar el archivo del código de ejemplo u obtenerlo del repositorio de github [Microsoft/WPF-samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .

    1. Haga clic con el botón secundario en el nodo del proyecto y seleccione **Agregar**  >  **elemento existente**o presione **MAYÚS** + **Alt** + **A**.

    2. En el cuadro de diálogo **Agregar elemento existente** , establezca el filtro de archivos en **todos los archivos** o **archivos de imagen**, busque el archivo de imagen que desea usar y, después, seleccione **Agregar**.

## <a name="build-and-run-the-application"></a>Compilación y ejecución de la aplicación

1. Para compilar y ejecutar la aplicación, presione **F5** o seleccione **iniciar depuración** en el menú **depurar** .

    En la ilustración siguiente se muestra la aplicación con los <xref:System.Windows.Navigation.NavigationWindow> botones:

    ![Aplicación después de compilarla y ejecutarla.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. Cierre la aplicación para volver a Visual Studio.

## <a name="create-the-layout"></a>Crear el diseño

El diseño proporciona una manera ordenada de colocar los elementos de la interfaz de usuario y también administra el tamaño y la posición de dichos elementos cuando se cambia el tamaño de una interfaz de usuario. Normalmente, se crea un diseño con uno de los controles de diseño siguientes:

- <xref:System.Windows.Controls.Canvas>: Define un área en la que se pueden colocar explícitamente los elementos secundarios usando coordenadas relativas al área de lienzo.
- <xref:System.Windows.Controls.DockPanel>: Define un área en la que puede organizar los elementos secundarios de forma horizontal o vertical, en relación unos con otros.
- <xref:System.Windows.Controls.Grid>: Define un área de cuadrícula flexible que consta de columnas y filas.
- <xref:System.Windows.Controls.StackPanel>: Organiza los elementos secundarios en una sola línea que se puede orientar horizontal o verticalmente.
- <xref:System.Windows.Controls.VirtualizingStackPanel>: Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.
- <xref:System.Windows.Controls.WrapPanel>: Coloca los elementos secundarios en una posición secuencial de izquierda a derecha, dividiendo el contenido en la línea siguiente en el borde del cuadro contenedor. La ordenación subsiguiente se realiza secuencialmente de arriba abajo o de derecha a izquierda, en función del valor de la propiedad Orientation.

Cada uno de estos controles de diseño admite un tipo determinado de diseño para sus elementos secundarios. `ExpenseIt`se puede cambiar el tamaño de las páginas y cada página tiene elementos que se organizan horizontal y verticalmente junto con otros elementos. En este ejemplo, <xref:System.Windows.Controls.Grid> se usa como elemento de diseño para la aplicación.

> [!TIP]
> Para obtener más información sobre <xref:System.Windows.Controls.Panel> los elementos, consulte [información general](../controls/panels-overview.md)de los paneles. Para obtener más información sobre el diseño, vea [diseño](../advanced/layout.md).

En esta sección, creará una tabla de una sola columna con tres filas y un margen de 10 píxeles agregando definiciones de columna y fila a <xref:System.Windows.Controls.Grid> en *`ExpenseItHome.xaml`* .

1. En *`ExpenseItHome.xaml`* , establezca la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad del <xref:System.Windows.Controls.Grid> elemento en "10, 0, 10, 10", que corresponde a los márgenes izquierdo, superior, derecho e inferior:

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > También puede establecer los valores de **margen** en la ventana **propiedades** , en la categoría **diseño** :
   >
   > ![Valores de margen en ventana Propiedades](./media/properties-margin.png)

2. Agregue el código XAML siguiente entre las <xref:System.Windows.Controls.Grid> etiquetas para crear las definiciones de fila y columna:

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    La <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas se establece en <xref:System.Windows.GridLength.Auto%2A> , lo que significa que el tamaño de las filas se basa en el contenido de las filas. El valor predeterminado <xref:System.Windows.Controls.RowDefinition.Height%2A> es <xref:System.Windows.GridUnitType.Star> sizing, lo que significa que el alto de fila es una proporción ponderada del espacio disponible. Por ejemplo, si dos filas tienen cada una <xref:System.Windows.Controls.RowDefinition.Height%2A> de "*", cada una tiene un alto que es la mitad del espacio disponible.

    <xref:System.Windows.Controls.Grid>Ahora debe contener el siguiente código XAML:

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a>Agregar controles

En esta sección, actualizará la interfaz de usuario de la Página principal para mostrar una lista de personas, donde puede seleccionar una persona para mostrar el informe de gastos. Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación. Para obtener más información, consulte [Controles](../controls/index.md).

Para crear esta interfaz de usuario, agregará los siguientes elementos a *`ExpenseItHome.xaml`* :

- Un <xref:System.Windows.Controls.ListBox> (para la lista de personas).
- Un <xref:System.Windows.Controls.Label> (para el encabezado de lista).
- Un <xref:System.Windows.Controls.Button> (para ver el informe de gastos de la persona que está seleccionada en la lista).

Cada control se coloca en una fila de estableciendo <xref:System.Windows.Controls.Grid> la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> propiedad adjunta. Para obtener más información sobre las propiedades adjuntas, vea [información general sobre las propiedades adjuntas](../advanced/attached-properties-overview.md).

1. En *`ExpenseItHome.xaml`* , agregue el código XAML siguiente en algún lugar entre las <xref:System.Windows.Controls.Grid> Etiquetas:

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > También puede crear los controles arrastrándolos desde la ventana cuadro de **herramientas** hasta la ventana de diseño y, a continuación, estableciendo sus propiedades en la ventana **propiedades** .

2. Compile y ejecute la aplicación.

    En la ilustración siguiente se muestran los controles que ha creado:

![Captura de pantalla de ejemplo ExpenseIt en la que se muestra una lista de nombres](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a>Agregar una imagen y un título

En esta sección, actualizará la interfaz de usuario de la Página principal con una imagen y un título de página.

1. En *`ExpenseItHome.xaml`* , agregue otra columna a <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un fijo <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de 230 píxeles:

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. Agregue otra fila al <xref:System.Windows.Controls.Grid.RowDefinitions%2A> , para un total de cuatro filas:

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. Mueva los controles a la segunda columna estableciendo la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad en 1 en cada uno de los tres controles (borde, cuadro de lista y botón).

4. Baje cada control una fila aumentando su <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valor en 1 para cada uno de los tres controles (borde, cuadro de lista y botón) y para el elemento Border.

   El código XAML de los tres controles tiene ahora el siguiente aspecto:

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. Establezca la <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> propiedad en el archivo de imagen *watermark.png* agregando el código XAML siguiente en cualquier lugar entre las `<Grid>` `</Grid>` etiquetas y:

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. Antes del <xref:System.Windows.Controls.Border> elemento, agregue <xref:System.Windows.Controls.Label> con el contenido "ver informe de gastos". Esta etiqueta es el título de la página.

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. Compile y ejecute la aplicación.

En la ilustración siguiente se muestran los resultados de lo que acaba de agregar:

![Captura de pantalla de ejemplo ExpenseIt que muestra el nuevo fondo de imagen y el título de la página](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a>Agregar código para controlar eventos

1. En *`ExpenseItHome.xaml`* , agregue un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos al <xref:System.Windows.Controls.Button> elemento. Para obtener más información, vea [Cómo: crear un controlador de eventos simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .

3. Agregue el código siguiente a la `ExpenseItHome` clase para agregar un controlador de eventos de clic de botón. El controlador de eventos abre la página **ExpenseReportPage** .

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a>Crear la interfaz de usuario para ExpenseReportPage

*ExpenseReportPage. Xaml* muestra el informe de gastos de la persona que está seleccionada en la **`ExpenseItHome`** página. En esta sección, creará la interfaz de usuario para **ExpenseReportPage**. También agregará colores de fondo y relleno a los distintos elementos de la interfaz de usuario.

1. Abra *ExpenseReportPage. Xaml*.

2. Agregue el código XAML siguiente entre las <xref:System.Windows.Controls.Grid> Etiquetas:

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    Esta interfaz de usuario es similar a *`ExpenseItHome.xaml`* , excepto en que los datos del informe se muestran en un <xref:System.Windows.Controls.DataGrid> .

3. Compile y ejecute la aplicación.

4. Seleccione el botón **Ver** .

    Se mostrará la página de informe de gastos Observe también que el botón de navegación hacia atrás está habilitado.

En la ilustración siguiente se muestran los elementos de la interfaz de usuario agregados a *ExpenseReportPage. Xaml*.

![Captura de pantalla de ejemplo ExpenseIt que muestra la interfaz de usuario que se acaba de crear para el ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a>Controles de estilo

La apariencia de varios elementos suele ser la misma para todos los elementos del mismo tipo en una interfaz de usuario. La interfaz de usuario usa [estilos](../../../desktop-wpf/fundamentals/styles-templates-overview.md) para que los aspectos se puedan volver a usar en varios elementos. La reutilización de los estilos ayuda a simplificar la creación y administración de XAML. En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.

1. Abra *Application. Xaml* o *app. Xaml*.

2. Agregue el código XAML siguiente entre las <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Etiquetas:

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    Este código XAML agrega los estilos siguientes:

    - `headerTextStyle`: para dar formato al título de la página <xref:System.Windows.Controls.Label>.

    - `labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> .

    - `columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.

    - `listHeaderStyle`: para dar formato a los controles del encabezado de lista <xref:System.Windows.Controls.Border> .

    - `listHeaderTextStyle`: Para dar formato al encabezado de la lista <xref:System.Windows.Controls.Label> .

    - `buttonStyle`: Para dar formato <xref:System.Windows.Controls.Button> al `ExpenseItHome.xaml` .

    Observe que los estilos son recursos y secundarios del <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento de propiedad. En esta ubicación, los estilos se aplican a todos los elementos de una aplicación. Para obtener un ejemplo del uso de recursos en una aplicación .NET, consulte [usar recursos de aplicación](../advanced/how-to-use-application-resources.md).

3. En *`ExpenseItHome.xaml`* , reemplace todo lo que haya entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente:

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos. Por ejemplo, `headerTextStyle` se aplica a "ver informe de gastos" <xref:System.Windows.Controls.Label> .

4. Abra *ExpenseReportPage. Xaml*.

5. Reemplace todo lo que haya entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente:

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    Este código XAML agrega estilos a <xref:System.Windows.Controls.Label> los <xref:System.Windows.Controls.Border> elementos y.

6. Compile y ejecute la aplicación. La apariencia de la ventana es la misma que antes.

    ![Captura de pantalla de ejemplo ExpenseIt con el mismo aspecto que en la última sección.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. Cierre la aplicación para volver a Visual Studio.

## <a name="bind-data-to-a-control"></a>Enlazar datos a un control

En esta sección, creará los datos XML que se enlazan a varios controles.

1. En *`ExpenseItHome.xaml`* , después del elemento de apertura <xref:System.Windows.Controls.Grid> , agregue el código XAML siguiente para crear un <xref:System.Windows.Data.XmlDataProvider> que contenga los datos de cada persona:

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    Los datos se crean como un <xref:System.Windows.Controls.Grid> recurso. Normalmente, estos datos se cargan como un archivo, pero para simplificar, los datos se agregan en línea.

2. Dentro del `<Grid.Resources>` elemento, agregue el siguiente `<xref:System.Windows.DataTemplate>` elemento, que define cómo mostrar los datos en <xref:System.Windows.Controls.ListBox> , después del `<XmlDataProvider>` elemento:

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    Para obtener más información acerca de las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).

3. Reemplace el existente <xref:System.Windows.Controls.ListBox> por el código XAML siguiente:

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    Este código XAML enlaza la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de <xref:System.Windows.Controls.ListBox> al origen de datos y aplica la plantilla de datos como <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> .

## <a name="connect-data-to-controls"></a>Conectar datos a controles

A continuación, agregará código para recuperar el nombre seleccionado en la **`ExpenseItHome`** página y pasarlo al constructor de **ExpenseReportPage**. **ExpenseReportPage** establece su contexto de datos con el elemento pasado, que es de lo que se enlazan los controles definidos en *ExpenseReportPage. Xaml* .

1. Abra *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.

2. Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .

4. Cambie el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para llamar al nuevo constructor pasando los datos del informe de gastos de la persona seleccionada.

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a>Estilo de datos con plantillas de datos

En esta sección, actualizará la interfaz de usuario para cada elemento de las listas enlazadas a datos mediante plantillas de datos.

1. Abra *ExpenseReportPage. Xaml*.

2. Enlace el contenido de los elementos "Name" y "Department" <xref:System.Windows.Controls.Label> a la propiedad de origen de datos adecuada. Para obtener más información sobre el enlace de datos, vea [información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos.

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. Después del elemento de apertura <xref:System.Windows.Controls.Grid> , agregue las siguientes plantillas de datos, que definen cómo mostrar los datos del informe de gastos:

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. Reemplace los <xref:System.Windows.Controls.DataGridTextColumn> elementos por <xref:System.Windows.Controls.DataGridTemplateColumn> debajo del <xref:System.Windows.Controls.DataGrid> elemento y aplíqueles las plantillas.

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. Compile y ejecute la aplicación.

6. Seleccione una persona y, a continuación, seleccione el botón **Ver** .

En la ilustración siguiente se muestran las dos páginas de la `ExpenseIt` aplicación con los controles, el diseño, los estilos, el enlace de datos y las plantillas de datos aplicados:

![Ambas páginas de la aplicación muestran la lista de nombres y un informe de gastos.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> Este ejemplo muestra una característica específica de WPF y no sigue todos los procedimientos recomendados para cosas como seguridad, localización y accesibilidad. Para obtener una completa cobertura de WPF y los procedimientos recomendados de desarrollo de aplicaciones .NET, vea los temas siguientes:
>
> - [Accesibilidad](../../ui-automation/accessibility-best-practices.md)
> - [Seguridad](../security-wpf.md)
> - [Globalización y localización de WPF](../advanced/wpf-globalization-and-localization-overview.md)
> - [Rendimiento de WPF](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido varias técnicas para crear una interfaz de usuario mediante Windows Presentation Foundation (WPF). Ahora debería tener un conocimiento básico de los bloques de creación de una aplicación .NET enlazada a datos. Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:

- [Arquitectura de WPF](../advanced/wpf-architecture.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Introducción a las propiedades de dependencia](../advanced/dependency-properties-overview.md)
- [Diseño](../advanced/layout.md)

Para más información sobre la creación de aplicaciones, vea los temas siguientes:

- [Desarrollo de aplicaciones](../app-development/index.md)
- [Controles](../controls/index.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Gráficos y multimedia](../graphics-multimedia/index.md)
- [Documentos en WPF](../advanced/documents-in-wpf.md)

## <a name="see-also"></a>Vea también

- [Información general sobre paneles](../controls/panels-overview.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)
- [Compilar una aplicación WPF](../app-development/building-a-wpf-application-wpf.md)
- [Estilos y plantillas](../controls/styles-and-templates.md)
