---
title: Introducción a WPF
titleSuffix: ''
description: Cree experiencias de usuario visualmente impresionantes en Windows. Descubra las capacidades clave y los conceptos de Windows Presentation Foundation (WPF).
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7a79174f5f3aebe90190db45566b37bd5e9fbe3f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853575"
---
# <a name="wpf-overview"></a><span data-ttu-id="cfedf-104">Información general sobre WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-104">WPF overview</span></span>

<span data-ttu-id="cfedf-105">Windows Presentation Foundation (WPF) le permite crear aplicaciones de cliente de escritorio para Windows con experiencias de usuario visualmente impactantes.</span><span class="sxs-lookup"><span data-stu-id="cfedf-105">Windows Presentation Foundation (WPF) lets you create desktop client applications for Windows with visually stunning user experiences.</span></span>

![Ejemplo Contoso Healthcare UI](media/introduction-to-wpf/wpfintrofigure24.png)

<span data-ttu-id="cfedf-107">El núcleo de WPF es un motor de representación basado en vectores e independiente de la resolución que está diseñado para sacar partido al moderno hardware gráfico.</span><span class="sxs-lookup"><span data-stu-id="cfedf-107">The core of WPF is a resolution-independent and vector-based rendering engine that is built to take advantage of modern graphics hardware.</span></span> <span data-ttu-id="cfedf-108">WPF amplía el núcleo con un conjunto completo de características de desarrollo de aplicaciones que incluyen Extensible Application Markup Language (XAML), controles, enlace de datos, diseño, gráficos en 2D y 3D, animación, estilos, plantillas, documentos, elementos multimedia, texto y tipografía.</span><span class="sxs-lookup"><span data-stu-id="cfedf-108">WPF extends the core with a comprehensive set of application-development features that include Extensible Application Markup Language (XAML), controls, data binding, layout, 2D and 3D graphics, animation, styles, templates, documents, media, text, and typography.</span></span> <span data-ttu-id="cfedf-109">WPF es parte de. NET, así que permite compilar aplicaciones que incorporan otros elementos de la API de .NET.</span><span class="sxs-lookup"><span data-stu-id="cfedf-109">WPF is part of .NET, so you can build applications that incorporate other elements of the .NET API.</span></span>

<span data-ttu-id="cfedf-110">Esta introducción está dirigida a personas que aún no conocen WPF, y en ella se abordan sus conceptos y capacidades principales.</span><span class="sxs-lookup"><span data-stu-id="cfedf-110">This overview is intended for newcomers and covers the key capabilities and concepts of WPF.</span></span>

## <a name="program-with-wpf"></a><span data-ttu-id="cfedf-111">Programar con WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-111">Program with WPF</span></span>

<span data-ttu-id="cfedf-112">WPF existe como un subconjunto de tipos de .NET que, en su mayoría, están ubicados en el espacio de nombres <xref:System.Windows>.</span><span class="sxs-lookup"><span data-stu-id="cfedf-112">WPF exists as a subset of .NET types that are (for the most part) located in the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="cfedf-113">Si ha compilado previamente aplicaciones con .NET mediante tecnologías administradas como ASP.NET y Windows Forms, la experiencia de programación fundamental en WPF debe resultarle familiar; cree instancias de clases, defina propiedades, llame a métodos y controle eventos con el lenguaje de programación de .NET que prefiera, como C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cfedf-113">If you have previously built applications with .NET using managed technologies like ASP.NET and Windows Forms, the fundamental WPF programming experience should be familiar; you instantiate classes, set properties, call methods, and handle events, using your favorite .NET programming language, such as C# or Visual Basic.</span></span>

