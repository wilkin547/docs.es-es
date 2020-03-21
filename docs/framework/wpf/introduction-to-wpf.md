---
title: Introducción a WPF
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
dev_langs:
- csharp
- vb
ms.openlocfilehash: 759c1ca20ac139ef856df08ec42fb259fc3920d1
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112016"
---
# <a name="wpf-overview"></a><span data-ttu-id="ed169-102">Información general sobre WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-102">WPF overview</span></span>

<span data-ttu-id="ed169-103">Windows Presentation Foundation (WPF) le permite crear aplicaciones de cliente de escritorio para Windows con experiencias de usuario visualmente impactantes.</span><span class="sxs-lookup"><span data-stu-id="ed169-103">Windows Presentation Foundation (WPF) lets you create desktop client applications for Windows with visually stunning user experiences.</span></span>

![Ejemplo Contoso Healthcare UI](media/introduction-to-wpf/wpfintrofigure24.png)

<span data-ttu-id="ed169-105">El núcleo de WPF es un motor de representación basado en vectores e independiente de la resolución que está diseñado para sacar partido al moderno hardware gráfico.</span><span class="sxs-lookup"><span data-stu-id="ed169-105">The core of WPF is a resolution-independent and vector-based rendering engine that is built to take advantage of modern graphics hardware.</span></span> <span data-ttu-id="ed169-106">WPF amplía el núcleo con un conjunto completo de características de desarrollo de aplicaciones que incluyen Extensible Application Markup Language (XAML), controles, enlace de datos, diseño, gráficos en 2D y 3D, animación, estilos, plantillas, documentos, elementos multimedia, texto y tipografía.</span><span class="sxs-lookup"><span data-stu-id="ed169-106">WPF extends the core with a comprehensive set of application-development features that include Extensible Application Markup Language (XAML), controls, data binding, layout, 2D and 3D graphics, animation, styles, templates, documents, media, text, and typography.</span></span> <span data-ttu-id="ed169-107">WPF es parte de. NET, así que permite compilar aplicaciones que incorporan otros elementos de la API de .NET.</span><span class="sxs-lookup"><span data-stu-id="ed169-107">WPF is part of .NET, so you can build applications that incorporate other elements of the .NET API.</span></span>

<span data-ttu-id="ed169-108">Esta introducción está dirigida a personas que aún no conocen WPF, y en ella se abordan sus conceptos y capacidades principales.</span><span class="sxs-lookup"><span data-stu-id="ed169-108">This overview is intended for newcomers and covers the key capabilities and concepts of WPF.</span></span>

## <a name="program-with-wpf"></a><span data-ttu-id="ed169-109">Programar con WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-109">Program with WPF</span></span>

<span data-ttu-id="ed169-110">WPF existe como un subconjunto de tipos de .NET que, en su mayoría, están ubicados en el espacio de nombres <xref:System.Windows>.</span><span class="sxs-lookup"><span data-stu-id="ed169-110">WPF exists as a subset of .NET types that are (for the most part) located in the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="ed169-111">Si ha compilado previamente aplicaciones con .NET mediante tecnologías administradas como ASP.NET y Windows Forms, la experiencia de programación fundamental en WPF debe resultarle familiar; cree instancias de clases, defina propiedades, llame a métodos y controle eventos con el lenguaje de programación de .NET que prefiera, como C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ed169-111">If you have previously built applications with .NET using managed technologies like ASP.NET and Windows Forms, the fundamental WPF programming experience should be familiar; you instantiate classes, set properties, call methods, and handle events, using your favorite .NET programming language, such as C# or Visual Basic.</span></span>

