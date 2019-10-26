---
title: Código fuente de L2DBForm.xaml
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 290b00e136f0c49e1b27d4fa1bca7321eebe936e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921231"
---
# <a name="l2dbformxaml-source-code"></a><span data-ttu-id="2560f-102">Código fuente de L2DBForm.xaml</span><span class="sxs-lookup"><span data-stu-id="2560f-102">L2DBForm.xaml source code</span></span>

<span data-ttu-id="2560f-103">Esta página contiene y describe el archivo de origen XAML para el [enlace de datos de WPF mediante LINQ to XML ejemplo](linq-to-xml-data-binding-sample.md).</span><span class="sxs-lookup"><span data-stu-id="2560f-103">This page contains and describes the XAML source file for the [WPF data binding using LINQ to XML example](linq-to-xml-data-binding-sample.md).</span></span>

## <a name="overall-ui-structure"></a><span data-ttu-id="2560f-104">Estructura de IU general</span><span class="sxs-lookup"><span data-stu-id="2560f-104">Overall UI structure</span></span>

<span data-ttu-id="2560f-105">Como es típico para un proyecto de WPF, este archivo contiene un elemento primario, un <xref:System.Windows.Window> elemento XML asociado a la clase derivada `L2XDBFrom` en el espacio de nombres `LinqToXmlDataBinding`.</span><span class="sxs-lookup"><span data-stu-id="2560f-105">As is typical for a WPF project, this file contains one parent element, a <xref:System.Windows.Window> XML element that's associated with the derived class `L2XDBFrom` in the `LinqToXmlDataBinding` namespace.</span></span>

<span data-ttu-id="2560f-106">El área cliente se encuentra dentro de un <xref:System.Windows.Controls.StackPanel> que tiene un fondo azul claro.</span><span class="sxs-lookup"><span data-stu-id="2560f-106">The client area is contained within a <xref:System.Windows.Controls.StackPanel> that's given a light blue background.</span></span> <span data-ttu-id="2560f-107">Este panel contiene cuatro secciones de IU <xref:System.Windows.Controls.DockPanel> separadas por barras <xref:System.Windows.Controls.Separator> .</span><span class="sxs-lookup"><span data-stu-id="2560f-107">This panel contains four <xref:System.Windows.Controls.DockPanel> UI sections separated by <xref:System.Windows.Controls.Separator> bars.</span></span> <span data-ttu-id="2560f-108">El propósito de estas secciones se describe [aquí](linq-to-xml-data-binding-sample.md#overview).</span><span class="sxs-lookup"><span data-stu-id="2560f-108">The purpose of these sections is described [here](linq-to-xml-data-binding-sample.md#overview).</span></span>

<span data-ttu-id="2560f-109">Cada sección contiene una etiqueta que la identifica.</span><span class="sxs-lookup"><span data-stu-id="2560f-109">Each section contains a label that identifies it.</span></span> <span data-ttu-id="2560f-110">En las primeras dos secciones, esta etiqueta se gira 90 grados mediante <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span><span class="sxs-lookup"><span data-stu-id="2560f-110">In the first two sections, this label is rotated 90 degrees through the use of a <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span></span> <span data-ttu-id="2560f-111">El resto de la sección contiene elementos de interfaz de usuario adecuados para la finalidad de esa sección, por ejemplo, bloques de texto, cuadros de texto y botones.</span><span class="sxs-lookup"><span data-stu-id="2560f-111">The rest of the section contains UI elements appropriate to the purpose of that section, for example, text blocks, text boxes, and buttons.</span></span> <span data-ttu-id="2560f-112">A veces se utiliza un <xref:System.Windows.Controls.StackPanel> secundario para alinear esos controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="2560f-112">Sometimes a child <xref:System.Windows.Controls.StackPanel> is used to align these child controls.</span></span>

## <a name="window-resource-section"></a><span data-ttu-id="2560f-113">Sección de recursos de la ventana</span><span class="sxs-lookup"><span data-stu-id="2560f-113">Window resource section</span></span>

<span data-ttu-id="2560f-114">La etiqueta de apertura `<Window.Resources>` de la línea 9 indica el inicio de la sección de recursos de la ventana.</span><span class="sxs-lookup"><span data-stu-id="2560f-114">The opening `<Window.Resources>` tag on line 9 indicates the start of the window resource section.</span></span> <span data-ttu-id="2560f-115">Acaba con la etiqueta de cierre de la línea 35.</span><span class="sxs-lookup"><span data-stu-id="2560f-115">It ends with the closing tag on line 35.</span></span>