<span data-ttu-id="cfedf-114">WPF incluye construcciones de programación adicionales que mejoran las propiedades y los eventos: las [propiedades de dependencia](advanced/dependency-properties-overview.md) y los [eventos enrutados](advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-114">WPF includes additional programming constructs that enhance properties and events: [dependency properties](advanced/dependency-properties-overview.md) and [routed events](advanced/routed-events-overview.md).</span></span>

## <a name="markup-and-code-behind"></a><span data-ttu-id="cfedf-115">Marcado y código subyacente</span><span class="sxs-lookup"><span data-stu-id="cfedf-115">Markup and code-behind</span></span>

<span data-ttu-id="cfedf-116">WPF permite desarrollar una aplicación que use tanto *marcado* como *código subyacente*, una experiencia que les resultará familiar a los desarrolladores de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cfedf-116">WPF lets you develop an application using both *markup* and *code-behind*, an experience with which ASP.NET developers should be familiar.</span></span> <span data-ttu-id="cfedf-117">En general, se usa marcado XAML para implementar la apariencia de una aplicación y lenguajes de programación administrados (código subyacente) para implementar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cfedf-117">You generally use XAML markup to implement the appearance of an application while using managed programming languages (code-behind) to implement its behavior.</span></span> <span data-ttu-id="cfedf-118">Esta separación entre la apariencia y el comportamiento tiene las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cfedf-118">This separation of appearance and behavior has the following benefits:</span></span>

- <span data-ttu-id="cfedf-119">Se reducen los costes de desarrollo y mantenimiento porque el marcado específico de la apariencia no está asociado estrechamente al código específico del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cfedf-119">Development and maintenance costs are reduced because appearance-specific markup is not tightly coupled with behavior-specific code.</span></span>

- <span data-ttu-id="cfedf-120">La programación es más eficaz porque los diseñadores pueden implementar la apariencia de una aplicación al mismo tiempo que los programadores implementan su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cfedf-120">Development is more efficient because designers can implement an application's appearance simultaneously with developers who are implementing the application's behavior.</span></span>

- <span data-ttu-id="cfedf-121">La[globalización y localización](advanced/wpf-globalization-and-localization-overview.md) de las aplicaciones WPF se ha simplificado.</span><span class="sxs-lookup"><span data-stu-id="cfedf-121">[Globalization and localization](advanced/wpf-globalization-and-localization-overview.md) for WPF applications is simplified.</span></span>

### <a name="markup"></a><span data-ttu-id="cfedf-122">marcado</span><span class="sxs-lookup"><span data-stu-id="cfedf-122">Markup</span></span>

<span data-ttu-id="cfedf-123">XAML es un lenguaje de marcado basado en XML que se usa para implementar la apariencia de una aplicación mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="cfedf-123">XAML is an XML-based markup language that implements an application's appearance declaratively.</span></span> <span data-ttu-id="cfedf-124">Se suele usar para crear ventanas, cuadros de diálogo, páginas y controles de usuario, así como para rellenarlos con controles, formas y gráficos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-124">You typically use it to create windows, dialog boxes, pages, and user controls, and to fill them with controls, shapes, and graphics.</span></span>

<span data-ttu-id="cfedf-125">En el ejemplo siguiente se usa XAML para implementar la apariencia de una ventana que contiene un solo botón:</span><span class="sxs-lookup"><span data-stu-id="cfedf-125">The following example uses XAML to implement the appearance of a window that contains a single button:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

<span data-ttu-id="cfedf-126">En concreto, este código XAML define una ventana y un botón mediante el uso de los elementos `Window` y `Button` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cfedf-126">Specifically, this XAML defines a window and a button by using the `Window` and `Button` elements, respectively.</span></span> <span data-ttu-id="cfedf-127">Cada elemento se configura con atributos como, por ejemplo, el atributo `Window` del elemento `Title` para especificar el texto de la barra de título de la ventana.</span><span class="sxs-lookup"><span data-stu-id="cfedf-127">Each element is configured with attributes, such as the `Window` element's `Title` attribute to specify the window's title-bar text.</span></span> <span data-ttu-id="cfedf-128">En tiempo de ejecución, WPF convierte los elementos y los atributos que se definen en el marcado en instancias de clases de WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-128">At run time, WPF converts the elements and attributes that are defined in markup to instances of WPF classes.</span></span> <span data-ttu-id="cfedf-129">Por ejemplo, el elemento `Window` se convierte en una instancia de la clase <xref:System.Windows.Window> cuya propiedad <xref:System.Windows.Window.Title%2A> es el valor del atributo `Title` .</span><span class="sxs-lookup"><span data-stu-id="cfedf-129">For example, the `Window` element is converted to an instance of the <xref:System.Windows.Window> class whose <xref:System.Windows.Window.Title%2A> property is the value of the `Title` attribute.</span></span>

<span data-ttu-id="cfedf-130">En la siguiente ilustración se muestra la interfaz de usuario (UI) definida por el XAML en el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="cfedf-130">The following figure shows the user interface (UI) that is defined by the XAML in the previous example:</span></span>

![Ventana que contiene un botón](media/introduction-to-wpf/wpfintrofigure10.png)

<span data-ttu-id="cfedf-132">Dado que XAML se basa en XML, la interfaz de usuario que se crea con este lenguaje se ensambla en una jerarquía de elementos anidados, que se denomina [árbol de elementos](advanced/trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-132">Since XAML is XML-based, the UI that you compose with it is assembled in a hierarchy of nested elements known as an [element tree](advanced/trees-in-wpf.md).</span></span> <span data-ttu-id="cfedf-133">El árbol de elementos proporciona una manera lógica e intuitiva para crear y administrar las interfaces de usuario.</span><span class="sxs-lookup"><span data-stu-id="cfedf-133">The element tree provides a logical and intuitive way to create and manage UIs.</span></span>

### <a name="code-behind"></a><span data-ttu-id="cfedf-134">Código subyacente</span><span class="sxs-lookup"><span data-stu-id="cfedf-134">Code-behind</span></span>

<span data-ttu-id="cfedf-135">El comportamiento principal de una aplicación consiste en implementar la funcionalidad que responde a las interacciones del usuario, lo que incluye controlar los eventos (por ejemplo, hacer clic en un menú, una barra de herramientas o un botón) y llamar, en respuesta, a la lógica de negocios y al acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-135">The main behavior of an application is to implement the functionality that responds to user interactions, including handling events (for example, clicking a menu, tool bar, or button) and calling business logic and data access logic in response.</span></span> <span data-ttu-id="cfedf-136">En WPF, este comportamiento se implementa en el código que está asociado al marcado.</span><span class="sxs-lookup"><span data-stu-id="cfedf-136">In WPF, this behavior is implemented in code that is associated with markup.</span></span> <span data-ttu-id="cfedf-137">Este tipo de código se conoce como código subyacente.</span><span class="sxs-lookup"><span data-stu-id="cfedf-137">This type of code is known as code-behind.</span></span> <span data-ttu-id="cfedf-138">En el ejemplo siguiente se muestra el marcado actualizado del ejemplo anterior y el código subyacente:</span><span class="sxs-lookup"><span data-stu-id="cfedf-138">The following example shows the updated markup from the previous example and the code-behind:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.AWindow"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button" Click="button_Click">Click Me!</Button>

</Window>
```

```csharp
using System.Windows; // Window, RoutedEventArgs, MessageBox

namespace SDKSample
{
    public partial class AWindow : Window
    {
        public AWindow()
        {
            // InitializeComponent call is required to merge the UI
            // that is defined in markup with this class, including  
            // setting properties and registering event handlers
            InitializeComponent();
        }

        void button_Click(object sender, RoutedEventArgs e)
        {
            // Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!");
        }
    }
}
```

```vb
Namespace SDKSample

    Partial Public Class AWindow
        Inherits System.Windows.Window

        Public Sub New()

            ' InitializeComponent call is required to merge the UI
            ' that is defined in markup with this class, including  
            ' setting properties and registering event handlers
            InitializeComponent()

        End Sub

        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)

            ' Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!")

        End Sub

    End Class

End Namespace
```

<span data-ttu-id="cfedf-139">En este ejemplo, el código subyacente implementa una clase que deriva de la clase <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-139">In this example, the code-behind implements a class that derives from the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="cfedf-140">El atributo `x:Class` se usa para asociar el marcado a la clase de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="cfedf-140">The `x:Class` attribute is used to associate the markup with the code-behind class.</span></span> <span data-ttu-id="cfedf-141">Se llama a `InitializeComponent` desde el constructor de la clase de código subyacente para combinar la interfaz de usuario que se define en el marcado con la clase de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="cfedf-141">`InitializeComponent` is called from the code-behind class's constructor to merge the UI that is defined in markup with the code-behind class.</span></span> <span data-ttu-id="cfedf-142">( `InitializeComponent` se genera automáticamente cuando se crea la aplicación, por lo que no es necesario implementarla manualmente). La combinación de `x:Class` y `InitializeComponent` garantiza que la implementación se inicializa correctamente cada vez que se crea.</span><span class="sxs-lookup"><span data-stu-id="cfedf-142">(`InitializeComponent` is generated for you when your application is built, which is why you don't need to implement it manually.) The combination of `x:Class` and `InitializeComponent` ensure that your implementation is correctly initialized whenever it is created.</span></span> <span data-ttu-id="cfedf-143">La clase de código subyacente también implementa un controlador de eventos para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón.</span><span class="sxs-lookup"><span data-stu-id="cfedf-143">The code-behind class also implements an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span> <span data-ttu-id="cfedf-144">Cuando se hace clic en el botón, el controlador de eventos muestra un cuadro de mensaje mediante una llamada al método <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-144">When the button is clicked, the event handler shows a message box by calling the <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> method.</span></span>

<span data-ttu-id="cfedf-145">En la siguiente ilustración se muestra el resultado cuando se hace clic en el botón:</span><span class="sxs-lookup"><span data-stu-id="cfedf-145">The following figure shows the result when the button is clicked:</span></span>

![MessageBox](media/introduction-to-wpf/wpfintrofigure25.png)

## <a name="controls"></a><span data-ttu-id="cfedf-147">Controles</span><span class="sxs-lookup"><span data-stu-id="cfedf-147">Controls</span></span>

<span data-ttu-id="cfedf-148">Las experiencias de usuario proporcionadas por el modelo de aplicación son controles construidos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-148">The user experiences that are delivered by the application model are constructed controls.</span></span> <span data-ttu-id="cfedf-149">En WPF, *control* es un término genérico que se aplica a una categoría de clases de WPF que se hospedan en una ventana o una página, tienen una interfaz de usuario e implementan un comportamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="cfedf-149">In WPF, *control* is an umbrella term that applies to a category of WPF classes that are hosted in either a window or a page, have a user interface, and implement some behavior.</span></span>

<span data-ttu-id="cfedf-150">Para obtener más información, consulte [Controles](controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-150">For more information, see [Controls](controls/index.md).</span></span>

### <a name="wpf-controls-by-function"></a><span data-ttu-id="cfedf-151">Controles de WPF por función</span><span class="sxs-lookup"><span data-stu-id="cfedf-151">WPF controls by function</span></span>

<span data-ttu-id="cfedf-152">Los controles de WPF integrados se enumeran aquí:</span><span class="sxs-lookup"><span data-stu-id="cfedf-152">The built-in WPF controls are listed here:</span></span>

- <span data-ttu-id="cfedf-153">**Botones**: <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.Primitives.RepeatButton> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-153">**Buttons**: <xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.Primitives.RepeatButton>.</span></span>

- <span data-ttu-id="cfedf-154">**Presentación de datos**: <xref:System.Windows.Controls.DataGrid> , <xref:System.Windows.Controls.ListView> y <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-154">**Data Display**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, and <xref:System.Windows.Controls.TreeView>.</span></span>

- <span data-ttu-id="cfedf-155">**Visualización y selección de fecha**: <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-155">**Date Display and Selection**: <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>.</span></span>

- <span data-ttu-id="cfedf-156">**Cuadros de diálogo**: <xref:Microsoft.Win32.OpenFileDialog> , <xref:System.Windows.Controls.PrintDialog> y <xref:Microsoft.Win32.SaveFileDialog> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-156">**Dialog Boxes**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, and <xref:Microsoft.Win32.SaveFileDialog>.</span></span>

- <span data-ttu-id="cfedf-157">**Entrada de lápiz digital**: <xref:System.Windows.Controls.InkCanvas> y <xref:System.Windows.Controls.InkPresenter> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-157">**Digital Ink**: <xref:System.Windows.Controls.InkCanvas> and <xref:System.Windows.Controls.InkPresenter>.</span></span>

- <span data-ttu-id="cfedf-158">**Documentos**: <xref:System.Windows.Controls.DocumentViewer> , <xref:System.Windows.Controls.FlowDocumentPageViewer> , <xref:System.Windows.Controls.FlowDocumentReader> , <xref:System.Windows.Controls.FlowDocumentScrollViewer> y <xref:System.Windows.Controls.StickyNoteControl> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-158">**Documents**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, and <xref:System.Windows.Controls.StickyNoteControl>.</span></span>

- <span data-ttu-id="cfedf-159">**Entrada**: <xref:System.Windows.Controls.TextBox> , <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Controls.PasswordBox> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-159">**Input**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Controls.PasswordBox>.</span></span>

- <span data-ttu-id="cfedf-160">**Diseño**:,,,,,,, <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Primitives.BulletDecorator> <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridSplitter> , <xref:System.Windows.Controls.GroupBox> , <xref:System.Windows.Controls.Panel> , <xref:System.Windows.Controls.Primitives.ResizeGrip> , <xref:System.Windows.Controls.Separator> , <xref:System.Windows.Controls.Primitives.ScrollBar> , <xref:System.Windows.Controls.ScrollViewer> , <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.Primitives.Thumb> , <xref:System.Windows.Controls.Viewbox> , <xref:System.Windows.Controls.VirtualizingStackPanel> , <xref:System.Windows.Window> y <xref:System.Windows.Controls.WrapPanel> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-160">**Layout**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, and <xref:System.Windows.Controls.WrapPanel>.</span></span>

- <span data-ttu-id="cfedf-161">**Multimedia**: <xref:System.Windows.Controls.Image> , <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Controls.SoundPlayerAction> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-161">**Media**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, and <xref:System.Windows.Controls.SoundPlayerAction>.</span></span>

- <span data-ttu-id="cfedf-162">**Menús**: <xref:System.Windows.Controls.ContextMenu> , <xref:System.Windows.Controls.Menu> y <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-162">**Menus**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, and <xref:System.Windows.Controls.ToolBar>.</span></span>

- <span data-ttu-id="cfedf-163">**Navegación**: <xref:System.Windows.Controls.Frame> , <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Controls.Page> , <xref:System.Windows.Navigation.NavigationWindow> y <xref:System.Windows.Controls.TabControl> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-163">**Navigation**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, and <xref:System.Windows.Controls.TabControl>.</span></span>

- <span data-ttu-id="cfedf-164">**Selección**: <xref:System.Windows.Controls.CheckBox> , <xref:System.Windows.Controls.ComboBox> , <xref:System.Windows.Controls.ListBox> , <xref:System.Windows.Controls.RadioButton> y <xref:System.Windows.Controls.Slider> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-164">**Selection**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, and <xref:System.Windows.Controls.Slider>.</span></span>

- <span data-ttu-id="cfedf-165">**Información del usuario**: <xref:System.Windows.Controls.AccessText> , <xref:System.Windows.Controls.Label> , <xref:System.Windows.Controls.Primitives.Popup> , <xref:System.Windows.Controls.ProgressBar> , <xref:System.Windows.Controls.Primitives.StatusBar> , <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.ToolTip> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-165">**User Information**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.ToolTip>.</span></span>

## <a name="input-and-commands"></a><span data-ttu-id="cfedf-166">Entrada y comandos</span><span class="sxs-lookup"><span data-stu-id="cfedf-166">Input and commands</span></span>

<span data-ttu-id="cfedf-167">Los controles casi siempre detectan las acciones del usuario y responden a ellas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-167">Controls most often detect and respond to user input.</span></span> <span data-ttu-id="cfedf-168">El [sistema de entrada de WPF](advanced/input-overview.md) usa eventos directos y enrutados para admitir la entrada de texto, la administración del enfoque y la posición del mouse.</span><span class="sxs-lookup"><span data-stu-id="cfedf-168">The [WPF input system](advanced/input-overview.md) uses both direct and routed events to support text input, focus management, and mouse positioning.</span></span>

<span data-ttu-id="cfedf-169">Las aplicaciones a menudo tienen tener requisitos de entrada complejos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-169">Applications often have complex input requirements.</span></span> <span data-ttu-id="cfedf-170">WPF proporciona un [sistema de comandos](advanced/commanding-overview.md) que separa las acciones de entrada del usuario del código que responde a esas acciones.</span><span class="sxs-lookup"><span data-stu-id="cfedf-170">WPF provides a [command system](advanced/commanding-overview.md) that separates user-input actions from the code that responds to those actions.</span></span>

## <a name="layout"></a><span data-ttu-id="cfedf-171">Layout</span><span class="sxs-lookup"><span data-stu-id="cfedf-171">Layout</span></span>

<span data-ttu-id="cfedf-172">Al crear crear una interfaz de usuario, se organizan los controles según su ubicación y tamaño para crear un diseño.</span><span class="sxs-lookup"><span data-stu-id="cfedf-172">When you create a user interface, you arrange your controls by location and size to form a layout.</span></span> <span data-ttu-id="cfedf-173">Un requisito fundamental de cualquier diseño es adaptarse a los cambios de tamaño de la ventana y de configuración de pantalla.</span><span class="sxs-lookup"><span data-stu-id="cfedf-173">A key requirement of any layout is to adapt to changes in window size and display settings.</span></span> <span data-ttu-id="cfedf-174">En lugar de obligarle a escribir código que adapte el diseño en estas circunstancias, WPF le proporciona un sistema de diseño extensible de primera clase.</span><span class="sxs-lookup"><span data-stu-id="cfedf-174">Rather than forcing you to write the code to adapt a layout in these circumstances, WPF provides a first-class, extensible layout system for you.</span></span>

<span data-ttu-id="cfedf-175">La piedra angular del sistema de diseño es la posición relativa, que aumenta la capacidad de adaptación a los cambios en la configuración de las ventanas y la pantalla.</span><span class="sxs-lookup"><span data-stu-id="cfedf-175">The cornerstone of the layout system is relative positioning, which increases the ability to adapt to changing window and display conditions.</span></span> <span data-ttu-id="cfedf-176">Además, el sistema de diseño administra la negociación entre los controles para determinar el diseño.</span><span class="sxs-lookup"><span data-stu-id="cfedf-176">In addition, the layout system manages the negotiation between controls to determine the layout.</span></span> <span data-ttu-id="cfedf-177">La negociación es un proceso de dos pasos: en primer lugar, el control indica a su elemento primario qué ubicación y tamaño necesita; en segundo lugar, el elemento primario indica al control cuánto espacio dispone.</span><span class="sxs-lookup"><span data-stu-id="cfedf-177">The negotiation is a two-step process: first, a control tells its parent what location and size it requires; second, the parent tells the control what space it can have.</span></span>

<span data-ttu-id="cfedf-178">El sistema de diseño se expone a los controles secundarios mediante las clases base de WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-178">The layout system is exposed to child controls through base WPF classes.</span></span> <span data-ttu-id="cfedf-179">Para los diseños comunes, como las cuadrículas, el apilamiento y el acoplamiento, WPF incluye varios controles de diseño:</span><span class="sxs-lookup"><span data-stu-id="cfedf-179">For common layouts such as grids, stacking, and docking, WPF includes several layout controls:</span></span>

- <span data-ttu-id="cfedf-180"><xref:System.Windows.Controls.Canvas>: los controles secundarios proporcionan su propio diseño.</span><span class="sxs-lookup"><span data-stu-id="cfedf-180"><xref:System.Windows.Controls.Canvas>: Child controls provide their own layout.</span></span>

- <span data-ttu-id="cfedf-181"><xref:System.Windows.Controls.DockPanel>: los controles secundarios se alinean con los bordes del panel.</span><span class="sxs-lookup"><span data-stu-id="cfedf-181"><xref:System.Windows.Controls.DockPanel>: Child controls are aligned to the edges of the panel.</span></span>

- <span data-ttu-id="cfedf-182"><xref:System.Windows.Controls.Grid>: los controles secundarios se colocan por filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-182"><xref:System.Windows.Controls.Grid>: Child controls are positioned by rows and columns.</span></span>

- <span data-ttu-id="cfedf-183"><xref:System.Windows.Controls.StackPanel>: los controles secundarios se apilan vertical u horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="cfedf-183"><xref:System.Windows.Controls.StackPanel>: Child controls are stacked either vertically or horizontally.</span></span>

- <span data-ttu-id="cfedf-184"><xref:System.Windows.Controls.VirtualizingStackPanel>: los controles secundarios se virtualizan y se organizan en una sola línea en sentido horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="cfedf-184"><xref:System.Windows.Controls.VirtualizingStackPanel>: Child controls are virtualized and arranged on a single line that is either horizontally or vertically oriented.</span></span>

- <span data-ttu-id="cfedf-185"><xref:System.Windows.Controls.WrapPanel>: los controles secundarios se sitúan en orden de izquierda a derecha y se ajustan a la línea siguiente cuando hay más controles de los que caben en la línea actual.</span><span class="sxs-lookup"><span data-stu-id="cfedf-185"><xref:System.Windows.Controls.WrapPanel>: Child controls are positioned in left-to-right order and wrapped to the next line when there are more controls on the current line than space allows.</span></span>

<span data-ttu-id="cfedf-186">En el ejemplo siguiente se utiliza un <xref:System.Windows.Controls.DockPanel> para disponer de varios <xref:System.Windows.Controls.TextBox> controles:</span><span class="sxs-lookup"><span data-stu-id="cfedf-186">The following example uses a <xref:System.Windows.Controls.DockPanel> to lay out several <xref:System.Windows.Controls.TextBox> controls:</span></span>

[!code-xaml[IntroToWPFSnippets#LayoutMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_1.xaml)]

<span data-ttu-id="cfedf-187"><xref:System.Windows.Controls.DockPanel> permite que los controles secundarios <xref:System.Windows.Controls.TextBox> le indiquen cómo se deben organizar.</span><span class="sxs-lookup"><span data-stu-id="cfedf-187">The <xref:System.Windows.Controls.DockPanel> allows the child <xref:System.Windows.Controls.TextBox> controls to tell it how to arrange them.</span></span> <span data-ttu-id="cfedf-188">Para ello, <xref:System.Windows.Controls.DockPanel> implementa una propiedad adjunta `Dock` que se expone a los controles secundarios para permitir que cada uno de ellos especifique un estilo de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="cfedf-188">To do this, the <xref:System.Windows.Controls.DockPanel> implements a `Dock` attached property that is exposed to the child controls to allow each of them to specify a dock style.</span></span>

> [!NOTE]
> <span data-ttu-id="cfedf-189">Una propiedad implementada por un control principal para que la usen los controles secundarios es una construcción de WPF denominada [propiedad adjunta](advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-189">A property that's implemented by a parent control for use by child controls is a WPF construct called an [attached property](advanced/attached-properties-overview.md).</span></span>

<span data-ttu-id="cfedf-190">En la ilustración siguiente se muestra el resultado del marcado XAML en el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="cfedf-190">The following figure shows the result of the XAML markup in the preceding example:</span></span>

![Página de DockPanel](media/introduction-to-wpf/wpfintrofigure11.png)

## <a name="data-binding"></a><span data-ttu-id="cfedf-192">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="cfedf-192">Data binding</span></span>

<span data-ttu-id="cfedf-193">La mayoría de las aplicaciones se crean para proporcionar a los usuarios recursos que les permitan ver y editar datos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-193">Most applications are created to provide users with the means to view and edit data.</span></span> <span data-ttu-id="cfedf-194">Para las aplicaciones de WPF, el trabajo de almacenamiento de datos y el acceso a ellos ya se proporciona mediante tecnologías existentes, como SQL Server y ADO .NET.</span><span class="sxs-lookup"><span data-stu-id="cfedf-194">For WPF applications, the work of storing and accessing data is already provided for by technologies such as SQL Server and ADO .NET.</span></span> <span data-ttu-id="cfedf-195">Una vez que se tiene acceso a los datos y se cargan en los objetos administrados de la aplicación, comienza la tarea ardua de las aplicaciones WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-195">After the data is accessed and loaded into an application's managed objects, the hard work for WPF applications begins.</span></span> <span data-ttu-id="cfedf-196">En esencia, esto implica dos cosas:</span><span class="sxs-lookup"><span data-stu-id="cfedf-196">Essentially, this involves two things:</span></span>

1. <span data-ttu-id="cfedf-197">Copiar los datos de los objetos administrados a los controles, donde los datos se pueden mostrar y editar.</span><span class="sxs-lookup"><span data-stu-id="cfedf-197">Copying the data from the managed objects into controls, where the data can be displayed and edited.</span></span>

2. <span data-ttu-id="cfedf-198">Asegurarse de que los cambios realizados en los datos mediante los controles se vuelvan a copiar a los objetos administrados.</span><span class="sxs-lookup"><span data-stu-id="cfedf-198">Ensuring that changes made to data by using controls are copied back to the managed objects.</span></span>

<span data-ttu-id="cfedf-199">Para simplificar el desarrollo de aplicaciones, WPF ofrece un motor de enlace de datos que sigue estos pasos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="cfedf-199">To simplify application development, WPF provides a data binding engine to automatically perform these steps.</span></span> <span data-ttu-id="cfedf-200">La unidad que constituye el núcleo del motor de enlace de datos es la clase <xref:System.Windows.Data.Binding> , que se encarga de enlazar un control (el destino de enlace) a un objeto de datos (el origen de enlace).</span><span class="sxs-lookup"><span data-stu-id="cfedf-200">The core unit of the data binding engine is the <xref:System.Windows.Data.Binding> class, whose job is to bind a control (the binding target) to a data object (the binding source).</span></span> <span data-ttu-id="cfedf-201">Esta relación se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfedf-201">This relationship is illustrated by the following figure:</span></span>

![Diagrama de enlace de datos básico](media/introduction-to-wpf/databindingmostbasic.png)

<span data-ttu-id="cfedf-203">En el ejemplo siguiente, se muestra cómo enlazar un control <xref:System.Windows.Controls.TextBox> a una instancia de un objeto `Person` personalizado.</span><span class="sxs-lookup"><span data-stu-id="cfedf-203">The next example demonstrates how to bind a <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object.</span></span> <span data-ttu-id="cfedf-204">La implementación de `Person` se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfedf-204">The `Person` implementation is shown in the following code:</span></span>

[!code-vb[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_2.vb)]
[!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_2.cs)]

<span data-ttu-id="cfedf-205">El marcado siguiente enlaza <xref:System.Windows.Controls.TextBox> a una instancia de un `Person` objeto personalizado:</span><span class="sxs-lookup"><span data-stu-id="cfedf-205">The following markup binds the <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object:</span></span>

```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
```

[!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_6.vb)]
[!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_6.cs)]

<span data-ttu-id="cfedf-206">En este ejemplo, se crea una instancia de la clase `Person` en el código subyacente y se establece como el contexto de datos para `DataBindingWindow`.</span><span class="sxs-lookup"><span data-stu-id="cfedf-206">In this example, the `Person` class is instantiated in code-behind and is set as the data context for the `DataBindingWindow`.</span></span> <span data-ttu-id="cfedf-207">En el marcado, la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> de <xref:System.Windows.Controls.TextBox> se enlaza a la propiedad `Person.Name` (mediante la sintaxis "`{Binding ... }`" de XAML).</span><span class="sxs-lookup"><span data-stu-id="cfedf-207">In markup, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> is bound to the `Person.Name` property (using the "`{Binding ... }`" XAML syntax).</span></span> <span data-ttu-id="cfedf-208">Este código XAML indica a WPF que enlace el control <xref:System.Windows.Controls.TextBox> al objeto `Person` almacenado en la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de la ventana.</span><span class="sxs-lookup"><span data-stu-id="cfedf-208">This XAML tells WPF to bind the <xref:System.Windows.Controls.TextBox> control to the `Person` object that is stored in the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the window.</span></span>

<span data-ttu-id="cfedf-209">El motor de enlace de datos de WPF proporciona compatibilidad adicional que incluye validación, ordenación, filtrado y agrupación.</span><span class="sxs-lookup"><span data-stu-id="cfedf-209">The WPF data binding engine provides additional support that includes validation, sorting, filtering, and grouping.</span></span> <span data-ttu-id="cfedf-210">Además, el enlace de datos admite el uso de plantillas de datos para crear una interfaz de usuario personalizada para los datos enlazados cuando la interfaz de usuario mostrada por los controles estándar de WPF no es adecuada.</span><span class="sxs-lookup"><span data-stu-id="cfedf-210">Furthermore, data binding supports the use of data templates to create custom user interface for bound data when the user interface displayed by the standard WPF controls is not appropriate.</span></span>

<span data-ttu-id="cfedf-211">Para obtener más información, vea [información general sobre el enlace de datos](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-211">For more information, see [Data binding overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="graphics"></a><span data-ttu-id="cfedf-212">Gráficos</span><span class="sxs-lookup"><span data-stu-id="cfedf-212">Graphics</span></span>

<span data-ttu-id="cfedf-213">WPF incluye un conjunto extenso, escalable y flexible de características de gráficos que tienen las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="cfedf-213">WPF introduces an extensive, scalable, and flexible set of graphics features that have the following benefits:</span></span>

- <span data-ttu-id="cfedf-214">**Gráficos independientes de la resolución e independientes del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="cfedf-214">**Resolution-independent and device-independent graphics**.</span></span> <span data-ttu-id="cfedf-215">La unidad de medida básica del sistema de gráficos de WPF es el píxel independiente del dispositivo, que es 1/96 de pulgada (sea cual fuere la resolución de pantalla real), y proporciona la base para la representación independiente de la resolución y del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfedf-215">The basic unit of measurement in the WPF graphics system is the device-independent pixel, which is 1/96th of an inch, regardless of actual screen resolution, and provides the foundation for resolution-independent and device-independent rendering.</span></span> <span data-ttu-id="cfedf-216">Cada píxel independiente del dispositivo se escala automáticamente para que coincida con la configuración de puntos por pulgada (ppp) del sistema en que se representa.</span><span class="sxs-lookup"><span data-stu-id="cfedf-216">Each device-independent pixel automatically scales to match the dots-per-inch (dpi) setting of the system it renders on.</span></span>

- <span data-ttu-id="cfedf-217">**Precisión mejorada**.</span><span class="sxs-lookup"><span data-stu-id="cfedf-217">**Improved precision**.</span></span> <span data-ttu-id="cfedf-218">El sistema de coordenadas de WPF se mide con números de punto flotante de precisión doble en lugar de precisión sencilla.</span><span class="sxs-lookup"><span data-stu-id="cfedf-218">The WPF coordinate system is measured with double-precision floating-point numbers rather than single-precision.</span></span> <span data-ttu-id="cfedf-219">Las transformaciones y los valores de opacidad también se expresan como de precisión doble.</span><span class="sxs-lookup"><span data-stu-id="cfedf-219">Transformations and opacity values are also expressed as double-precision.</span></span> <span data-ttu-id="cfedf-220">WPF admite, además, una gama de color amplia (scRGB) y ofrece compatibilidad integrada para la administración de entradas de diferentes espacios de color.</span><span class="sxs-lookup"><span data-stu-id="cfedf-220">WPF also supports a wide color gamut (scRGB) and provides integrated support for managing inputs from different color spaces.</span></span>

- <span data-ttu-id="cfedf-221">**Compatibilidad con gráficos y animación avanzados**.</span><span class="sxs-lookup"><span data-stu-id="cfedf-221">**Advanced graphics and animation support**.</span></span> <span data-ttu-id="cfedf-222">WPF simplifica la programación de gráficos administrando automáticamente las escenas de animación. No tendrá que preocuparse por el procesamiento de escenas, los bucles de presentación ni la interpolación bilineal.</span><span class="sxs-lookup"><span data-stu-id="cfedf-222">WPF simplifies graphics programming by managing animation scenes for you; there is no need to worry about scene processing, rendering loops, and bilinear interpolation.</span></span> <span data-ttu-id="cfedf-223">Además, WPF admite la prueba de clics y proporciona compatibilidad plena con la composición alfa.</span><span class="sxs-lookup"><span data-stu-id="cfedf-223">Additionally, WPF provides hit-testing support and full alpha-compositing support.</span></span>

- <span data-ttu-id="cfedf-224">**Aceleración de hardware**.</span><span class="sxs-lookup"><span data-stu-id="cfedf-224">**Hardware acceleration**.</span></span> <span data-ttu-id="cfedf-225">El sistema de gráficos de WPF saca partido del hardware de gráficos para minimizar el uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="cfedf-225">The WPF graphics system takes advantage of graphics hardware to minimize CPU usage.</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="cfedf-226">Formas en 2D</span><span class="sxs-lookup"><span data-stu-id="cfedf-226">2D shapes</span></span>

<span data-ttu-id="cfedf-227">WPF proporciona una biblioteca de formas en 2D comunes dibujadas mediante vectores, como los rectángulos y las elipses que se muestran en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfedf-227">WPF provides a library of common vector-drawn 2D shapes, such as the rectangles and ellipses that are shown in the following illustration:</span></span>

![Elipses y rectángulos](media/introduction-to-wpf/wpfintrofigure4.PNG)

<span data-ttu-id="cfedf-229">Una función interesante de las formas es que no sirven únicamente para su presentación; las formas implementan muchas de las características que cabe esperar de los controles, incluida la entrada de datos desde el teclado y el mouse.</span><span class="sxs-lookup"><span data-stu-id="cfedf-229">An interesting capability of shapes is that they are not just for display; shapes implement many of the features that you expect from controls, including keyboard and mouse input.</span></span> <span data-ttu-id="cfedf-230">En el ejemplo siguiente se muestra el <xref:System.Windows.UIElement.MouseUp> evento de un <xref:System.Windows.Shapes.Ellipse> control que se está administrando:</span><span class="sxs-lookup"><span data-stu-id="cfedf-230">The following example shows the <xref:System.Windows.UIElement.MouseUp> event of an <xref:System.Windows.Shapes.Ellipse> being handled:</span></span>

[!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_7.xaml)]

[!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_8.vb)]
[!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_8.cs)]

<span data-ttu-id="cfedf-231">En la siguiente ilustración se muestra lo que genera el código anterior:</span><span class="sxs-lookup"><span data-stu-id="cfedf-231">The following figure shows what is produced by the preceding code:</span></span>

![Ventana con el texto "You clicked the ellipse&#33;" (Ha hecho clic en la elipse)](media/introduction-to-wpf/wpfintrofigure12.png)

<span data-ttu-id="cfedf-233">Para obtener más información, vea [información general sobre formas y dibujo básico en WPF](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-233">For more information, see [Shapes and basic drawing in WPF overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="cfedf-234">Geometrías en 2D</span><span class="sxs-lookup"><span data-stu-id="cfedf-234">2D geometries</span></span>

<span data-ttu-id="cfedf-235">Las formas en 2D que proporciona WPF abarcan el conjunto estándar de formas básicas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-235">The 2D shapes provided by WPF cover the standard set of basic shapes.</span></span> <span data-ttu-id="cfedf-236">Pero tal vez sea necesario crear formas personalizadas para facilitar el diseño de una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="cfedf-236">However, you may need to create custom shapes to facilitate the design of a customized user interface.</span></span> <span data-ttu-id="cfedf-237">Para ello, WPF proporciona las geometrías.</span><span class="sxs-lookup"><span data-stu-id="cfedf-237">For this purpose, WPF provides geometries.</span></span> <span data-ttu-id="cfedf-238">En la siguiente ilustración se muestra el uso de geometrías para crear una forma personalizada que se puede dibujar directamente, usar como un pincel o usar para recortar otras formas y controles.</span><span class="sxs-lookup"><span data-stu-id="cfedf-238">The following figure demonstrates the use of geometries to create a custom shape that can be drawn directly, used as a brush, or used to clip other shapes and controls.</span></span>

<span data-ttu-id="cfedf-239">Los objetos<xref:System.Windows.Shapes.Path> se pueden usar para dibujar formas cerradas o abiertas, varias formas o incluso formas curvas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-239"><xref:System.Windows.Shapes.Path> objects can be used to draw closed or open shapes, multiple shapes, and even curved shapes.</span></span>

<span data-ttu-id="cfedf-240">Los objetos <xref:System.Windows.Media.Geometry> se pueden usar para el recorte, la prueba de posicionamiento y la representación de datos de gráficos en 2D.</span><span class="sxs-lookup"><span data-stu-id="cfedf-240"><xref:System.Windows.Media.Geometry> objects can be used for clipping, hit-testing, and rendering 2D graphic data.</span></span>

![Varios usos de una ruta de acceso](media/introduction-to-wpf/wpfintrofigure5.png)

<span data-ttu-id="cfedf-242">Para obtener más información, vea [Información general sobre geometría](graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-242">For more information, see [Geometry overview](graphics-multimedia/geometry-overview.md).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="cfedf-243">Efectos en 2D</span><span class="sxs-lookup"><span data-stu-id="cfedf-243">2D effects</span></span>

<span data-ttu-id="cfedf-244">Un subconjunto de funciones en 2D de WPF incluye los efectos visuales, tales como degradados, mapas de bits, dibujos, pintar con vídeos, rotación, escala y sesgado.</span><span class="sxs-lookup"><span data-stu-id="cfedf-244">A subset of WPF 2D capabilities includes visual effects, such as gradients, bitmaps, drawings, painting with videos, rotation, scaling, and skewing.</span></span> <span data-ttu-id="cfedf-245">Todos ellos se logran con los pinceles; en la siguiente ilustración se muestran algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="cfedf-245">These are all achieved with brushes; the following figure shows some examples:</span></span>

![Ilustración de diferentes pinceles](media/introduction-to-wpf/wpfintrofigure6.png)

<span data-ttu-id="cfedf-247">Para obtener más información, vea [Información general sobre pinceles de WPF](graphics-multimedia/wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-247">For more information, see [WPF brushes overview](graphics-multimedia/wpf-brushes-overview.md).</span></span>

### <a name="3d-rendering"></a><span data-ttu-id="cfedf-248">Representación en 3D</span><span class="sxs-lookup"><span data-stu-id="cfedf-248">3D rendering</span></span>

<span data-ttu-id="cfedf-249">WPF también incluye funciones de representación 3D que se integran con gráficos 2D para permitir la creación de interfaces de usuario más interesantes e interesantes.</span><span class="sxs-lookup"><span data-stu-id="cfedf-249">WPF also includes 3D rendering capabilities that integrate with 2D graphics to allow the creation of more exciting and interesting user interfaces.</span></span> <span data-ttu-id="cfedf-250">Por ejemplo, la siguiente ilustración muestra imágenes 2D representadas en formas 3D:</span><span class="sxs-lookup"><span data-stu-id="cfedf-250">For example, the following figure shows 2D images rendered onto 3D shapes:</span></span>

![Captura de pantalla de ejemplo Visual3D](media/introduction-to-wpf/wpfintrofigure13.png)

<span data-ttu-id="cfedf-252">Para obtener más información, vea [Información general sobre gráficos 3D](graphics-multimedia/3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-252">For more information, see [3D graphics overview](graphics-multimedia/3-d-graphics-overview.md).</span></span>

## <a name="animation"></a><span data-ttu-id="cfedf-253">Animación</span><span class="sxs-lookup"><span data-stu-id="cfedf-253">Animation</span></span>

<span data-ttu-id="cfedf-254">El soporte de animación de WPF permite hacer que los controles crezcan, tiemblen, giren o se desvanezcan, crear transiciones de página interesantes y mucho más.</span><span class="sxs-lookup"><span data-stu-id="cfedf-254">WPF animation support lets you make controls grow, shake, spin, and fade, to create interesting page transitions, and more.</span></span> <span data-ttu-id="cfedf-255">Se puede animar la mayoría de las clases de WPF, incluso las clases personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-255">You can animate most WPF classes, even custom classes.</span></span> <span data-ttu-id="cfedf-256">En la siguiente ilustración se muestra una animación simple en acción:</span><span class="sxs-lookup"><span data-stu-id="cfedf-256">The following figure shows a simple animation in action:</span></span>

![Imágenes de un cubo animado](media/introduction-to-wpf/wpfintrofigure7.png)

<span data-ttu-id="cfedf-258">Para obtener más información, vea [Información general sobre animaciones](graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-258">For more information, see [Animation overview](graphics-multimedia/animation-overview.md).</span></span>

## <a name="media"></a><span data-ttu-id="cfedf-259">Multimedia</span><span class="sxs-lookup"><span data-stu-id="cfedf-259">Media</span></span>

<span data-ttu-id="cfedf-260">Una manera de mostrar contenido enriquecido es mediante el uso de medios audiovisuales (multimedia).</span><span class="sxs-lookup"><span data-stu-id="cfedf-260">One way to convey rich content is through the use of audiovisual media.</span></span> <span data-ttu-id="cfedf-261">WPF proporciona compatibilidad especial con imágenes, vídeo y audio.</span><span class="sxs-lookup"><span data-stu-id="cfedf-261">WPF provides special support for images, video, and audio.</span></span>

### <a name="images"></a><span data-ttu-id="cfedf-262">Imágenes</span><span class="sxs-lookup"><span data-stu-id="cfedf-262">Images</span></span>

<span data-ttu-id="cfedf-263">Las imágenes son comunes a la mayoría de las aplicaciones y WPF proporciona varias maneras de usarlas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-263">Images are common to most applications, and WPF provides several ways to use them.</span></span> <span data-ttu-id="cfedf-264">La siguiente ilustración muestra una interfaz de usuario con un cuadro de lista que contiene imágenes en miniatura.</span><span class="sxs-lookup"><span data-stu-id="cfedf-264">The following figure shows a user interface with a list box that contains thumbnail images.</span></span> <span data-ttu-id="cfedf-265">Cuando se selecciona una miniatura, aparece la imagen a tamaño completo.</span><span class="sxs-lookup"><span data-stu-id="cfedf-265">When a thumbnail is selected, the image is shown full-size.</span></span>

![Imágenes en miniatura e imagen a tamaño completo](media/introduction-to-wpf/wpfintrofigure8.png)

<span data-ttu-id="cfedf-267">Para obtener más información, vea [Información general sobre imágenes](graphics-multimedia/imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-267">For more information, see [Imaging overview](graphics-multimedia/imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="cfedf-268">Vídeo y audio</span><span class="sxs-lookup"><span data-stu-id="cfedf-268">Video and audio</span></span>

<span data-ttu-id="cfedf-269">El control <xref:System.Windows.Controls.MediaElement> es capaz de reproducir vídeo y audio, y es lo suficientemente flexible como para ser la base de un reproductor multimedia personalizado.</span><span class="sxs-lookup"><span data-stu-id="cfedf-269">The <xref:System.Windows.Controls.MediaElement> control is capable of playing both video and audio, and it is flexible enough to be the basis for a custom media player.</span></span> <span data-ttu-id="cfedf-270">El marcado XAML siguiente implementa un reproductor de media:</span><span class="sxs-lookup"><span data-stu-id="cfedf-270">The following XAML markup implements a media player:</span></span>

[!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_9.xaml)]

<span data-ttu-id="cfedf-271">En la ventana de la siguiente ilustración se muestra el <xref:System.Windows.Controls.MediaElement> control en acción:</span><span class="sxs-lookup"><span data-stu-id="cfedf-271">The window in the following figure shows the <xref:System.Windows.Controls.MediaElement> control in action:</span></span>

![Control MediaElement con audio y vídeo](media/introduction-to-wpf/wpfintrofigure1.png)

<span data-ttu-id="cfedf-273">Para obtener más información, vea [Gráficos y multimedia](graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-273">For more information, see [Graphics and multimedia](graphics-multimedia/index.md).</span></span>

## <a name="text-and-typography"></a><span data-ttu-id="cfedf-274">Texto y tipografía</span><span class="sxs-lookup"><span data-stu-id="cfedf-274">Text and typography</span></span>

<span data-ttu-id="cfedf-275">Para facilitar la representación de texto de alta calidad, WPF ofrece las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="cfedf-275">To facilitate high-quality text rendering, WPF offers the following features:</span></span>

- <span data-ttu-id="cfedf-276">Compatibilidad con fuentes OpenType.</span><span class="sxs-lookup"><span data-stu-id="cfedf-276">OpenType font support.</span></span>

- <span data-ttu-id="cfedf-277">Mejoras de ClearType.</span><span class="sxs-lookup"><span data-stu-id="cfedf-277">ClearType enhancements.</span></span>

- <span data-ttu-id="cfedf-278">Alto rendimiento que saca partido de la aceleración de hardware.</span><span class="sxs-lookup"><span data-stu-id="cfedf-278">High performance that takes advantage of hardware acceleration.</span></span>

- <span data-ttu-id="cfedf-279">Integración de texto con multimedia, gráficos y animación.</span><span class="sxs-lookup"><span data-stu-id="cfedf-279">Integration of text with media, graphics, and animation.</span></span>

- <span data-ttu-id="cfedf-280">Compatibilidad con fuentes internacionales y mecanismos de reserva.</span><span class="sxs-lookup"><span data-stu-id="cfedf-280">International font support and fallback mechanisms.</span></span>

<span data-ttu-id="cfedf-281">Como demostración de la integración de texto con gráficos, en la siguiente ilustración se muestra la aplicación de decoraciones de texto:</span><span class="sxs-lookup"><span data-stu-id="cfedf-281">As a demonstration of text integration with graphics, the following figure shows the application of text decorations:</span></span>

![Texto con diversas decoraciones de texto](media/introduction-to-wpf/wpfintrofigure23.png)

<span data-ttu-id="cfedf-283">Para obtener más información, consulte [Tipografía en Windows Presentation Foundation](advanced/typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-283">For more information, see [Typography in Windows Presentation Foundation](advanced/typography-in-wpf.md).</span></span>

## <a name="customize-wpf-apps"></a><span data-ttu-id="cfedf-284">Personalización de aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-284">Customize WPF apps</span></span>

<span data-ttu-id="cfedf-285">Hasta este punto, hemos estudiado los bloques de creación de WPF fundamentales para desarrollar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cfedf-285">Up to this point, you've seen the core WPF building blocks for developing applications.</span></span> <span data-ttu-id="cfedf-286">El modelo de aplicación se usa para hospedar y distribuir el contenido de las aplicaciones, que está compuesto principalmente de controles.</span><span class="sxs-lookup"><span data-stu-id="cfedf-286">You use the application model to host and deliver application content, which consists mainly of controls.</span></span> <span data-ttu-id="cfedf-287">Para simplificar la organización de los controles de una interfaz de usuario y asegurarse de que la organización se conserve aunque se modifiquen el tamaño de la ventana y la configuración de pantalla, se usa el sistema de diseño de WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-287">To simplify the arrangement of controls in a user interface, and to ensure the arrangement is maintained in the face of changes to window size and display settings, you use the WPF layout system.</span></span> <span data-ttu-id="cfedf-288">Debido a que la mayoría de las aplicaciones permiten a los usuarios interactuar con los datos, se usa el enlace de datos para reducir el trabajo de la integración de la interfaz de usuario con los datos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-288">Because most applications let users interact with data, you use data binding to reduce the work of integrating your user interface with data.</span></span> <span data-ttu-id="cfedf-289">Para mejorar la apariencia visual de la aplicación, se usa la amplia gama de gráficos, animación y multimedia compatibilidad que proporciona WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-289">To enhance the visual appearance of your application, you use the comprehensive range of graphics, animation, and media support provided by WPF.</span></span>

<span data-ttu-id="cfedf-290">Sin embargo, a menudo los conceptos básicos no bastan para crear y administrar realmente una experiencia del usuario diferenciada y visualmente impactante.</span><span class="sxs-lookup"><span data-stu-id="cfedf-290">Often, though, the basics are not enough for creating and managing a truly distinct and visually stunning user experience.</span></span> <span data-ttu-id="cfedf-291">Es posible que los controles estándar de WPF no se integren con la apariencia deseada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfedf-291">The standard WPF controls might not integrate with the desired appearance of your application.</span></span> <span data-ttu-id="cfedf-292">Es posible que los datos no se muestren del modo más eficaz.</span><span class="sxs-lookup"><span data-stu-id="cfedf-292">Data might not be displayed in the most effective way.</span></span> <span data-ttu-id="cfedf-293">La apariencia y el funcionamiento predeterminados de los temas de Windows pueden no ser adecuados para proporcionar la experiencia global del usuario con respecto a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfedf-293">Your application's overall user experience may not be suited to the default look and feel of Windows themes.</span></span> <span data-ttu-id="cfedf-294">En muchos aspectos, una tecnología de presentación requiere de extensibilidad visual tanto como cualquier otro tipo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="cfedf-294">In many ways, a presentation technology needs visual extensibility as much as any other type of extensibility.</span></span>

<span data-ttu-id="cfedf-295">Por este motivo, WPF proporciona una variedad de mecanismos para crear experiencias del usuario únicas, incluido un modelo de contenido enriquecido para los controles, desencadenadores, control y plantillas de datos, estilos, recursos de interfaz de usuario y temas y máscaras.</span><span class="sxs-lookup"><span data-stu-id="cfedf-295">For this reason, WPF provides a variety of mechanisms for creating unique user experiences, including a rich content model for controls, triggers, control and data templates, styles, user interface resources, and themes and skins.</span></span>

### <a name="content-model"></a><span data-ttu-id="cfedf-296">Modelo de contenido</span><span class="sxs-lookup"><span data-stu-id="cfedf-296">Content model</span></span>

<span data-ttu-id="cfedf-297">El propósito principal de la mayoría de los controles de WPF es mostrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="cfedf-297">The main purpose of a majority of the WPF controls is to display content.</span></span> <span data-ttu-id="cfedf-298">En WPF, el tipo y el número de elementos que pueden constituir el contenido de un control se conoce como *modelo de contenido*del control.</span><span class="sxs-lookup"><span data-stu-id="cfedf-298">In WPF, the type and number of items that can constitute the content of a control is referred to as the control's *content model*.</span></span> <span data-ttu-id="cfedf-299">Algunos controles pueden contener un solo elemento y tipo de contenido. Por ejemplo, el contenido de un control <xref:System.Windows.Controls.TextBox> es un valor de cadena que se asigna a la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-299">Some controls can contain a single item and type of content; for example, the content of a <xref:System.Windows.Controls.TextBox> is a string value that is assigned to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="cfedf-300">En el ejemplo siguiente se establece el contenido de un <xref:System.Windows.Controls.TextBox> :</span><span class="sxs-lookup"><span data-stu-id="cfedf-300">The following example sets the content of a <xref:System.Windows.Controls.TextBox>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">

    <TextBox Text="This is the content of a TextBox." />
</Window>
```

<span data-ttu-id="cfedf-301">En la ilustración siguiente se muestra el resultado:</span><span class="sxs-lookup"><span data-stu-id="cfedf-301">The following figure shows the result:</span></span>

![Control TextBox que contiene texto](media/introduction-to-wpf/wpfintrofigure21.png)

<span data-ttu-id="cfedf-303">Otros controles, sin embargo, pueden contener varios elementos de diferentes tipos de contenido. El contenido de un control <xref:System.Windows.Controls.Button>, especificado por la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A>, puede contener diversos elementos, incluidos los controles de diseño, texto, imágenes y formas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-303">Other controls, however, can contain multiple items of different types of content; the content of a <xref:System.Windows.Controls.Button>, specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property, can contain a variety of items including layout controls, text, images, and shapes.</span></span> <span data-ttu-id="cfedf-304">En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.Button> con contenido que incluye <xref:System.Windows.Controls.DockPanel> ,, <xref:System.Windows.Controls.Label> , <xref:System.Windows.Controls.Border> y <xref:System.Windows.Controls.MediaElement> :</span><span class="sxs-lookup"><span data-stu-id="cfedf-304">The following example shows a <xref:System.Windows.Controls.Button> with content that includes a <xref:System.Windows.Controls.DockPanel>, a <xref:System.Windows.Controls.Label>, a <xref:System.Windows.Controls.Border>, and a <xref:System.Windows.Controls.MediaElement>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ButtonContentWindow"
    Title="Button Content">

  <Button Margin="20">
    <!-- Button Content -->
    <DockPanel Width="200" Height="180">
      <Label DockPanel.Dock="Top" HorizontalAlignment="Center">Click Me!</Label>
      <Border Background="Black" BorderBrush="Yellow" BorderThickness="2"
        CornerRadius="2" Margin="5">
        <MediaElement Source="media/wpf.wmv" Stretch="Fill" />
      </Border>
    </DockPanel>
  </Button>
</Window>
```

<span data-ttu-id="cfedf-305">En la ilustración siguiente se muestra el contenido de este botón:</span><span class="sxs-lookup"><span data-stu-id="cfedf-305">The following figure shows the content of this button:</span></span>

![Botón que tiene varios tipos de contenido](media/introduction-to-wpf/wpfintrofigure22.png)

<span data-ttu-id="cfedf-307">Para obtener más información sobre los tipos de contenido admitidos por los diversos controles, vea [Modelo de contenido de WPF](controls/wpf-content-model.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-307">For more information on the kinds of content that is supported by various controls, see [WPF content model](controls/wpf-content-model.md).</span></span>

### <a name="triggers"></a><span data-ttu-id="cfedf-308">Desencadenadores</span><span class="sxs-lookup"><span data-stu-id="cfedf-308">Triggers</span></span>

<span data-ttu-id="cfedf-309">Aunque el propósito principal del marcado XAML es implementar la apariencia de la aplicación, también se puede usar XAML para implementar algunos aspectos del comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfedf-309">Although the main purpose of XAML markup is to implement an application's appearance, you can also use XAML to implement some aspects of an application's behavior.</span></span> <span data-ttu-id="cfedf-310">Un ejemplo es el uso de desencadenadores para cambiar la apariencia de una aplicación según las interacciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfedf-310">One example is the use of triggers to change an application's appearance based on user interactions.</span></span> <span data-ttu-id="cfedf-311">Para más información, vea [Estilos y plantillas](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-311">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="control-templates"></a><span data-ttu-id="cfedf-312">Plantillas de control</span><span class="sxs-lookup"><span data-stu-id="cfedf-312">Control templates</span></span>

<span data-ttu-id="cfedf-313">Normalmente, las interfaces de usuario predeterminadas para los controles de WPF se construyen a partir de otros controles y formas.</span><span class="sxs-lookup"><span data-stu-id="cfedf-313">The default user interfaces for WPF controls are typically constructed from other controls and shapes.</span></span> <span data-ttu-id="cfedf-314">Por ejemplo, un control <xref:System.Windows.Controls.Button> está compuesto por los controles <xref:Microsoft.Windows.Themes.ButtonChrome> y <xref:System.Windows.Controls.ContentPresenter> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-314">For example, a <xref:System.Windows.Controls.Button> is composed of both <xref:Microsoft.Windows.Themes.ButtonChrome> and <xref:System.Windows.Controls.ContentPresenter> controls.</span></span> <span data-ttu-id="cfedf-315"><xref:Microsoft.Windows.Themes.ButtonChrome> proporciona la apariencia del botón estándar, mientras que <xref:System.Windows.Controls.ContentPresenter> muestra el contenido del botón, según lo especificado por la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-315">The <xref:Microsoft.Windows.Themes.ButtonChrome> provides the standard button appearance, while the <xref:System.Windows.Controls.ContentPresenter> displays the button's content, as specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property.</span></span>

<span data-ttu-id="cfedf-316">A veces, la apariencia predeterminada de un control puede ser incongruente con la apariencia general de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfedf-316">Sometimes the default appearance of a control may be incongruent with the overall appearance of an application.</span></span> <span data-ttu-id="cfedf-317">En este caso, se puede usar un control <xref:System.Windows.Controls.ControlTemplate> para cambiar la apariencia de la interfaz de usuario del control sin modificar su contenido ni su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cfedf-317">In this case, you can use a <xref:System.Windows.Controls.ControlTemplate> to change the appearance of the control's user interface without changing its content and behavior.</span></span>

<span data-ttu-id="cfedf-318">En el ejemplo siguiente se muestra cómo cambiar la apariencia de un <xref:System.Windows.Controls.Button> mediante un <xref:System.Windows.Controls.ControlTemplate> :</span><span class="sxs-lookup"><span data-stu-id="cfedf-318">The following example shows how to change the appearance of a <xref:System.Windows.Controls.Button> by using a <xref:System.Windows.Controls.ControlTemplate>:</span></span>

[!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_16.xaml)]

[!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_17.cs)]
[!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_17.vb)]

<span data-ttu-id="cfedf-319">En este ejemplo, la interfaz de usuario del botón predeterminado se ha reemplazado por una forma <xref:System.Windows.Shapes.Ellipse> que tiene un borde azul marino y se rellena mediante <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="cfedf-319">In this example, the default button user interface has been replaced with an <xref:System.Windows.Shapes.Ellipse> that has a dark blue border and is filled using a <xref:System.Windows.Media.RadialGradientBrush>.</span></span> <span data-ttu-id="cfedf-320">El control <xref:System.Windows.Controls.ContentPresenter> muestra el contenido de <xref:System.Windows.Controls.Button>, "Click Me!".</span><span class="sxs-lookup"><span data-stu-id="cfedf-320">The <xref:System.Windows.Controls.ContentPresenter> control displays the content of the <xref:System.Windows.Controls.Button>, "Click Me!"</span></span> <span data-ttu-id="cfedf-321">Cuando se hace clic en <xref:System.Windows.Controls.Button> , el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> todavía se provoca como parte del comportamiento predeterminado del control <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-321">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event is still raised as part of the <xref:System.Windows.Controls.Button> control's default behavior.</span></span> <span data-ttu-id="cfedf-322">El resultado se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfedf-322">The result is shown in the following figure:</span></span>

![Botón elíptico y una segunda ventana](media/introduction-to-wpf/wpfintrofigure2.png)

### <a name="data-templates"></a><span data-ttu-id="cfedf-324">Plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="cfedf-324">Data templates</span></span>

<span data-ttu-id="cfedf-325">Mientras que una plantilla de control permite especificar la apariencia de un control, una plantilla de datos permite especificar la apariencia del contenido del control.</span><span class="sxs-lookup"><span data-stu-id="cfedf-325">Whereas a control template lets you specify the appearance of a control, a data template lets you specify the appearance of a control's content.</span></span> <span data-ttu-id="cfedf-326">Las plantillas de datos se usan con frecuencia para mejorar la manera de mostrar los datos enlazados.</span><span class="sxs-lookup"><span data-stu-id="cfedf-326">Data templates are frequently used to enhance how bound data is displayed.</span></span> <span data-ttu-id="cfedf-327">En la ilustración siguiente se muestra la apariencia predeterminada de un <xref:System.Windows.Controls.ListBox> que está enlazado a una colección de `Task` objetos, donde cada tarea tiene un nombre, una descripción y una prioridad:</span><span class="sxs-lookup"><span data-stu-id="cfedf-327">The following figure shows the default appearance for a <xref:System.Windows.Controls.ListBox> that is bound to a collection of `Task` objects, where each task has a name, description, and priority:</span></span>

![Cuadro de lista con el aspecto predeterminado](media/introduction-to-wpf/wpfintrofigure18.png)

<span data-ttu-id="cfedf-329">La apariencia predeterminada es la que cabría esperar de un control <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="cfedf-329">The default appearance is what you would expect from a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="cfedf-330">Sin embargo, la apariencia predeterminada de cada tarea contiene únicamente el nombre de tarea.</span><span class="sxs-lookup"><span data-stu-id="cfedf-330">However, the default appearance of each task contains only the task name.</span></span> <span data-ttu-id="cfedf-331">Para mostrar el nombre de la tarea, la descripción y la prioridad, la apariencia predeterminada de los elementos de lista enlazados al control <xref:System.Windows.Controls.ListBox> se debe modificar mediante una plantilla de datos <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="cfedf-331">To show the task name, description, and priority, the default appearance of the <xref:System.Windows.Controls.ListBox> control's bound list items must be changed by using a <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="cfedf-332">El código XAML siguiente define este tipo <xref:System.Windows.DataTemplate> , que se aplica a cada tarea mediante el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> atributo:</span><span class="sxs-lookup"><span data-stu-id="cfedf-332">The following XAML defines such a <xref:System.Windows.DataTemplate>, which is applied to each task by using the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> attribute:</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="SDKSample.DataTemplateWindow"
  Title="With a Data Template">
  <Window.Resources>
    <!-- Data Template (applied to each bound task item in the task collection) -->
    <DataTemplate x:Key="myTaskTemplate">
      <Border Name="border" BorderBrush="DarkSlateBlue" BorderThickness="2"
        CornerRadius="2" Padding="5" Margin="5">
        <Grid>
          <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
          </Grid.RowDefinitions>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition />
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Row="0" Grid.Column="0" Padding="0,0,5,0" Text="Task Name:"/>
          <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Path=TaskName}"/>
          <TextBlock Grid.Row="1" Grid.Column="0" Padding="0,0,5,0" Text="Description:"/>
          <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Path=Description}"/>
          <TextBlock Grid.Row="2" Grid.Column="0" Padding="0,0,5,0" Text="Priority:"/>
          <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Path=Priority}"/>
        </Grid>
      </Border>
    </DataTemplate>
  </Window.Resources>

  <!-- UI -->
  <DockPanel>
    <!-- Title -->
    <Label DockPanel.Dock="Top" FontSize="18" Margin="5" Content="My Task List:"/>

    <!-- Data template is specified by the ItemTemplate attribute -->
    <ListBox
      ItemsSource="{Binding}"
      ItemTemplate="{StaticResource myTaskTemplate}"
      HorizontalContentAlignment="Stretch"
      IsSynchronizedWithCurrentItem="True"
      Margin="5,0,5,5" />

 </DockPanel>
</Window>
```

<span data-ttu-id="cfedf-333">En la ilustración siguiente se muestra el efecto de este código:</span><span class="sxs-lookup"><span data-stu-id="cfedf-333">The following figure shows the effect of this code:</span></span>

![Cuadro de lista que usa una plantilla de datos](media/introduction-to-wpf/wpfintrofigure19.png)

<span data-ttu-id="cfedf-335">Observe que el control <xref:System.Windows.Controls.ListBox> conserva su comportamiento y apariencia general; sólo se modificó la apariencia del contenido mostrado por el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="cfedf-335">Note that the <xref:System.Windows.Controls.ListBox> has retained its behavior and overall appearance; only the appearance of the content being displayed by the list box has changed.</span></span>

<span data-ttu-id="cfedf-336">Para obtener más información, vea [Información general sobre plantillas de datos](data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-336">For more information, see [Data templating overview](data/data-templating-overview.md).</span></span>

### <a name="styles"></a><span data-ttu-id="cfedf-337">Estilos</span><span class="sxs-lookup"><span data-stu-id="cfedf-337">Styles</span></span>

<span data-ttu-id="cfedf-338">Los estilos permiten que los desarrolladores y diseñadores estandaricen un aspecto determinado de su producto.</span><span class="sxs-lookup"><span data-stu-id="cfedf-338">Styles enable developers and designers to standardize on a particular appearance for their product.</span></span> <span data-ttu-id="cfedf-339">WPF proporciona un modelo de estilo eficaz, cuya base es el elemento <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="cfedf-339">WPF provides a strong style model, the foundation of which is the <xref:System.Windows.Style> element.</span></span> <span data-ttu-id="cfedf-340">En el ejemplo siguiente se crea un estilo que establece el color de fondo de cada <xref:System.Windows.Controls.Button> en una ventana para `Orange` :</span><span class="sxs-lookup"><span data-stu-id="cfedf-340">The following example creates a style that sets the background color for every <xref:System.Windows.Controls.Button> on a window to `Orange`:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">
  <!-- Style that will be applied to all buttons -->
  <Style TargetType="{x:Type Button}">
    <Setter Property="Background" Value="Orange" />
    <Setter Property="BorderBrush" Value="Crimson" />
    <Setter Property="FontSize" Value="20" />
    <Setter Property="FontWeight" Value="Bold" />
    <Setter Property="Margin" Value="5" />
  </Style>
  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>

  <!-- This label will not have the style applied to it -->
  <Label>Don't Click Me!</Label>

  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>
</Window>
```

<span data-ttu-id="cfedf-341">Dado que este estilo tiene como destino todos los controles <xref:System.Windows.Controls.Button>, se aplica automáticamente a todos los botones de la ventana, tal como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfedf-341">Because this style targets all <xref:System.Windows.Controls.Button> controls, the style is automatically applied to all the buttons in the window, as shown in the following figure:</span></span>

![Dos botones de color naranja](media/introduction-to-wpf/wpfintrofigure20.png)

<span data-ttu-id="cfedf-343">Para más información, vea [Estilos y plantillas](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-343">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="resources"></a><span data-ttu-id="cfedf-344">Recursos</span><span class="sxs-lookup"><span data-stu-id="cfedf-344">Resources</span></span>

<span data-ttu-id="cfedf-345">Los controles de una aplicación deben compartir la misma apariencia, que puede incluir todo tipo de recursos, desde fuentes y colores de fondo hasta plantillas de control, plantillas de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-345">Controls in an application should share the same appearance, which can include anything from fonts and background colors to control templates, data templates, and styles.</span></span> <span data-ttu-id="cfedf-346">Se puede usar la compatibilidad de WPF con los recursos de la interfaz de usuario para encapsular estos recursos en una ubicación única y poder reutilizarlos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-346">You can use WPF's support for user interface resources to encapsulate these resources in a single location for reuse.</span></span>

<span data-ttu-id="cfedf-347">En el ejemplo siguiente se define un color de fondo común que comparten un <xref:System.Windows.Controls.Button> y un <xref:System.Windows.Controls.Label> :</span><span class="sxs-lookup"><span data-stu-id="cfedf-347">The following example defines a common background color that is shared by a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.Label>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">

  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>
</Window>
```

<span data-ttu-id="cfedf-348">En este ejemplo se implementa un recurso de color de fondo mediante el elemento de propiedad `Window.Resources` .</span><span class="sxs-lookup"><span data-stu-id="cfedf-348">This example implements a background color resource by using the `Window.Resources` property element.</span></span> <span data-ttu-id="cfedf-349">Este recurso está disponible para todos los elementos secundarios de <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="cfedf-349">This resource is available to all children of the <xref:System.Windows.Window>.</span></span> <span data-ttu-id="cfedf-350">Hay una gran variedad de ámbitos de recursos, incluidos los siguientes, que se muestran en el orden en que se resuelven:</span><span class="sxs-lookup"><span data-stu-id="cfedf-350">There are a variety of resource scopes, including the following, listed in the order in which they are resolved:</span></span>

1. <span data-ttu-id="cfedf-351">Un control individual (mediante la propiedad <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> heredada).</span><span class="sxs-lookup"><span data-stu-id="cfedf-351">An individual control (using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

2. <span data-ttu-id="cfedf-352"><xref:System.Windows.Window> o <xref:System.Windows.Controls.Page> (también mediante la propiedad <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> heredada).</span><span class="sxs-lookup"><span data-stu-id="cfedf-352">A <xref:System.Windows.Window> or a <xref:System.Windows.Controls.Page> (also using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

3. <span data-ttu-id="cfedf-353"><xref:System.Windows.Application> (mediante la propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="cfedf-353">An <xref:System.Windows.Application> (using the <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> property).</span></span>

<span data-ttu-id="cfedf-354">La variedad de ámbitos aporta flexibilidad al desarrollador con respecto a la manera de definir y compartir los recursos.</span><span class="sxs-lookup"><span data-stu-id="cfedf-354">The variety of scopes gives you flexibility with respect to the way in which you define and share your resources.</span></span>

<span data-ttu-id="cfedf-355">Como alternativa para asociar directamente los recursos a un ámbito determinado, se puede empaquetar uno o varios recursos mediante un <xref:System.Windows.ResourceDictionary> independiente al que puede hacer referencia en otras partes de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfedf-355">As an alternative to directly associating your resources with a particular scope, you can package one or more resources by using a separate <xref:System.Windows.ResourceDictionary> that can be referenced in other parts of an application.</span></span> <span data-ttu-id="cfedf-356">Por ejemplo, en el ejemplo siguiente se define un color de fondo predeterminado en un diccionario de recursos:</span><span class="sxs-lookup"><span data-stu-id="cfedf-356">For example, the following example defines a default background color in a resource dictionary:</span></span>

```xaml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```

<span data-ttu-id="cfedf-357">En el ejemplo siguiente se hace referencia al Diccionario de recursos definido en el ejemplo anterior para que se comparta en una aplicación:</span><span class="sxs-lookup"><span data-stu-id="cfedf-357">The following example references the resource dictionary defined in the previous example so that it is shared across an application:</span></span>

```xaml
<Application
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.App">

  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="BackgroundColorResources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```

<span data-ttu-id="cfedf-358">Los recursos y los diccionarios de recursos constituyen la base de la compatibilidad de WPF con los temas y las máscaras.</span><span class="sxs-lookup"><span data-stu-id="cfedf-358">Resources and resource dictionaries are the foundation of WPF support for themes and skins.</span></span>

<span data-ttu-id="cfedf-359">Para obtener más información, consulte [Recursos](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-359">For more information, see [Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="custom-controls"></a><span data-ttu-id="cfedf-360">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="cfedf-360">Custom controls</span></span>

<span data-ttu-id="cfedf-361">Aunque WPF proporciona una amplísima compatibilidad con funciones de personalización, puede encontrar situaciones en que los controles existentes de WPF no satisfagan las necesidades de la aplicación o de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cfedf-361">Although WPF provides a host of customization support, you may encounter situations where existing WPF controls do not meet the needs of either your application or its users.</span></span> <span data-ttu-id="cfedf-362">Esto puede suceder si:</span><span class="sxs-lookup"><span data-stu-id="cfedf-362">This can occur when:</span></span>

- <span data-ttu-id="cfedf-363">La UI que se necesita no puede crearse personalizando la apariencia y el funcionamiento de las implementaciones de WPF existentes.</span><span class="sxs-lookup"><span data-stu-id="cfedf-363">The user interface that you require cannot be created by customizing the look and feel of existing WPF implementations.</span></span>

- <span data-ttu-id="cfedf-364">Las implementaciones de WPF existentes no admiten el comportamiento que se necesita (o lo admiten, pero no fácilmente).</span><span class="sxs-lookup"><span data-stu-id="cfedf-364">The behavior that you require is not supported (or not easily supported) by existing WPF implementations.</span></span>

<span data-ttu-id="cfedf-365">Sin embargo, en este punto puede sacar partido de uno de los tres modelos de WPF para crear un nuevo control.</span><span class="sxs-lookup"><span data-stu-id="cfedf-365">At this point, however, you can take advantage of one of three WPF models to create a new control.</span></span> <span data-ttu-id="cfedf-366">Cada modelo está destinado a un escenario concreto y necesita que el control personalizado se derive de una clase base de WPF determinada.</span><span class="sxs-lookup"><span data-stu-id="cfedf-366">Each model targets a specific scenario and requires your custom control to derive from a particular WPF base class.</span></span> <span data-ttu-id="cfedf-367">A continuación se muestran los tres modelos:</span><span class="sxs-lookup"><span data-stu-id="cfedf-367">The three models are listed here:</span></span>

- <span data-ttu-id="cfedf-368">**Modelo de control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="cfedf-368">**User Control Model**.</span></span> <span data-ttu-id="cfedf-369">El control personalizado se deriva de <xref:System.Windows.Controls.UserControl> y se crea a partir de uno o varios controles.</span><span class="sxs-lookup"><span data-stu-id="cfedf-369">A custom control derives from <xref:System.Windows.Controls.UserControl> and is composed of one or more other controls.</span></span>

- <span data-ttu-id="cfedf-370">**Modelo de control**.</span><span class="sxs-lookup"><span data-stu-id="cfedf-370">**Control Model**.</span></span> <span data-ttu-id="cfedf-371">El control personalizado se deriva de <xref:System.Windows.Controls.Control> y se usa para crear implementaciones que separan su comportamiento de su apariencia mediante plantillas, de un modo muy similar a la mayoría de los controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-371">A custom control derives from <xref:System.Windows.Controls.Control> and is used to build implementations that separate their behavior from their appearance using templates, much like the majority of WPF controls.</span></span> <span data-ttu-id="cfedf-372">Al derivarse de <xref:System.Windows.Controls.Control> , permite mayor libertad para la creación de una UI personalizada que los controles de usuario, pero puede requerir más esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="cfedf-372">Deriving from <xref:System.Windows.Controls.Control> allows you more freedom for creating a custom user interface than user controls, but it may require more effort.</span></span>

- <span data-ttu-id="cfedf-373">**Modelo de elemento de marco de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="cfedf-373">**Framework Element Model**.</span></span> <span data-ttu-id="cfedf-374">Un control personalizado se deriva de <xref:System.Windows.FrameworkElement> cuando su apariencia se define mediante la lógica de representación personalizada (no mediante plantillas).</span><span class="sxs-lookup"><span data-stu-id="cfedf-374">A custom control derives from <xref:System.Windows.FrameworkElement> when its appearance is defined by custom rendering logic (not templates).</span></span>

<span data-ttu-id="cfedf-375">En el ejemplo siguiente se muestra un control numérico personalizado de arriba/abajo que deriva de <xref:System.Windows.Controls.UserControl> :</span><span class="sxs-lookup"><span data-stu-id="cfedf-375">The following example shows a custom numeric up/down control that derives from <xref:System.Windows.Controls.UserControl>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_33.xaml)]

[!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_34.cs)]
[!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_34.vb)]

<span data-ttu-id="cfedf-376">En el ejemplo siguiente se muestra el código XAML necesario para incorporar el control de usuario a un <xref:System.Windows.Window> :</span><span class="sxs-lookup"><span data-stu-id="cfedf-376">The following example illustrates the XAML that is required to incorporate the user control into a <xref:System.Windows.Window>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_37.xaml)]