<span data-ttu-id="ed169-112">WPF incluye construcciones de programación adicionales que mejoran las propiedades y los eventos: las [propiedades de dependencia](advanced/dependency-properties-overview.md) y los [eventos enrutados](advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-112">WPF includes additional programming constructs that enhance properties and events: [dependency properties](advanced/dependency-properties-overview.md) and [routed events](advanced/routed-events-overview.md).</span></span>

## <a name="markup-and-code-behind"></a><span data-ttu-id="ed169-113">Marcado y código subyacente</span><span class="sxs-lookup"><span data-stu-id="ed169-113">Markup and code-behind</span></span>

<span data-ttu-id="ed169-114">WPF permite desarrollar una aplicación que use tanto *marcado* como *código subyacente*, una experiencia que les resultará familiar a los desarrolladores de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ed169-114">WPF lets you develop an application using both *markup* and *code-behind*, an experience with which ASP.NET developers should be familiar.</span></span> <span data-ttu-id="ed169-115">En general, se usa marcado XAML para implementar la apariencia de una aplicación y lenguajes de programación administrados (código subyacente) para implementar su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ed169-115">You generally use XAML markup to implement the appearance of an application while using managed programming languages (code-behind) to implement its behavior.</span></span> <span data-ttu-id="ed169-116">Esta separación entre la apariencia y el comportamiento tiene las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed169-116">This separation of appearance and behavior has the following benefits:</span></span>

- <span data-ttu-id="ed169-117">Se reducen los costes de desarrollo y mantenimiento porque el marcado específico de la apariencia no está asociado estrechamente al código específico del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ed169-117">Development and maintenance costs are reduced because appearance-specific markup is not tightly coupled with behavior-specific code.</span></span>

- <span data-ttu-id="ed169-118">La programación es más eficaz porque los diseñadores pueden implementar la apariencia de una aplicación al mismo tiempo que los programadores implementan su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ed169-118">Development is more efficient because designers can implement an application's appearance simultaneously with developers who are implementing the application's behavior.</span></span>

- <span data-ttu-id="ed169-119">La[globalización y localización](advanced/wpf-globalization-and-localization-overview.md) de las aplicaciones WPF se ha simplificado.</span><span class="sxs-lookup"><span data-stu-id="ed169-119">[Globalization and localization](advanced/wpf-globalization-and-localization-overview.md) for WPF applications is simplified.</span></span>

### <a name="markup"></a><span data-ttu-id="ed169-120">marcado</span><span class="sxs-lookup"><span data-stu-id="ed169-120">Markup</span></span>

<span data-ttu-id="ed169-121">XAML es un lenguaje de marcado basado en XML que se usa para implementar la apariencia de una aplicación mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="ed169-121">XAML is an XML-based markup language that implements an application's appearance declaratively.</span></span> <span data-ttu-id="ed169-122">Se suele usar para crear ventanas, cuadros de diálogo, páginas y controles de usuario, así como para rellenarlos con controles, formas y gráficos.</span><span class="sxs-lookup"><span data-stu-id="ed169-122">You typically use it to create windows, dialog boxes, pages, and user controls, and to fill them with controls, shapes, and graphics.</span></span>

<span data-ttu-id="ed169-123">En el ejemplo siguiente se usa XAML para implementar la apariencia de una ventana que contiene un solo botón:</span><span class="sxs-lookup"><span data-stu-id="ed169-123">The following example uses XAML to implement the appearance of a window that contains a single button:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

<span data-ttu-id="ed169-124">En concreto, este código XAML define una ventana y un botón mediante el uso de los elementos `Window` y `Button` , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ed169-124">Specifically, this XAML defines a window and a button by using the `Window` and `Button` elements, respectively.</span></span> <span data-ttu-id="ed169-125">Cada elemento se configura con atributos como, por ejemplo, el atributo `Window` del elemento `Title` para especificar el texto de la barra de título de la ventana.</span><span class="sxs-lookup"><span data-stu-id="ed169-125">Each element is configured with attributes, such as the `Window` element's `Title` attribute to specify the window's title-bar text.</span></span> <span data-ttu-id="ed169-126">En tiempo de ejecución, WPF convierte los elementos y los atributos que se definen en el marcado en instancias de clases de WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-126">At run time, WPF converts the elements and attributes that are defined in markup to instances of WPF classes.</span></span> <span data-ttu-id="ed169-127">Por ejemplo, el elemento `Window` se convierte en una instancia de la clase <xref:System.Windows.Window> cuya propiedad <xref:System.Windows.Window.Title%2A> es el valor del atributo `Title` .</span><span class="sxs-lookup"><span data-stu-id="ed169-127">For example, the `Window` element is converted to an instance of the <xref:System.Windows.Window> class whose <xref:System.Windows.Window.Title%2A> property is the value of the `Title` attribute.</span></span>

<span data-ttu-id="ed169-128">La figura siguiente muestra la interfaz de usuario (UI) definida por el XAML en el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="ed169-128">The following figure shows the user interface (UI) that is defined by the XAML in the previous example:</span></span>

![Ventana que contiene un botón](media/introduction-to-wpf/wpfintrofigure10.png)

<span data-ttu-id="ed169-130">Dado que XAML se basa en XML, la interfaz de usuario que se crea con este lenguaje se ensambla en una jerarquía de elementos anidados, que se denomina [árbol de elementos](advanced/trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-130">Since XAML is XML-based, the UI that you compose with it is assembled in a hierarchy of nested elements known as an [element tree](advanced/trees-in-wpf.md).</span></span> <span data-ttu-id="ed169-131">El árbol de elementos proporciona una manera lógica e intuitiva para crear y administrar las interfaces de usuario.</span><span class="sxs-lookup"><span data-stu-id="ed169-131">The element tree provides a logical and intuitive way to create and manage UIs.</span></span>

### <a name="code-behind"></a><span data-ttu-id="ed169-132">Código subyacente</span><span class="sxs-lookup"><span data-stu-id="ed169-132">Code-behind</span></span>

<span data-ttu-id="ed169-133">El comportamiento principal de una aplicación consiste en implementar la funcionalidad que responde a las interacciones del usuario, lo que incluye controlar los eventos (por ejemplo, hacer clic en un menú, una barra de herramientas o un botón) y llamar, en respuesta, a la lógica de negocios y al acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="ed169-133">The main behavior of an application is to implement the functionality that responds to user interactions, including handling events (for example, clicking a menu, tool bar, or button) and calling business logic and data access logic in response.</span></span> <span data-ttu-id="ed169-134">En WPF, este comportamiento se implementa en el código que está asociado al marcado.</span><span class="sxs-lookup"><span data-stu-id="ed169-134">In WPF, this behavior is implemented in code that is associated with markup.</span></span> <span data-ttu-id="ed169-135">Este tipo de código se conoce como código subyacente.</span><span class="sxs-lookup"><span data-stu-id="ed169-135">This type of code is known as code-behind.</span></span> <span data-ttu-id="ed169-136">En el ejemplo siguiente se muestra el marcado actualizado del ejemplo anterior y el código subyacente:</span><span class="sxs-lookup"><span data-stu-id="ed169-136">The following example shows the updated markup from the previous example and the code-behind:</span></span>

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

<span data-ttu-id="ed169-137">En este ejemplo, el código subyacente implementa una clase que deriva de la clase <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="ed169-137">In this example, the code-behind implements a class that derives from the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="ed169-138">El atributo `x:Class` se usa para asociar el marcado a la clase de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="ed169-138">The `x:Class` attribute is used to associate the markup with the code-behind class.</span></span> <span data-ttu-id="ed169-139">Se llama a `InitializeComponent` desde el constructor de la clase de código subyacente para combinar la interfaz de usuario que se define en el marcado con la clase de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="ed169-139">`InitializeComponent` is called from the code-behind class's constructor to merge the UI that is defined in markup with the code-behind class.</span></span> <span data-ttu-id="ed169-140">(`InitializeComponent` se genera automáticamente cuando se compila la aplicación, por lo que no es necesario implementarla manualmente.) La combinación `InitializeComponent` de y asegurarse de `x:Class` que la implementación se inicializa correctamente cada vez que se crea.</span><span class="sxs-lookup"><span data-stu-id="ed169-140">(`InitializeComponent` is generated for you when your application is built, which is why you don't need to implement it manually.) The combination of `x:Class` and `InitializeComponent` ensure that your implementation is correctly initialized whenever it is created.</span></span> <span data-ttu-id="ed169-141">La clase de código subyacente también implementa un controlador de eventos para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón.</span><span class="sxs-lookup"><span data-stu-id="ed169-141">The code-behind class also implements an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span> <span data-ttu-id="ed169-142">Cuando se hace clic en el botón, el controlador de eventos muestra un cuadro de mensaje mediante una llamada al método <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="ed169-142">When the button is clicked, the event handler shows a message box by calling the <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> method.</span></span>

<span data-ttu-id="ed169-143">La figura siguiente muestra el resultado cuando se hace clic en el botón:</span><span class="sxs-lookup"><span data-stu-id="ed169-143">The following figure shows the result when the button is clicked:</span></span>

![MessageBox](media/introduction-to-wpf/wpfintrofigure25.png)

## <a name="controls"></a><span data-ttu-id="ed169-145">Controles</span><span class="sxs-lookup"><span data-stu-id="ed169-145">Controls</span></span>

<span data-ttu-id="ed169-146">Las experiencias de usuario proporcionadas por el modelo de aplicación son controles construidos.</span><span class="sxs-lookup"><span data-stu-id="ed169-146">The user experiences that are delivered by the application model are constructed controls.</span></span> <span data-ttu-id="ed169-147">En WPF, *control* es un término genérico que se aplica a una categoría de clases de WPF que se hospedan en una ventana o una página, tienen una interfaz de usuario e implementan un comportamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="ed169-147">In WPF, *control* is an umbrella term that applies to a category of WPF classes that are hosted in either a window or a page, have a user interface, and implement some behavior.</span></span>

<span data-ttu-id="ed169-148">Para obtener más información, consulte [Controles](controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-148">For more information, see [Controls](controls/index.md).</span></span>

### <a name="wpf-controls-by-function"></a><span data-ttu-id="ed169-149">Controles de WPF por función</span><span class="sxs-lookup"><span data-stu-id="ed169-149">WPF controls by function</span></span>

<span data-ttu-id="ed169-150">Los controles WPF integrados se enumeran aquí:</span><span class="sxs-lookup"><span data-stu-id="ed169-150">The built-in WPF controls are listed here:</span></span>

- <span data-ttu-id="ed169-151">**Botones** <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.RepeatButton>: y .</span><span class="sxs-lookup"><span data-stu-id="ed169-151">**Buttons**: <xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.Primitives.RepeatButton>.</span></span>

- <span data-ttu-id="ed169-152">**Visualización** <xref:System.Windows.Controls.DataGrid>de <xref:System.Windows.Controls.ListView>datos <xref:System.Windows.Controls.TreeView>: , , y .</span><span class="sxs-lookup"><span data-stu-id="ed169-152">**Data Display**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, and <xref:System.Windows.Controls.TreeView>.</span></span>

- <span data-ttu-id="ed169-153">**Visualización y selección de fecha:** <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="ed169-153">**Date Display and Selection**: <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>.</span></span>

- <span data-ttu-id="ed169-154">**Cuadros** <xref:Microsoft.Win32.OpenFileDialog>de <xref:System.Windows.Controls.PrintDialog>diálogo <xref:Microsoft.Win32.SaveFileDialog>: , , y .</span><span class="sxs-lookup"><span data-stu-id="ed169-154">**Dialog Boxes**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, and <xref:Microsoft.Win32.SaveFileDialog>.</span></span>

- <span data-ttu-id="ed169-155">**Tinta**digital <xref:System.Windows.Controls.InkCanvas> <xref:System.Windows.Controls.InkPresenter>: y .</span><span class="sxs-lookup"><span data-stu-id="ed169-155">**Digital Ink**: <xref:System.Windows.Controls.InkCanvas> and <xref:System.Windows.Controls.InkPresenter>.</span></span>

- <span data-ttu-id="ed169-156">**Documentos** <xref:System.Windows.Controls.DocumentViewer> <xref:System.Windows.Controls.FlowDocumentPageViewer>: <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentScrollViewer>, <xref:System.Windows.Controls.StickyNoteControl>, , , y .</span><span class="sxs-lookup"><span data-stu-id="ed169-156">**Documents**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, and <xref:System.Windows.Controls.StickyNoteControl>.</span></span>

- <span data-ttu-id="ed169-157">**Entrada** <xref:System.Windows.Controls.TextBox>: <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.PasswordBox>, y .</span><span class="sxs-lookup"><span data-stu-id="ed169-157">**Input**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Controls.PasswordBox>.</span></span>

- <span data-ttu-id="ed169-158">**Diseño** <xref:System.Windows.Controls.Border>: <xref:System.Windows.Controls.Primitives.BulletDecorator> <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter> <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator> <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer> <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel> <xref:System.Windows.Window>, <xref:System.Windows.Controls.WrapPanel>, , , , , , , , , , , .</span><span class="sxs-lookup"><span data-stu-id="ed169-158">**Layout**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, and <xref:System.Windows.Controls.WrapPanel>.</span></span>

- <span data-ttu-id="ed169-159">**Medios** <xref:System.Windows.Controls.Image>: <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Controls.SoundPlayerAction>, y .</span><span class="sxs-lookup"><span data-stu-id="ed169-159">**Media**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, and <xref:System.Windows.Controls.SoundPlayerAction>.</span></span>

- <span data-ttu-id="ed169-160">**Menús** <xref:System.Windows.Controls.ContextMenu> <xref:System.Windows.Controls.Menu>: <xref:System.Windows.Controls.ToolBar>, , y .</span><span class="sxs-lookup"><span data-stu-id="ed169-160">**Menus**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, and <xref:System.Windows.Controls.ToolBar>.</span></span>

- <span data-ttu-id="ed169-161">**Navegación** <xref:System.Windows.Controls.Frame>: <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.TabControl>, , y .</span><span class="sxs-lookup"><span data-stu-id="ed169-161">**Navigation**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, and <xref:System.Windows.Controls.TabControl>.</span></span>

- <span data-ttu-id="ed169-162">**Selección** <xref:System.Windows.Controls.CheckBox>: <xref:System.Windows.Controls.ComboBox> <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.Slider>, , y .</span><span class="sxs-lookup"><span data-stu-id="ed169-162">**Selection**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, and <xref:System.Windows.Controls.Slider>.</span></span>

- <span data-ttu-id="ed169-163">**Información**del <xref:System.Windows.Controls.AccessText> <xref:System.Windows.Controls.Label>usuario <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.ProgressBar>: <xref:System.Windows.Controls.Primitives.StatusBar> <xref:System.Windows.Controls.TextBlock>, <xref:System.Windows.Controls.ToolTip>, , , , , , y .</span><span class="sxs-lookup"><span data-stu-id="ed169-163">**User Information**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.ToolTip>.</span></span>

## <a name="input-and-commands"></a><span data-ttu-id="ed169-164">Entrada y comandos</span><span class="sxs-lookup"><span data-stu-id="ed169-164">Input and commands</span></span>

<span data-ttu-id="ed169-165">Los controles casi siempre detectan las acciones del usuario y responden a ellas.</span><span class="sxs-lookup"><span data-stu-id="ed169-165">Controls most often detect and respond to user input.</span></span> <span data-ttu-id="ed169-166">El [sistema de entrada de WPF](advanced/input-overview.md) usa eventos directos y enrutados para admitir la entrada de texto, la administración del enfoque y la posición del mouse.</span><span class="sxs-lookup"><span data-stu-id="ed169-166">The [WPF input system](advanced/input-overview.md) uses both direct and routed events to support text input, focus management, and mouse positioning.</span></span>

<span data-ttu-id="ed169-167">Las aplicaciones a menudo tienen tener requisitos de entrada complejos.</span><span class="sxs-lookup"><span data-stu-id="ed169-167">Applications often have complex input requirements.</span></span> <span data-ttu-id="ed169-168">WPF proporciona un [sistema de comandos](advanced/commanding-overview.md) que separa las acciones de entrada del usuario del código que responde a esas acciones.</span><span class="sxs-lookup"><span data-stu-id="ed169-168">WPF provides a [command system](advanced/commanding-overview.md) that separates user-input actions from the code that responds to those actions.</span></span>

## <a name="layout"></a><span data-ttu-id="ed169-169">Diseño</span><span class="sxs-lookup"><span data-stu-id="ed169-169">Layout</span></span>

<span data-ttu-id="ed169-170">Al crear crear una interfaz de usuario, se organizan los controles según su ubicación y tamaño para crear un diseño.</span><span class="sxs-lookup"><span data-stu-id="ed169-170">When you create a user interface, you arrange your controls by location and size to form a layout.</span></span> <span data-ttu-id="ed169-171">Un requisito fundamental de cualquier diseño es adaptarse a los cambios de tamaño de la ventana y de configuración de pantalla.</span><span class="sxs-lookup"><span data-stu-id="ed169-171">A key requirement of any layout is to adapt to changes in window size and display settings.</span></span> <span data-ttu-id="ed169-172">En lugar de obligarle a escribir código que adapte el diseño en estas circunstancias, WPF le proporciona un sistema de diseño extensible de primera clase.</span><span class="sxs-lookup"><span data-stu-id="ed169-172">Rather than forcing you to write the code to adapt a layout in these circumstances, WPF provides a first-class, extensible layout system for you.</span></span>

<span data-ttu-id="ed169-173">La piedra angular del sistema de diseño es la posición relativa, que aumenta la capacidad de adaptación a los cambios en la configuración de las ventanas y la pantalla.</span><span class="sxs-lookup"><span data-stu-id="ed169-173">The cornerstone of the layout system is relative positioning, which increases the ability to adapt to changing window and display conditions.</span></span> <span data-ttu-id="ed169-174">Además, el sistema de diseño administra la negociación entre los controles para determinar el diseño.</span><span class="sxs-lookup"><span data-stu-id="ed169-174">In addition, the layout system manages the negotiation between controls to determine the layout.</span></span> <span data-ttu-id="ed169-175">La negociación es un proceso de dos pasos: en primer lugar, el control indica a su elemento primario qué ubicación y tamaño necesita; en segundo lugar, el elemento primario indica al control cuánto espacio dispone.</span><span class="sxs-lookup"><span data-stu-id="ed169-175">The negotiation is a two-step process: first, a control tells its parent what location and size it requires; second, the parent tells the control what space it can have.</span></span>

<span data-ttu-id="ed169-176">El sistema de diseño se expone a los controles secundarios mediante las clases base de WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-176">The layout system is exposed to child controls through base WPF classes.</span></span> <span data-ttu-id="ed169-177">Para los diseños comunes, como las cuadrículas, el apilamiento y el acoplamiento, WPF incluye varios controles de diseño:</span><span class="sxs-lookup"><span data-stu-id="ed169-177">For common layouts such as grids, stacking, and docking, WPF includes several layout controls:</span></span>

- <span data-ttu-id="ed169-178"><xref:System.Windows.Controls.Canvas>: los controles secundarios proporcionan su propio diseño.</span><span class="sxs-lookup"><span data-stu-id="ed169-178"><xref:System.Windows.Controls.Canvas>: Child controls provide their own layout.</span></span>

- <span data-ttu-id="ed169-179"><xref:System.Windows.Controls.DockPanel>: los controles secundarios se alinean con los bordes del panel.</span><span class="sxs-lookup"><span data-stu-id="ed169-179"><xref:System.Windows.Controls.DockPanel>: Child controls are aligned to the edges of the panel.</span></span>

- <span data-ttu-id="ed169-180"><xref:System.Windows.Controls.Grid>: los controles secundarios se colocan por filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="ed169-180"><xref:System.Windows.Controls.Grid>: Child controls are positioned by rows and columns.</span></span>

- <span data-ttu-id="ed169-181"><xref:System.Windows.Controls.StackPanel>: los controles secundarios se apilan vertical u horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="ed169-181"><xref:System.Windows.Controls.StackPanel>: Child controls are stacked either vertically or horizontally.</span></span>

- <span data-ttu-id="ed169-182"><xref:System.Windows.Controls.VirtualizingStackPanel>: los controles secundarios se virtualizan y se organizan en una sola línea en sentido horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="ed169-182"><xref:System.Windows.Controls.VirtualizingStackPanel>: Child controls are virtualized and arranged on a single line that is either horizontally or vertically oriented.</span></span>

- <span data-ttu-id="ed169-183"><xref:System.Windows.Controls.WrapPanel>: los controles secundarios se sitúan en orden de izquierda a derecha y se ajustan a la línea siguiente cuando hay más controles de los que caben en la línea actual.</span><span class="sxs-lookup"><span data-stu-id="ed169-183"><xref:System.Windows.Controls.WrapPanel>: Child controls are positioned in left-to-right order and wrapped to the next line when there are more controls on the current line than space allows.</span></span>

<span data-ttu-id="ed169-184">En el ejemplo <xref:System.Windows.Controls.DockPanel> siguiente se <xref:System.Windows.Controls.TextBox> utiliza a para establecer varios controles:</span><span class="sxs-lookup"><span data-stu-id="ed169-184">The following example uses a <xref:System.Windows.Controls.DockPanel> to lay out several <xref:System.Windows.Controls.TextBox> controls:</span></span>

[!code-xaml[IntroToWPFSnippets#LayoutMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_1.xaml)]

<span data-ttu-id="ed169-185"><xref:System.Windows.Controls.DockPanel> permite que los controles secundarios <xref:System.Windows.Controls.TextBox> le indiquen cómo se deben organizar.</span><span class="sxs-lookup"><span data-stu-id="ed169-185">The <xref:System.Windows.Controls.DockPanel> allows the child <xref:System.Windows.Controls.TextBox> controls to tell it how to arrange them.</span></span> <span data-ttu-id="ed169-186">Para ello, <xref:System.Windows.Controls.DockPanel> implementa una propiedad adjunta `Dock` que se expone a los controles secundarios para permitir que cada uno de ellos especifique un estilo de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="ed169-186">To do this, the <xref:System.Windows.Controls.DockPanel> implements a `Dock` attached property that is exposed to the child controls to allow each of them to specify a dock style.</span></span>

> [!NOTE]
> <span data-ttu-id="ed169-187">Una propiedad implementada por un control principal para que la usen los controles secundarios es una construcción de WPF denominada [propiedad adjunta](advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-187">A property that's implemented by a parent control for use by child controls is a WPF construct called an [attached property](advanced/attached-properties-overview.md).</span></span>

<span data-ttu-id="ed169-188">La siguiente figura muestra el resultado del marcado XAML en el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="ed169-188">The following figure shows the result of the XAML markup in the preceding example:</span></span>

![Página de DockPanel](media/introduction-to-wpf/wpfintrofigure11.png)

## <a name="data-binding"></a><span data-ttu-id="ed169-190">Enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ed169-190">Data binding</span></span>

<span data-ttu-id="ed169-191">La mayoría de las aplicaciones se crean para proporcionar a los usuarios recursos que les permitan ver y editar datos.</span><span class="sxs-lookup"><span data-stu-id="ed169-191">Most applications are created to provide users with the means to view and edit data.</span></span> <span data-ttu-id="ed169-192">Para las aplicaciones de WPF, el trabajo de almacenamiento de datos y el acceso a ellos ya se proporciona mediante tecnologías existentes, como SQL Server y ADO .NET.</span><span class="sxs-lookup"><span data-stu-id="ed169-192">For WPF applications, the work of storing and accessing data is already provided for by technologies such as SQL Server and ADO .NET.</span></span> <span data-ttu-id="ed169-193">Una vez que se tiene acceso a los datos y se cargan en los objetos administrados de la aplicación, comienza la tarea ardua de las aplicaciones WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-193">After the data is accessed and loaded into an application's managed objects, the hard work for WPF applications begins.</span></span> <span data-ttu-id="ed169-194">En esencia, esto implica dos cosas:</span><span class="sxs-lookup"><span data-stu-id="ed169-194">Essentially, this involves two things:</span></span>

1. <span data-ttu-id="ed169-195">Copiar los datos de los objetos administrados a los controles, donde los datos se pueden mostrar y editar.</span><span class="sxs-lookup"><span data-stu-id="ed169-195">Copying the data from the managed objects into controls, where the data can be displayed and edited.</span></span>

2. <span data-ttu-id="ed169-196">Asegurarse de que los cambios realizados en los datos mediante los controles se vuelvan a copiar a los objetos administrados.</span><span class="sxs-lookup"><span data-stu-id="ed169-196">Ensuring that changes made to data by using controls are copied back to the managed objects.</span></span>

<span data-ttu-id="ed169-197">Para simplificar el desarrollo de aplicaciones, WPF ofrece un motor de enlace de datos que sigue estos pasos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ed169-197">To simplify application development, WPF provides a data binding engine to automatically perform these steps.</span></span> <span data-ttu-id="ed169-198">La unidad que constituye el núcleo del motor de enlace de datos es la clase <xref:System.Windows.Data.Binding> , que se encarga de enlazar un control (el destino de enlace) a un objeto de datos (el origen de enlace).</span><span class="sxs-lookup"><span data-stu-id="ed169-198">The core unit of the data binding engine is the <xref:System.Windows.Data.Binding> class, whose job is to bind a control (the binding target) to a data object (the binding source).</span></span> <span data-ttu-id="ed169-199">Esta relación se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed169-199">This relationship is illustrated by the following figure:</span></span>

![Diagrama de enlace de datos básico](media/introduction-to-wpf/databindingmostbasic.png)

<span data-ttu-id="ed169-201">En el ejemplo siguiente, se muestra cómo enlazar un control <xref:System.Windows.Controls.TextBox> a una instancia de un objeto `Person` personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed169-201">The next example demonstrates how to bind a <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object.</span></span> <span data-ttu-id="ed169-202">La implementación de `Person` se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed169-202">The `Person` implementation is shown in the following code:</span></span>

[!code-vb[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_2.vb)]
[!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_2.cs)]

<span data-ttu-id="ed169-203">El marcado siguiente <xref:System.Windows.Controls.TextBox> enlaza el a `Person` una instancia de un objeto personalizado:</span><span class="sxs-lookup"><span data-stu-id="ed169-203">The following markup binds the <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object:</span></span>

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

<span data-ttu-id="ed169-204">En este ejemplo, se crea una instancia de la clase `Person` en el código subyacente y se establece como el contexto de datos para `DataBindingWindow`.</span><span class="sxs-lookup"><span data-stu-id="ed169-204">In this example, the `Person` class is instantiated in code-behind and is set as the data context for the `DataBindingWindow`.</span></span> <span data-ttu-id="ed169-205">En el marcado, la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> de <xref:System.Windows.Controls.TextBox> se enlaza a la propiedad `Person.Name` (mediante la sintaxis "`{Binding ... }`" de XAML).</span><span class="sxs-lookup"><span data-stu-id="ed169-205">In markup, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> is bound to the `Person.Name` property (using the "`{Binding ... }`" XAML syntax).</span></span> <span data-ttu-id="ed169-206">Este código XAML indica a WPF que enlace el control <xref:System.Windows.Controls.TextBox> al objeto `Person` almacenado en la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de la ventana.</span><span class="sxs-lookup"><span data-stu-id="ed169-206">This XAML tells WPF to bind the <xref:System.Windows.Controls.TextBox> control to the `Person` object that is stored in the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the window.</span></span>

<span data-ttu-id="ed169-207">El motor de enlace de datos de WPF proporciona compatibilidad adicional que incluye validación, ordenación, filtrado y agrupación.</span><span class="sxs-lookup"><span data-stu-id="ed169-207">The WPF data binding engine provides additional support that includes validation, sorting, filtering, and grouping.</span></span> <span data-ttu-id="ed169-208">Además, el enlace de datos admite el uso de plantillas de datos para crear una interfaz de usuario personalizada para los datos enlazados cuando la interfaz de usuario mostrada por los controles estándar de WPF no es adecuada.</span><span class="sxs-lookup"><span data-stu-id="ed169-208">Furthermore, data binding supports the use of data templates to create custom user interface for bound data when the user interface displayed by the standard WPF controls is not appropriate.</span></span>

<span data-ttu-id="ed169-209">Para obtener más información, vea [Introducción al enlace](../../desktop-wpf/data/data-binding-overview.md)de datos .</span><span class="sxs-lookup"><span data-stu-id="ed169-209">For more information, see [Data binding overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="graphics"></a><span data-ttu-id="ed169-210">Gráficos</span><span class="sxs-lookup"><span data-stu-id="ed169-210">Graphics</span></span>

<span data-ttu-id="ed169-211">WPF incluye un conjunto extenso, escalable y flexible de características de gráficos que tienen las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="ed169-211">WPF introduces an extensive, scalable, and flexible set of graphics features that have the following benefits:</span></span>

- <span data-ttu-id="ed169-212">**Gráficos independientes de la resolución e independientes del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ed169-212">**Resolution-independent and device-independent graphics**.</span></span> <span data-ttu-id="ed169-213">La unidad de medida básica del sistema de gráficos de WPF es el píxel independiente del dispositivo, que es 1/96 de pulgada (sea cual fuere la resolución de pantalla real), y proporciona la base para la representación independiente de la resolución y del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ed169-213">The basic unit of measurement in the WPF graphics system is the device-independent pixel, which is 1/96th of an inch, regardless of actual screen resolution, and provides the foundation for resolution-independent and device-independent rendering.</span></span> <span data-ttu-id="ed169-214">Cada píxel independiente del dispositivo se escala automáticamente para que coincida con la configuración de puntos por pulgada (ppp) del sistema en que se representa.</span><span class="sxs-lookup"><span data-stu-id="ed169-214">Each device-independent pixel automatically scales to match the dots-per-inch (dpi) setting of the system it renders on.</span></span>

- <span data-ttu-id="ed169-215">**Precisión mejorada**.</span><span class="sxs-lookup"><span data-stu-id="ed169-215">**Improved precision**.</span></span> <span data-ttu-id="ed169-216">El sistema de coordenadas de WPF se mide con números de punto flotante de precisión doble en lugar de precisión sencilla.</span><span class="sxs-lookup"><span data-stu-id="ed169-216">The WPF coordinate system is measured with double-precision floating-point numbers rather than single-precision.</span></span> <span data-ttu-id="ed169-217">Las transformaciones y los valores de opacidad también se expresan como de precisión doble.</span><span class="sxs-lookup"><span data-stu-id="ed169-217">Transformations and opacity values are also expressed as double-precision.</span></span> <span data-ttu-id="ed169-218">WPF admite, además, una gama de color amplia (scRGB) y ofrece compatibilidad integrada para la administración de entradas de diferentes espacios de color.</span><span class="sxs-lookup"><span data-stu-id="ed169-218">WPF also supports a wide color gamut (scRGB) and provides integrated support for managing inputs from different color spaces.</span></span>

- <span data-ttu-id="ed169-219">**Compatibilidad con gráficos y animación avanzados**.</span><span class="sxs-lookup"><span data-stu-id="ed169-219">**Advanced graphics and animation support**.</span></span> <span data-ttu-id="ed169-220">WPF simplifica la programación de gráficos administrando automáticamente las escenas de animación. No tendrá que preocuparse por el procesamiento de escenas, los bucles de presentación ni la interpolación bilineal.</span><span class="sxs-lookup"><span data-stu-id="ed169-220">WPF simplifies graphics programming by managing animation scenes for you; there is no need to worry about scene processing, rendering loops, and bilinear interpolation.</span></span> <span data-ttu-id="ed169-221">Además, WPF admite la prueba de clics y proporciona compatibilidad plena con la composición alfa.</span><span class="sxs-lookup"><span data-stu-id="ed169-221">Additionally, WPF provides hit-testing support and full alpha-compositing support.</span></span>

- <span data-ttu-id="ed169-222">**Aceleración de hardware**.</span><span class="sxs-lookup"><span data-stu-id="ed169-222">**Hardware acceleration**.</span></span> <span data-ttu-id="ed169-223">El sistema de gráficos de WPF saca partido del hardware de gráficos para minimizar el uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="ed169-223">The WPF graphics system takes advantage of graphics hardware to minimize CPU usage.</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="ed169-224">Formas en 2D</span><span class="sxs-lookup"><span data-stu-id="ed169-224">2D shapes</span></span>

<span data-ttu-id="ed169-225">WPF proporciona una biblioteca de formas en 2D comunes dibujadas mediante vectores, como los rectángulos y las elipses que se muestran en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed169-225">WPF provides a library of common vector-drawn 2D shapes, such as the rectangles and ellipses that are shown in the following illustration:</span></span>

![Elipses y rectángulos](media/introduction-to-wpf/wpfintrofigure4.PNG)

<span data-ttu-id="ed169-227">Una función interesante de las formas es que no sirven únicamente para su presentación; las formas implementan muchas de las características que cabe esperar de los controles, incluida la entrada de datos desde el teclado y el mouse.</span><span class="sxs-lookup"><span data-stu-id="ed169-227">An interesting capability of shapes is that they are not just for display; shapes implement many of the features that you expect from controls, including keyboard and mouse input.</span></span> <span data-ttu-id="ed169-228">En el ejemplo <xref:System.Windows.UIElement.MouseUp> siguiente <xref:System.Windows.Shapes.Ellipse> se muestra el evento de un controlador:</span><span class="sxs-lookup"><span data-stu-id="ed169-228">The following example shows the <xref:System.Windows.UIElement.MouseUp> event of an <xref:System.Windows.Shapes.Ellipse> being handled:</span></span>

[!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_7.xaml)]

[!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_8.vb)]
[!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_8.cs)]

<span data-ttu-id="ed169-229">La figura siguiente muestra lo que genera el código anterior:</span><span class="sxs-lookup"><span data-stu-id="ed169-229">The following figure shows what is produced by the preceding code:</span></span>

![Ventana con el texto "You clicked the ellipse&#33;" (Ha hecho clic en la elipse)](media/introduction-to-wpf/wpfintrofigure12.png)

<span data-ttu-id="ed169-231">Para obtener más información, vea [Formas y dibujo básico en Información general](../../desktop-wpf/data/data-binding-overview.md)de WPF .</span><span class="sxs-lookup"><span data-stu-id="ed169-231">For more information, see [Shapes and basic drawing in WPF overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="ed169-232">Geometrías en 2D</span><span class="sxs-lookup"><span data-stu-id="ed169-232">2D geometries</span></span>

<span data-ttu-id="ed169-233">Las formas en 2D que proporciona WPF abarcan el conjunto estándar de formas básicas.</span><span class="sxs-lookup"><span data-stu-id="ed169-233">The 2D shapes provided by WPF cover the standard set of basic shapes.</span></span> <span data-ttu-id="ed169-234">Pero tal vez sea necesario crear formas personalizadas para facilitar el diseño de una interfaz de usuario personalizada.</span><span class="sxs-lookup"><span data-stu-id="ed169-234">However, you may need to create custom shapes to facilitate the design of a customized user interface.</span></span> <span data-ttu-id="ed169-235">Para ello, WPF proporciona las geometrías.</span><span class="sxs-lookup"><span data-stu-id="ed169-235">For this purpose, WPF provides geometries.</span></span> <span data-ttu-id="ed169-236">En la siguiente ilustración se muestra el uso de geometrías para crear una forma personalizada que se puede dibujar directamente, usar como un pincel o usar para recortar otras formas y controles.</span><span class="sxs-lookup"><span data-stu-id="ed169-236">The following figure demonstrates the use of geometries to create a custom shape that can be drawn directly, used as a brush, or used to clip other shapes and controls.</span></span>

<span data-ttu-id="ed169-237">Los objetos<xref:System.Windows.Shapes.Path> se pueden usar para dibujar formas cerradas o abiertas, varias formas o incluso formas curvas.</span><span class="sxs-lookup"><span data-stu-id="ed169-237"><xref:System.Windows.Shapes.Path> objects can be used to draw closed or open shapes, multiple shapes, and even curved shapes.</span></span>

<span data-ttu-id="ed169-238">Los objetos <xref:System.Windows.Media.Geometry> se pueden usar para el recorte, la prueba de posicionamiento y la representación de datos de gráficos en 2D.</span><span class="sxs-lookup"><span data-stu-id="ed169-238"><xref:System.Windows.Media.Geometry> objects can be used for clipping, hit-testing, and rendering 2D graphic data.</span></span>

![Varios usos de una ruta de acceso](media/introduction-to-wpf/wpfintrofigure5.png)

<span data-ttu-id="ed169-240">Para obtener más información, vea [Información general sobre geometría](graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-240">For more information, see [Geometry overview](graphics-multimedia/geometry-overview.md).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="ed169-241">Efectos en 2D</span><span class="sxs-lookup"><span data-stu-id="ed169-241">2D effects</span></span>

<span data-ttu-id="ed169-242">Un subconjunto de funciones en 2D de WPF incluye los efectos visuales, tales como degradados, mapas de bits, dibujos, pintar con vídeos, rotación, escala y sesgado.</span><span class="sxs-lookup"><span data-stu-id="ed169-242">A subset of WPF 2D capabilities includes visual effects, such as gradients, bitmaps, drawings, painting with videos, rotation, scaling, and skewing.</span></span> <span data-ttu-id="ed169-243">Todos ellos se logran con pinceles; la figura siguiente muestra algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="ed169-243">These are all achieved with brushes; the following figure shows some examples:</span></span>

![Ilustración de diferentes pinceles](media/introduction-to-wpf/wpfintrofigure6.png)

<span data-ttu-id="ed169-245">Para obtener más información, vea [Información general sobre pinceles de WPF](graphics-multimedia/wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-245">For more information, see [WPF brushes overview](graphics-multimedia/wpf-brushes-overview.md).</span></span>

### <a name="3d-rendering"></a><span data-ttu-id="ed169-246">Representación en 3D</span><span class="sxs-lookup"><span data-stu-id="ed169-246">3D rendering</span></span>

<span data-ttu-id="ed169-247">WPFWPF también incluye capacidades de representación 3D que se integran con gráficos 2D para permitir la creación de interfaces de usuario más interesantes e interesantes.</span><span class="sxs-lookup"><span data-stu-id="ed169-247">WPF also includes 3D rendering capabilities that integrate with 2D graphics to allow the creation of more exciting and interesting user interfaces.</span></span> <span data-ttu-id="ed169-248">Por ejemplo, la figura siguiente muestra imágenes 2D renderizadas en formas 3D:</span><span class="sxs-lookup"><span data-stu-id="ed169-248">For example, the following figure shows 2D images rendered onto 3D shapes:</span></span>

![Captura de pantalla de ejemplo Visual3D](media/introduction-to-wpf/wpfintrofigure13.png)

<span data-ttu-id="ed169-250">Para obtener más información, vea [Información general sobre gráficos 3D](graphics-multimedia/3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-250">For more information, see [3D graphics overview](graphics-multimedia/3-d-graphics-overview.md).</span></span>

## <a name="animation"></a><span data-ttu-id="ed169-251">Animación</span><span class="sxs-lookup"><span data-stu-id="ed169-251">Animation</span></span>

<span data-ttu-id="ed169-252">El soporte de animación de WPF permite hacer que los controles crezcan, tiemblen, giren o se desvanezcan, crear transiciones de página interesantes y mucho más.</span><span class="sxs-lookup"><span data-stu-id="ed169-252">WPF animation support lets you make controls grow, shake, spin, and fade, to create interesting page transitions, and more.</span></span> <span data-ttu-id="ed169-253">Se puede animar la mayoría de las clases de WPF, incluso las clases personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ed169-253">You can animate most WPF classes, even custom classes.</span></span> <span data-ttu-id="ed169-254">La figura siguiente muestra una animación simple en acción:</span><span class="sxs-lookup"><span data-stu-id="ed169-254">The following figure shows a simple animation in action:</span></span>

![Imágenes de un cubo animado](media/introduction-to-wpf/wpfintrofigure7.png)

<span data-ttu-id="ed169-256">Para obtener más información, vea [Información general sobre animaciones](graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-256">For more information, see [Animation overview](graphics-multimedia/animation-overview.md).</span></span>

## <a name="media"></a><span data-ttu-id="ed169-257">Multimedia</span><span class="sxs-lookup"><span data-stu-id="ed169-257">Media</span></span>

<span data-ttu-id="ed169-258">Una manera de mostrar contenido enriquecido es mediante el uso de medios audiovisuales (multimedia).</span><span class="sxs-lookup"><span data-stu-id="ed169-258">One way to convey rich content is through the use of audiovisual media.</span></span> <span data-ttu-id="ed169-259">WPF proporciona compatibilidad especial con imágenes, vídeo y audio.</span><span class="sxs-lookup"><span data-stu-id="ed169-259">WPF provides special support for images, video, and audio.</span></span>

### <a name="images"></a><span data-ttu-id="ed169-260">Imágenes</span><span class="sxs-lookup"><span data-stu-id="ed169-260">Images</span></span>

<span data-ttu-id="ed169-261">Las imágenes son comunes a la mayoría de las aplicaciones y WPF proporciona varias maneras de usarlas.</span><span class="sxs-lookup"><span data-stu-id="ed169-261">Images are common to most applications, and WPF provides several ways to use them.</span></span> <span data-ttu-id="ed169-262">La siguiente ilustración muestra una interfaz de usuario con un cuadro de lista que contiene imágenes en miniatura.</span><span class="sxs-lookup"><span data-stu-id="ed169-262">The following figure shows a user interface with a list box that contains thumbnail images.</span></span> <span data-ttu-id="ed169-263">Cuando se selecciona una miniatura, aparece la imagen a tamaño completo.</span><span class="sxs-lookup"><span data-stu-id="ed169-263">When a thumbnail is selected, the image is shown full-size.</span></span>

![Imágenes en miniatura e imagen a tamaño completo](media/introduction-to-wpf/wpfintrofigure8.png)

<span data-ttu-id="ed169-265">Para obtener más información, vea [Información general sobre imágenes](graphics-multimedia/imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-265">For more information, see [Imaging overview](graphics-multimedia/imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="ed169-266">Vídeo y audio</span><span class="sxs-lookup"><span data-stu-id="ed169-266">Video and audio</span></span>

<span data-ttu-id="ed169-267">El control <xref:System.Windows.Controls.MediaElement> es capaz de reproducir vídeo y audio, y es lo suficientemente flexible como para ser la base de un reproductor multimedia personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed169-267">The <xref:System.Windows.Controls.MediaElement> control is capable of playing both video and audio, and it is flexible enough to be the basis for a custom media player.</span></span> <span data-ttu-id="ed169-268">El siguiente marcado XAML implementa un reproductor multimedia:</span><span class="sxs-lookup"><span data-stu-id="ed169-268">The following XAML markup implements a media player:</span></span>

[!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_9.xaml)]

<span data-ttu-id="ed169-269">La ventana de la <xref:System.Windows.Controls.MediaElement> figura siguiente muestra el control en acción:</span><span class="sxs-lookup"><span data-stu-id="ed169-269">The window in the following figure shows the <xref:System.Windows.Controls.MediaElement> control in action:</span></span>

![Control MediaElement con audio y vídeo](media/introduction-to-wpf/wpfintrofigure1.png)

<span data-ttu-id="ed169-271">Para obtener más información, vea [Gráficos y multimedia](graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-271">For more information, see [Graphics and multimedia](graphics-multimedia/index.md).</span></span>

## <a name="text-and-typography"></a><span data-ttu-id="ed169-272">Texto y tipografía</span><span class="sxs-lookup"><span data-stu-id="ed169-272">Text and typography</span></span>

<span data-ttu-id="ed169-273">Para facilitar la representación de texto de alta calidad, WPF ofrece las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="ed169-273">To facilitate high-quality text rendering, WPF offers the following features:</span></span>

- <span data-ttu-id="ed169-274">Compatibilidad con fuentes OpenType.</span><span class="sxs-lookup"><span data-stu-id="ed169-274">OpenType font support.</span></span>

- <span data-ttu-id="ed169-275">Mejoras de ClearType.</span><span class="sxs-lookup"><span data-stu-id="ed169-275">ClearType enhancements.</span></span>

- <span data-ttu-id="ed169-276">Alto rendimiento que saca partido de la aceleración de hardware.</span><span class="sxs-lookup"><span data-stu-id="ed169-276">High performance that takes advantage of hardware acceleration.</span></span>

- <span data-ttu-id="ed169-277">Integración de texto con multimedia, gráficos y animación.</span><span class="sxs-lookup"><span data-stu-id="ed169-277">Integration of text with media, graphics, and animation.</span></span>

- <span data-ttu-id="ed169-278">Compatibilidad con fuentes internacionales y mecanismos de reserva.</span><span class="sxs-lookup"><span data-stu-id="ed169-278">International font support and fallback mechanisms.</span></span>

<span data-ttu-id="ed169-279">Como demostración de la integración de texto con gráficos, la siguiente figura muestra la aplicación de decoraciones de texto:</span><span class="sxs-lookup"><span data-stu-id="ed169-279">As a demonstration of text integration with graphics, the following figure shows the application of text decorations:</span></span>

![Texto con diversas decoraciones de texto](media/introduction-to-wpf/wpfintrofigure23.png)

<span data-ttu-id="ed169-281">Para obtener más información, consulte [Tipografía en Windows Presentation Foundation](advanced/typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-281">For more information, see [Typography in Windows Presentation Foundation](advanced/typography-in-wpf.md).</span></span>

## <a name="customize-wpf-apps"></a><span data-ttu-id="ed169-282">Personalización de aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-282">Customize WPF apps</span></span>

<span data-ttu-id="ed169-283">Hasta este punto, hemos estudiado los bloques de creación de WPF fundamentales para desarrollar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ed169-283">Up to this point, you've seen the core WPF building blocks for developing applications.</span></span> <span data-ttu-id="ed169-284">El modelo de aplicación se usa para hospedar y distribuir el contenido de las aplicaciones, que está compuesto principalmente de controles.</span><span class="sxs-lookup"><span data-stu-id="ed169-284">You use the application model to host and deliver application content, which consists mainly of controls.</span></span> <span data-ttu-id="ed169-285">Para simplificar la organización de los controles de una interfaz de usuario y asegurarse de que la organización se conserve aunque se modifiquen el tamaño de la ventana y la configuración de pantalla, se usa el sistema de diseño de WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-285">To simplify the arrangement of controls in a user interface, and to ensure the arrangement is maintained in the face of changes to window size and display settings, you use the WPF layout system.</span></span> <span data-ttu-id="ed169-286">Debido a que la mayoría de las aplicaciones permiten a los usuarios interactuar con los datos, se usa el enlace de datos para reducir el trabajo de la integración de la interfaz de usuario con los datos.</span><span class="sxs-lookup"><span data-stu-id="ed169-286">Because most applications let users interact with data, you use data binding to reduce the work of integrating your user interface with data.</span></span> <span data-ttu-id="ed169-287">Para mejorar la apariencia visual de la aplicación, se usa la amplia gama de gráficos, animación y multimedia compatibilidad que proporciona WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-287">To enhance the visual appearance of your application, you use the comprehensive range of graphics, animation, and media support provided by WPF.</span></span>

<span data-ttu-id="ed169-288">Sin embargo, a menudo los conceptos básicos no bastan para crear y administrar realmente una experiencia del usuario diferenciada y visualmente impactante.</span><span class="sxs-lookup"><span data-stu-id="ed169-288">Often, though, the basics are not enough for creating and managing a truly distinct and visually stunning user experience.</span></span> <span data-ttu-id="ed169-289">Es posible que los controles estándar de WPF no se integren con la apariencia deseada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed169-289">The standard WPF controls might not integrate with the desired appearance of your application.</span></span> <span data-ttu-id="ed169-290">Es posible que los datos no se muestren del modo más eficaz.</span><span class="sxs-lookup"><span data-stu-id="ed169-290">Data might not be displayed in the most effective way.</span></span> <span data-ttu-id="ed169-291">La apariencia y el funcionamiento predeterminados de los temas de Windows pueden no ser adecuados para proporcionar la experiencia global del usuario con respecto a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed169-291">Your application's overall user experience may not be suited to the default look and feel of Windows themes.</span></span> <span data-ttu-id="ed169-292">En muchos aspectos, una tecnología de presentación requiere de extensibilidad visual tanto como cualquier otro tipo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="ed169-292">In many ways, a presentation technology needs visual extensibility as much as any other type of extensibility.</span></span>

<span data-ttu-id="ed169-293">Por este motivo, WPF proporciona una variedad de mecanismos para crear experiencias del usuario únicas, incluido un modelo de contenido enriquecido para los controles, desencadenadores, control y plantillas de datos, estilos, recursos de interfaz de usuario y temas y máscaras.</span><span class="sxs-lookup"><span data-stu-id="ed169-293">For this reason, WPF provides a variety of mechanisms for creating unique user experiences, including a rich content model for controls, triggers, control and data templates, styles, user interface resources, and themes and skins.</span></span>

### <a name="content-model"></a><span data-ttu-id="ed169-294">Modelo de contenido</span><span class="sxs-lookup"><span data-stu-id="ed169-294">Content model</span></span>

<span data-ttu-id="ed169-295">El propósito principal de la mayoría de los controles de WPF es mostrar el contenido.</span><span class="sxs-lookup"><span data-stu-id="ed169-295">The main purpose of a majority of the WPF controls is to display content.</span></span> <span data-ttu-id="ed169-296">En WPF, el tipo y el número de elementos que pueden constituir el contenido de un control se conoce como *modelo de contenido*del control.</span><span class="sxs-lookup"><span data-stu-id="ed169-296">In WPF, the type and number of items that can constitute the content of a control is referred to as the control's *content model*.</span></span> <span data-ttu-id="ed169-297">Algunos controles pueden contener un solo elemento y tipo de contenido. Por ejemplo, el contenido de un control <xref:System.Windows.Controls.TextBox> es un valor de cadena que se asigna a la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> .</span><span class="sxs-lookup"><span data-stu-id="ed169-297">Some controls can contain a single item and type of content; for example, the content of a <xref:System.Windows.Controls.TextBox> is a string value that is assigned to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="ed169-298">En el ejemplo siguiente <xref:System.Windows.Controls.TextBox>se establece el contenido de un :</span><span class="sxs-lookup"><span data-stu-id="ed169-298">The following example sets the content of a <xref:System.Windows.Controls.TextBox>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">

    <TextBox Text="This is the content of a TextBox." />
</Window>
```

<span data-ttu-id="ed169-299">La figura siguiente muestra el resultado:</span><span class="sxs-lookup"><span data-stu-id="ed169-299">The following figure shows the result:</span></span>

![Control TextBox que contiene texto](media/introduction-to-wpf/wpfintrofigure21.png)

<span data-ttu-id="ed169-301">Otros controles, sin embargo, pueden contener varios elementos de diferentes tipos de contenido. El contenido de un control <xref:System.Windows.Controls.Button>, especificado por la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A>, puede contener diversos elementos, incluidos los controles de diseño, texto, imágenes y formas.</span><span class="sxs-lookup"><span data-stu-id="ed169-301">Other controls, however, can contain multiple items of different types of content; the content of a <xref:System.Windows.Controls.Button>, specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property, can contain a variety of items including layout controls, text, images, and shapes.</span></span> <span data-ttu-id="ed169-302">En el ejemplo <xref:System.Windows.Controls.Button> siguiente se <xref:System.Windows.Controls.DockPanel>muestra <xref:System.Windows.Controls.Label>un <xref:System.Windows.Controls.Border>contenido con <xref:System.Windows.Controls.MediaElement>contenido que incluye un , a , a , y un :</span><span class="sxs-lookup"><span data-stu-id="ed169-302">The following example shows a <xref:System.Windows.Controls.Button> with content that includes a <xref:System.Windows.Controls.DockPanel>, a <xref:System.Windows.Controls.Label>, a <xref:System.Windows.Controls.Border>, and a <xref:System.Windows.Controls.MediaElement>:</span></span>

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

<span data-ttu-id="ed169-303">La figura siguiente muestra el contenido de este botón:</span><span class="sxs-lookup"><span data-stu-id="ed169-303">The following figure shows the content of this button:</span></span>

![Botón que tiene varios tipos de contenido](media/introduction-to-wpf/wpfintrofigure22.png)

<span data-ttu-id="ed169-305">Para obtener más información sobre los tipos de contenido admitidos por los diversos controles, vea [Modelo de contenido de WPF](controls/wpf-content-model.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-305">For more information on the kinds of content that is supported by various controls, see [WPF content model](controls/wpf-content-model.md).</span></span>

### <a name="triggers"></a><span data-ttu-id="ed169-306">Desencadenadores</span><span class="sxs-lookup"><span data-stu-id="ed169-306">Triggers</span></span>

<span data-ttu-id="ed169-307">Aunque el propósito principal del marcado XAML es implementar la apariencia de la aplicación, también se puede usar XAML para implementar algunos aspectos del comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed169-307">Although the main purpose of XAML markup is to implement an application's appearance, you can also use XAML to implement some aspects of an application's behavior.</span></span> <span data-ttu-id="ed169-308">Un ejemplo es el uso de desencadenadores para cambiar la apariencia de una aplicación según las interacciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="ed169-308">One example is the use of triggers to change an application's appearance based on user interactions.</span></span> <span data-ttu-id="ed169-309">Para más información, vea [Estilos y plantillas](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-309">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="control-templates"></a><span data-ttu-id="ed169-310">Plantillas de control</span><span class="sxs-lookup"><span data-stu-id="ed169-310">Control templates</span></span>

<span data-ttu-id="ed169-311">Normalmente, las interfaces de usuario predeterminadas para los controles de WPF se construyen a partir de otros controles y formas.</span><span class="sxs-lookup"><span data-stu-id="ed169-311">The default user interfaces for WPF controls are typically constructed from other controls and shapes.</span></span> <span data-ttu-id="ed169-312">Por ejemplo, un control <xref:System.Windows.Controls.Button> está compuesto por los controles <xref:Microsoft.Windows.Themes.ButtonChrome> y <xref:System.Windows.Controls.ContentPresenter> .</span><span class="sxs-lookup"><span data-stu-id="ed169-312">For example, a <xref:System.Windows.Controls.Button> is composed of both <xref:Microsoft.Windows.Themes.ButtonChrome> and <xref:System.Windows.Controls.ContentPresenter> controls.</span></span> <span data-ttu-id="ed169-313"><xref:Microsoft.Windows.Themes.ButtonChrome> proporciona la apariencia del botón estándar, mientras que <xref:System.Windows.Controls.ContentPresenter> muestra el contenido del botón, según lo especificado por la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> .</span><span class="sxs-lookup"><span data-stu-id="ed169-313">The <xref:Microsoft.Windows.Themes.ButtonChrome> provides the standard button appearance, while the <xref:System.Windows.Controls.ContentPresenter> displays the button's content, as specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property.</span></span>

<span data-ttu-id="ed169-314">A veces, la apariencia predeterminada de un control puede ser incongruente con la apariencia general de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed169-314">Sometimes the default appearance of a control may be incongruent with the overall appearance of an application.</span></span> <span data-ttu-id="ed169-315">En este caso, se puede usar un control <xref:System.Windows.Controls.ControlTemplate> para cambiar la apariencia de la interfaz de usuario del control sin modificar su contenido ni su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ed169-315">In this case, you can use a <xref:System.Windows.Controls.ControlTemplate> to change the appearance of the control's user interface without changing its content and behavior.</span></span>

<span data-ttu-id="ed169-316">En el ejemplo siguiente se muestra <xref:System.Windows.Controls.Button> cómo <xref:System.Windows.Controls.ControlTemplate>cambiar la apariencia de a mediante un :</span><span class="sxs-lookup"><span data-stu-id="ed169-316">The following example shows how to change the appearance of a <xref:System.Windows.Controls.Button> by using a <xref:System.Windows.Controls.ControlTemplate>:</span></span>

[!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_16.xaml)]

[!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_17.cs)]
[!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_17.vb)]

<span data-ttu-id="ed169-317">En este ejemplo, la interfaz de usuario del botón predeterminado se ha reemplazado por una forma <xref:System.Windows.Shapes.Ellipse> que tiene un borde azul marino y se rellena mediante <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="ed169-317">In this example, the default button user interface has been replaced with an <xref:System.Windows.Shapes.Ellipse> that has a dark blue border and is filled using a <xref:System.Windows.Media.RadialGradientBrush>.</span></span> <span data-ttu-id="ed169-318">El control <xref:System.Windows.Controls.ContentPresenter> muestra el contenido de <xref:System.Windows.Controls.Button>, "Click Me!".</span><span class="sxs-lookup"><span data-stu-id="ed169-318">The <xref:System.Windows.Controls.ContentPresenter> control displays the content of the <xref:System.Windows.Controls.Button>, "Click Me!"</span></span> <span data-ttu-id="ed169-319">Cuando se hace clic en <xref:System.Windows.Controls.Button> , el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> todavía se provoca como parte del comportamiento predeterminado del control <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="ed169-319">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event is still raised as part of the <xref:System.Windows.Controls.Button> control's default behavior.</span></span> <span data-ttu-id="ed169-320">El resultado se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed169-320">The result is shown in the following figure:</span></span>

![Botón elíptico y una segunda ventana](media/introduction-to-wpf/wpfintrofigure2.png)

### <a name="data-templates"></a><span data-ttu-id="ed169-322">Plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="ed169-322">Data templates</span></span>

<span data-ttu-id="ed169-323">Mientras que una plantilla de control permite especificar la apariencia de un control, una plantilla de datos permite especificar la apariencia del contenido del control.</span><span class="sxs-lookup"><span data-stu-id="ed169-323">Whereas a control template lets you specify the appearance of a control, a data template lets you specify the appearance of a control's content.</span></span> <span data-ttu-id="ed169-324">Las plantillas de datos se usan con frecuencia para mejorar la manera de mostrar los datos enlazados.</span><span class="sxs-lookup"><span data-stu-id="ed169-324">Data templates are frequently used to enhance how bound data is displayed.</span></span> <span data-ttu-id="ed169-325">La figura siguiente muestra la <xref:System.Windows.Controls.ListBox> apariencia predeterminada de `Task` un que está enlazado a una colección de objetos, donde cada tarea tiene un nombre, una descripción y una prioridad:</span><span class="sxs-lookup"><span data-stu-id="ed169-325">The following figure shows the default appearance for a <xref:System.Windows.Controls.ListBox> that is bound to a collection of `Task` objects, where each task has a name, description, and priority:</span></span>

![Cuadro de lista con el aspecto predeterminado](media/introduction-to-wpf/wpfintrofigure18.png)

<span data-ttu-id="ed169-327">La apariencia predeterminada es la que cabría esperar de un control <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="ed169-327">The default appearance is what you would expect from a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="ed169-328">Sin embargo, la apariencia predeterminada de cada tarea contiene únicamente el nombre de tarea.</span><span class="sxs-lookup"><span data-stu-id="ed169-328">However, the default appearance of each task contains only the task name.</span></span> <span data-ttu-id="ed169-329">Para mostrar el nombre de la tarea, la descripción y la prioridad, la apariencia predeterminada de los elementos de lista enlazados al control <xref:System.Windows.Controls.ListBox> se debe modificar mediante una plantilla de datos <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="ed169-329">To show the task name, description, and priority, the default appearance of the <xref:System.Windows.Controls.ListBox> control's bound list items must be changed by using a <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="ed169-330">El XAML siguiente <xref:System.Windows.DataTemplate>define un valor de este <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> tipo , que se aplica a cada tarea mediante el atributo:</span><span class="sxs-lookup"><span data-stu-id="ed169-330">The following XAML defines such a <xref:System.Windows.DataTemplate>, which is applied to each task by using the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> attribute:</span></span>

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

<span data-ttu-id="ed169-331">La figura siguiente muestra el efecto de este código:</span><span class="sxs-lookup"><span data-stu-id="ed169-331">The following figure shows the effect of this code:</span></span>

![Cuadro de lista que usa una plantilla de datos](media/introduction-to-wpf/wpfintrofigure19.png)

<span data-ttu-id="ed169-333">Observe que el control <xref:System.Windows.Controls.ListBox> conserva su comportamiento y apariencia general; sólo se modificó la apariencia del contenido mostrado por el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="ed169-333">Note that the <xref:System.Windows.Controls.ListBox> has retained its behavior and overall appearance; only the appearance of the content being displayed by the list box has changed.</span></span>

<span data-ttu-id="ed169-334">Para obtener más información, vea [Información general sobre plantillas de datos](data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-334">For more information, see [Data templating overview](data/data-templating-overview.md).</span></span>

### <a name="styles"></a><span data-ttu-id="ed169-335">Estilos</span><span class="sxs-lookup"><span data-stu-id="ed169-335">Styles</span></span>

<span data-ttu-id="ed169-336">Los estilos permiten que los desarrolladores y diseñadores estandaricen un aspecto determinado de su producto.</span><span class="sxs-lookup"><span data-stu-id="ed169-336">Styles enable developers and designers to standardize on a particular appearance for their product.</span></span> <span data-ttu-id="ed169-337">WPF proporciona un modelo de estilo eficaz, cuya base es el elemento <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="ed169-337">WPF provides a strong style model, the foundation of which is the <xref:System.Windows.Style> element.</span></span> <span data-ttu-id="ed169-338">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Button> estilo que `Orange`establece el color de fondo para cada ventana en:</span><span class="sxs-lookup"><span data-stu-id="ed169-338">The following example creates a style that sets the background color for every <xref:System.Windows.Controls.Button> on a window to `Orange`:</span></span>

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

<span data-ttu-id="ed169-339">Dado que este estilo tiene como destino todos los controles <xref:System.Windows.Controls.Button>, se aplica automáticamente a todos los botones de la ventana, tal como se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed169-339">Because this style targets all <xref:System.Windows.Controls.Button> controls, the style is automatically applied to all the buttons in the window, as shown in the following figure:</span></span>

![Dos botones de color naranja](media/introduction-to-wpf/wpfintrofigure20.png)

<span data-ttu-id="ed169-341">Para más información, vea [Estilos y plantillas](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-341">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="resources"></a><span data-ttu-id="ed169-342">Recursos</span><span class="sxs-lookup"><span data-stu-id="ed169-342">Resources</span></span>

<span data-ttu-id="ed169-343">Los controles de una aplicación deben compartir la misma apariencia, que puede incluir todo tipo de recursos, desde fuentes y colores de fondo hasta plantillas de control, plantillas de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="ed169-343">Controls in an application should share the same appearance, which can include anything from fonts and background colors to control templates, data templates, and styles.</span></span> <span data-ttu-id="ed169-344">Se puede usar la compatibilidad de WPF con los recursos de la interfaz de usuario para encapsular estos recursos en una ubicación única y poder reutilizarlos.</span><span class="sxs-lookup"><span data-stu-id="ed169-344">You can use WPF's support for user interface resources to encapsulate these resources in a single location for reuse.</span></span>

<span data-ttu-id="ed169-345">En el ejemplo siguiente se define un <xref:System.Windows.Controls.Button> color <xref:System.Windows.Controls.Label>de fondo común que es compartido por a y a:</span><span class="sxs-lookup"><span data-stu-id="ed169-345">The following example defines a common background color that is shared by a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.Label>:</span></span>

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

<span data-ttu-id="ed169-346">En este ejemplo se implementa un recurso de color de fondo mediante el elemento de propiedad `Window.Resources` .</span><span class="sxs-lookup"><span data-stu-id="ed169-346">This example implements a background color resource by using the `Window.Resources` property element.</span></span> <span data-ttu-id="ed169-347">Este recurso está disponible para todos los elementos secundarios de <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="ed169-347">This resource is available to all children of the <xref:System.Windows.Window>.</span></span> <span data-ttu-id="ed169-348">Hay una gran variedad de ámbitos de recursos, incluidos los siguientes, que se muestran en el orden en que se resuelven:</span><span class="sxs-lookup"><span data-stu-id="ed169-348">There are a variety of resource scopes, including the following, listed in the order in which they are resolved:</span></span>

1. <span data-ttu-id="ed169-349">Un control individual (mediante la propiedad <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> heredada).</span><span class="sxs-lookup"><span data-stu-id="ed169-349">An individual control (using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

2. <span data-ttu-id="ed169-350"><xref:System.Windows.Window> o <xref:System.Windows.Controls.Page> (también mediante la propiedad <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> heredada).</span><span class="sxs-lookup"><span data-stu-id="ed169-350">A <xref:System.Windows.Window> or a <xref:System.Windows.Controls.Page> (also using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

3. <span data-ttu-id="ed169-351"><xref:System.Windows.Application> (mediante la propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="ed169-351">An <xref:System.Windows.Application> (using the <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> property).</span></span>

<span data-ttu-id="ed169-352">La variedad de ámbitos aporta flexibilidad al desarrollador con respecto a la manera de definir y compartir los recursos.</span><span class="sxs-lookup"><span data-stu-id="ed169-352">The variety of scopes gives you flexibility with respect to the way in which you define and share your resources.</span></span>

<span data-ttu-id="ed169-353">Como alternativa para asociar directamente los recursos a un ámbito determinado, se puede empaquetar uno o varios recursos mediante un <xref:System.Windows.ResourceDictionary> independiente al que puede hacer referencia en otras partes de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed169-353">As an alternative to directly associating your resources with a particular scope, you can package one or more resources by using a separate <xref:System.Windows.ResourceDictionary> that can be referenced in other parts of an application.</span></span> <span data-ttu-id="ed169-354">Por ejemplo, en el ejemplo siguiente se define un color de fondo predeterminado en un diccionario de recursos:</span><span class="sxs-lookup"><span data-stu-id="ed169-354">For example, the following example defines a default background color in a resource dictionary:</span></span>

```xaml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```

<span data-ttu-id="ed169-355">En el ejemplo siguiente se hace referencia al diccionario de recursos definido en el ejemplo anterior para que se comparta entre una aplicación:</span><span class="sxs-lookup"><span data-stu-id="ed169-355">The following example references the resource dictionary defined in the previous example so that it is shared across an application:</span></span>

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

<span data-ttu-id="ed169-356">Los recursos y los diccionarios de recursos constituyen la base de la compatibilidad de WPF con los temas y las máscaras.</span><span class="sxs-lookup"><span data-stu-id="ed169-356">Resources and resource dictionaries are the foundation of WPF support for themes and skins.</span></span>

<span data-ttu-id="ed169-357">Para obtener más información, consulte [Recursos](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-357">For more information, see [Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="custom-controls"></a><span data-ttu-id="ed169-358">Controles personalizados</span><span class="sxs-lookup"><span data-stu-id="ed169-358">Custom controls</span></span>

<span data-ttu-id="ed169-359">Aunque WPF proporciona una amplísima compatibilidad con funciones de personalización, puede encontrar situaciones en que los controles existentes de WPF no satisfagan las necesidades de la aplicación o de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed169-359">Although WPF provides a host of customization support, you may encounter situations where existing WPF controls do not meet the needs of either your application or its users.</span></span> <span data-ttu-id="ed169-360">Esto puede suceder si:</span><span class="sxs-lookup"><span data-stu-id="ed169-360">This can occur when:</span></span>

- <span data-ttu-id="ed169-361">La UI que se necesita no puede crearse personalizando la apariencia y el funcionamiento de las implementaciones de WPF existentes.</span><span class="sxs-lookup"><span data-stu-id="ed169-361">The user interface that you require cannot be created by customizing the look and feel of existing WPF implementations.</span></span>

- <span data-ttu-id="ed169-362">Las implementaciones de WPF existentes no admiten el comportamiento que se necesita (o lo admiten, pero no fácilmente).</span><span class="sxs-lookup"><span data-stu-id="ed169-362">The behavior that you require is not supported (or not easily supported) by existing WPF implementations.</span></span>

<span data-ttu-id="ed169-363">Sin embargo, en este punto puede sacar partido de uno de los tres modelos de WPF para crear un nuevo control.</span><span class="sxs-lookup"><span data-stu-id="ed169-363">At this point, however, you can take advantage of one of three WPF models to create a new control.</span></span> <span data-ttu-id="ed169-364">Cada modelo está destinado a un escenario concreto y necesita que el control personalizado se derive de una clase base de WPF determinada.</span><span class="sxs-lookup"><span data-stu-id="ed169-364">Each model targets a specific scenario and requires your custom control to derive from a particular WPF base class.</span></span> <span data-ttu-id="ed169-365">A continuación se muestran los tres modelos:</span><span class="sxs-lookup"><span data-stu-id="ed169-365">The three models are listed here:</span></span>

- <span data-ttu-id="ed169-366">**Modelo de control de usuario**.</span><span class="sxs-lookup"><span data-stu-id="ed169-366">**User Control Model**.</span></span> <span data-ttu-id="ed169-367">El control personalizado se deriva de <xref:System.Windows.Controls.UserControl> y se crea a partir de uno o varios controles.</span><span class="sxs-lookup"><span data-stu-id="ed169-367">A custom control derives from <xref:System.Windows.Controls.UserControl> and is composed of one or more other controls.</span></span>

- <span data-ttu-id="ed169-368">**Modelo de control**.</span><span class="sxs-lookup"><span data-stu-id="ed169-368">**Control Model**.</span></span> <span data-ttu-id="ed169-369">El control personalizado se deriva de <xref:System.Windows.Controls.Control> y se usa para crear implementaciones que separan su comportamiento de su apariencia mediante plantillas, de un modo muy similar a la mayoría de los controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-369">A custom control derives from <xref:System.Windows.Controls.Control> and is used to build implementations that separate their behavior from their appearance using templates, much like the majority of WPF controls.</span></span> <span data-ttu-id="ed169-370">Al derivarse de <xref:System.Windows.Controls.Control> , permite mayor libertad para la creación de una UI personalizada que los controles de usuario, pero puede requerir más esfuerzo.</span><span class="sxs-lookup"><span data-stu-id="ed169-370">Deriving from <xref:System.Windows.Controls.Control> allows you more freedom for creating a custom user interface than user controls, but it may require more effort.</span></span>

- <span data-ttu-id="ed169-371">**Modelo de elemento de marco de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ed169-371">**Framework Element Model**.</span></span> <span data-ttu-id="ed169-372">Un control personalizado se deriva de <xref:System.Windows.FrameworkElement> cuando su apariencia se define mediante la lógica de representación personalizada (no mediante plantillas).</span><span class="sxs-lookup"><span data-stu-id="ed169-372">A custom control derives from <xref:System.Windows.FrameworkElement> when its appearance is defined by custom rendering logic (not templates).</span></span>

<span data-ttu-id="ed169-373">En el ejemplo siguiente se muestra un control <xref:System.Windows.Controls.UserControl>numérico personalizado arriba/abajo que deriva de:</span><span class="sxs-lookup"><span data-stu-id="ed169-373">The following example shows a custom numeric up/down control that derives from <xref:System.Windows.Controls.UserControl>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_33.xaml)]

[!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_34.cs)]
[!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_34.vb)]

<span data-ttu-id="ed169-374">En el ejemplo siguiente se muestra el XAML necesario <xref:System.Windows.Window>para incorporar el control de usuario en:</span><span class="sxs-lookup"><span data-stu-id="ed169-374">The following example illustrates the XAML that is required to incorporate the user control into a <xref:System.Windows.Window>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_37.xaml)]

<span data-ttu-id="ed169-375">La figura siguiente `NumericUpDown` muestra el <xref:System.Windows.Window>control hospedado en:</span><span class="sxs-lookup"><span data-stu-id="ed169-375">The following figure shows the `NumericUpDown` control hosted in a <xref:System.Windows.Window>:</span></span>

![UserControl personalizado](media/introduction-to-wpf/wpfintrofigure3.png)

<span data-ttu-id="ed169-377">Para obtener más información sobre los controles personalizados, vea [Información general sobre la creación de controles](controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ed169-377">For more information on custom controls, see [Control authoring overview](controls/control-authoring-overview.md).</span></span>

## <a name="wpf-best-practices"></a><span data-ttu-id="ed169-378">Procedimientos recomendados en WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-378">WPF best practices</span></span>

<span data-ttu-id="ed169-379">Como sucede con cualquier plataforma de desarrollo, WPF se puede usar de diversas maneras para lograr el resultado deseado.</span><span class="sxs-lookup"><span data-stu-id="ed169-379">As with any development platform, WPF can be used in a variety of ways to achieve the desired result.</span></span> <span data-ttu-id="ed169-380">Para asegurarse de que las aplicaciones de WPF proporcionen la experiencia del usuario necesaria y satisfagan las exigencias del público en general, existen procedimientos recomendados de accesibilidad, globalización y localización, y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ed169-380">As a way of ensuring that your WPF applications provide the required user experience and meet the demands of the audience in general, there are recommended best practices for accessibility, globalization and localization, and performance.</span></span> <span data-ttu-id="ed169-381">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ed169-381">For more information, see:</span></span>

- [<span data-ttu-id="ed169-382">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="ed169-382">Accessibility</span></span>](../ui-automation/accessibility-best-practices.md)
- [<span data-ttu-id="ed169-383">Globalización y localización de WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-383">WPF globalization and localization</span></span>](advanced/wpf-globalization-and-localization-overview.md)
- [<span data-ttu-id="ed169-384">Rendimiento de aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-384">WPF app performance</span></span>](advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="ed169-385">Seguridad de WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-385">WPF security</span></span>](security-wpf.md)

## <a name="next-steps"></a><span data-ttu-id="ed169-386">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ed169-386">Next steps</span></span>

<span data-ttu-id="ed169-387">Hemos analizado las principales características de WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-387">We've looked at the key features of WPF.</span></span> <span data-ttu-id="ed169-388">Ahora es el momento de que compile su primera aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="ed169-388">Now it's time to build your first WPF app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ed169-389">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-389">Walkthrough: My first WPF desktop app</span></span>](getting-started/walkthrough-my-first-wpf-desktop-application.md)

## <a name="see-also"></a><span data-ttu-id="ed169-390">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed169-390">See also</span></span>

- [<span data-ttu-id="ed169-391">Introducción a WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-391">Get started with WPF</span></span>](getting-started/index.md)
- [<span data-ttu-id="ed169-392">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="ed169-392">Windows Presentation Foundation</span></span>](index.md)
- [<span data-ttu-id="ed169-393">Recursos comunitarios de WPF</span><span class="sxs-lookup"><span data-stu-id="ed169-393">WPF community resources</span></span>](getting-started/community-feedback.md)