<span data-ttu-id="2560f-116">La etiqueta `<ObjectDataProvider>` que se extiende por las líneas 11 a 25, declara un <xref:System.Windows.Data.ObjectDataProvider>, con el nombre `LoadedBooks`, que utiliza <xref:System.Xml.Linq.XElement> como el origen.</span><span class="sxs-lookup"><span data-stu-id="2560f-116">The `<ObjectDataProvider>` tag, which spans lines 11 through 25, declares a <xref:System.Windows.Data.ObjectDataProvider>, named `LoadedBooks`, that uses an <xref:System.Xml.Linq.XElement> as the source.</span></span> <span data-ttu-id="2560f-117">Este <xref:System.Xml.Linq.XElement> se inicializa analizando un documento XML insertado (un elemento `CDATA`).</span><span class="sxs-lookup"><span data-stu-id="2560f-117">The <xref:System.Xml.Linq.XElement> is initialized by parsing an embedded XML document (a `CDATA` element).</span></span> <span data-ttu-id="2560f-118">Observe que se conserva el espacio en blanco al declarar el documento XML incrustado y también cuando se analiza.</span><span class="sxs-lookup"><span data-stu-id="2560f-118">Notice that white space is preserved when declaring the embedded XML document and also when it's parsed.</span></span> <span data-ttu-id="2560f-119">El espacio en blanco se conserva porque el control <xref:System.Windows.Controls.TextBlock>, que se utiliza para visualizar XML sin formato, no tiene capacidades de formato XML especiales.</span><span class="sxs-lookup"><span data-stu-id="2560f-119">White space is preserved because the <xref:System.Windows.Controls.TextBlock> control, which is used to display the raw XML, has no special XML formatting capabilities.</span></span>

<span data-ttu-id="2560f-120">Por último, u <xref:System.Windows.DataTemplate> con el nombre `BookTemplate` se define en las líneas 28 a 34.</span><span class="sxs-lookup"><span data-stu-id="2560f-120">Lastly, a <xref:System.Windows.DataTemplate> named `BookTemplate` is defined on lines 28 through 34.</span></span> <span data-ttu-id="2560f-121">Esta plantilla se utiliza para mostrar las entradas de la sección **Lista de libros**.</span><span class="sxs-lookup"><span data-stu-id="2560f-121">This template is used to display the entries in the **Book List** UI section.</span></span> <span data-ttu-id="2560f-122">Utiliza el enlace de datos y las propiedades dinámicas de LINQ to XML para recuperar el Id. y el nombre de libro a través de las siguientes asignaciones:</span><span class="sxs-lookup"><span data-stu-id="2560f-122">It uses data binding and LINQ to XML dynamic properties to retrieve the book ID and book name through the following assignments:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a><span data-ttu-id="2560f-123">Código de enlace de datos</span><span class="sxs-lookup"><span data-stu-id="2560f-123">Data binding code</span></span>

<span data-ttu-id="2560f-124">Además del elemento <xref:System.Windows.DataTemplate> , se utiliza el enlace datos en otros sitios de este archivo.</span><span class="sxs-lookup"><span data-stu-id="2560f-124">In addition to the <xref:System.Windows.DataTemplate> element, data binding is used in a number of other places in this file.</span></span>

<span data-ttu-id="2560f-125">En la etiqueta de apertura `<StackPanel>` de la línea 38, la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de este panel se establece en el proveedor de datos `LoadedBooks` .</span><span class="sxs-lookup"><span data-stu-id="2560f-125">In the opening `<StackPanel>` tag on line 38, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of this panel is set to the `LoadedBooks` data provider.</span></span>