<span data-ttu-id="cfedf-377">En la ilustración siguiente se muestra el `NumericUpDown` control hospedado en una <xref:System.Windows.Window> :</span><span class="sxs-lookup"><span data-stu-id="cfedf-377">The following figure shows the `NumericUpDown` control hosted in a <xref:System.Windows.Window>:</span></span>

![UserControl personalizado](media/introduction-to-wpf/wpfintrofigure3.png)

<span data-ttu-id="cfedf-379">Para obtener más información sobre los controles personalizados, vea [Información general sobre la creación de controles](controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cfedf-379">For more information on custom controls, see [Control authoring overview](controls/control-authoring-overview.md).</span></span>

## <a name="wpf-best-practices"></a><span data-ttu-id="cfedf-380">Procedimientos recomendados en WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-380">WPF best practices</span></span>

<span data-ttu-id="cfedf-381">Como sucede con cualquier plataforma de desarrollo, WPF se puede usar de diversas maneras para lograr el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="cfedf-381">As with any development platform, WPF can be used in a variety of ways to achieve the desired result.</span></span> <span data-ttu-id="cfedf-382">Para asegurarse de que las aplicaciones de WPF proporcionen la experiencia del usuario necesaria y satisfagan las exigencias del público en general, existen procedimientos recomendados de accesibilidad, globalización y localización, y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cfedf-382">As a way of ensuring that your WPF applications provide the required user experience and meet the demands of the audience in general, there are recommended best practices for accessibility, globalization and localization, and performance.</span></span> <span data-ttu-id="cfedf-383">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="cfedf-383">For more information, see:</span></span>

- [<span data-ttu-id="cfedf-384">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="cfedf-384">Accessibility</span></span>](../ui-automation/accessibility-best-practices.md)
- [<span data-ttu-id="cfedf-385">Globalización y localización de WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-385">WPF globalization and localization</span></span>](advanced/wpf-globalization-and-localization-overview.md)
- [<span data-ttu-id="cfedf-386">Rendimiento de aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-386">WPF app performance</span></span>](advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="cfedf-387">Seguridad de WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-387">WPF security</span></span>](security-wpf.md)

## <a name="next-steps"></a><span data-ttu-id="cfedf-388">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cfedf-388">Next steps</span></span>

<span data-ttu-id="cfedf-389">Hemos analizado las principales características de WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-389">We've looked at the key features of WPF.</span></span> <span data-ttu-id="cfedf-390">Ahora es el momento de que compile su primera aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="cfedf-390">Now it's time to build your first WPF app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cfedf-391">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-391">Walkthrough: My first WPF desktop app</span></span>](getting-started/walkthrough-my-first-wpf-desktop-application.md)

## <a name="see-also"></a><span data-ttu-id="cfedf-392">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfedf-392">See also</span></span>

- [<span data-ttu-id="cfedf-393">Introducción a WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-393">Get started with WPF</span></span>](getting-started/index.md)
- [<span data-ttu-id="cfedf-394">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="cfedf-394">Windows Presentation Foundation</span></span>](index.md)
- [<span data-ttu-id="cfedf-395">Recursos de la comunidad de WPF</span><span class="sxs-lookup"><span data-stu-id="cfedf-395">WPF community resources</span></span>](getting-started/community-feedback.md)