```xaml
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

<span data-ttu-id="2560f-126">Establecer el contexto de datos posibilita (en la línea 46) que el <xref:System.Windows.Controls.TextBlock> con el nombre `tbRawXml` muestre el XML sin formato enlazando con la propiedad `Xml` de este proveedor de datos:</span><span class="sxs-lookup"><span data-stu-id="2560f-126">Setting the data context makes it possible (on line 46) for the <xref:System.Windows.Controls.TextBlock> named `tbRawXml` to display the raw XML by binding to this data provider's `Xml` property:</span></span>

```xaml
Text="{Binding Path=Xml}"
```

<span data-ttu-id="2560f-127"><xref:System.Windows.Controls.ListBox> en la sección de IU **Lista de libros** , en las líneas 58 a 62, establece la plantilla para sus elementos de visualización en la `BookTemplate` definida en la sección de recursos de la ventana:</span><span class="sxs-lookup"><span data-stu-id="2560f-127">The <xref:System.Windows.Controls.ListBox> in the **Book List** UI section, on lines 58 through 62, sets the template for its display items to the `BookTemplate` defined in the window resource section:</span></span>

```xaml
ItemTemplate ="{StaticResource BookTemplate}"
```

<span data-ttu-id="2560f-128">A continuación, en las líneas 59 a 62, los valores reales de los libros se enlazan con este cuadro de lista:</span><span class="sxs-lookup"><span data-stu-id="2560f-128">Then, on lines 59 through 62, the actual values of the books are bound to this list box:</span></span>

```xaml
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

<span data-ttu-id="2560f-129">La tercera sección de IU, **Editar el libro seleccionado**, primero enlaza el <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.StackPanel> primario con el elemento seleccionado actualmente de la sección de IU **Lista de libros** (línea 82):</span><span class="sxs-lookup"><span data-stu-id="2560f-129">The third UI section, **Edit Selected Book**, first binds the <xref:System.Windows.FrameworkElement.DataContext%2A> of the parent <xref:System.Windows.Controls.StackPanel> to the currently selected item in from the **Book List** UI section (line 82):</span></span>

```xaml
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

<span data-ttu-id="2560f-130">A continuación usa el enlace de datos bidireccional, de forma que los valores actuales de los elementos del libro se muestran y se actualizan desde los dos cuadros de texto de este panel.</span><span class="sxs-lookup"><span data-stu-id="2560f-130">It then uses two-way data binding, so that the current values of the book elements are displayed to, and updated from, the two text boxes in this panel.</span></span> <span data-ttu-id="2560f-131">El enlace de datos con propiedades dinámicas es similar al utilizado en la plantilla de datos `BookTemplate` :</span><span class="sxs-lookup"><span data-stu-id="2560f-131">Data binding to dynamic properties is similar to the data binding used in the `BookTemplate` data template:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

<span data-ttu-id="2560f-132">La última sección de la interfaz de usuario, **Agregar nuevo libro**, no utiliza el enlace de datos en su código XAML.</span><span class="sxs-lookup"><span data-stu-id="2560f-132">The last UI section, **Add New Book**, doesn't use data binding in its XAML code.</span></span> <span data-ttu-id="2560f-133">En su lugar, el enlace de datos está en su código de control de eventos en el archivo *L2DBForm.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="2560f-133">Instead, data binding is in its event handling code in the file *L2DBForm.xaml.cs*.</span></span>

## <a name="example"></a><span data-ttu-id="2560f-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2560f-134">Example</span></span>

### <a name="description"></a><span data-ttu-id="2560f-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="2560f-135">Description</span></span>

> [!NOTE]
> <span data-ttu-id="2560f-136">Se recomienda copiar el código siguiente en un editor de código, como el editor de código fuente de C# de Visual Studio, de forma que sea más sencillo realizar un seguimiento de los números de línea.</span><span class="sxs-lookup"><span data-stu-id="2560f-136">We recommend that you copy the following code below into a code editor, such as the C# source code editor in Visual Studio, so that line numbers will be easier to track.</span></span>

### <a name="code"></a><span data-ttu-id="2560f-137">Código</span><span class="sxs-lookup"><span data-stu-id="2560f-137">Code</span></span>

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>
```

### <a name="comments"></a><span data-ttu-id="2560f-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2560f-138">Comments</span></span>

<span data-ttu-id="2560f-139">Para conocer el código fuente de C# de los controladores de eventos asociados con los elementos de IU de WPF, vea [Código de origen de L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="2560f-139">For the C# source code for the event handlers associated with the WPF UI elements, see [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2560f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="2560f-140">See also</span></span>

- [<span data-ttu-id="2560f-141">Tutorial: Ejemplo de LinqToXmlDataBinding</span><span class="sxs-lookup"><span data-stu-id="2560f-141">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="2560f-142">Código fuente de L2DBForm.xaml.cs</span><span class="sxs-lookup"><span data-stu-id="2560f-142">L2DBForm.xaml.cs source code</span></span>](l2dbform-xaml-cs-source-code.md)
