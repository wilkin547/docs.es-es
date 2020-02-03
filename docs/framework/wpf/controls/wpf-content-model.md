---
title: Modelo de contenido
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: a84ab2e66b4e373591fc9365b1c17d0bb0c66713
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738283"
---
# <a name="wpf-content-model"></a><span data-ttu-id="203dc-102">Modelo de contenido de WPF</span><span class="sxs-lookup"><span data-stu-id="203dc-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="203dc-103">es una plataforma de presentación que proporciona muchos controles y tipos semejantes a controles cuyo propósito principal es mostrar diferentes tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="203dc-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="203dc-104">Para determinar qué control usar o de qué control derivar, debe entender los tipos de objetos que un control determinado puede mostrar mejor.</span><span class="sxs-lookup"><span data-stu-id="203dc-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="203dc-105">En este tema se resume el modelo de contenido para controles y tipos semejantes a controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="203dc-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="203dc-106">El modelo de contenido describe el contenido que se puede utilizar en un control.</span><span class="sxs-lookup"><span data-stu-id="203dc-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="203dc-107">En este tema también se incluyen las propiedades de contenido para cada modelo de contenido.</span><span class="sxs-lookup"><span data-stu-id="203dc-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="203dc-108">Una propiedad de contenido es aquella que se utiliza para almacenar el contenido del objeto.</span><span class="sxs-lookup"><span data-stu-id="203dc-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="203dc-109">Clases que incluyen contenido arbitrario</span><span class="sxs-lookup"><span data-stu-id="203dc-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="203dc-110">Algunos controles pueden contener un objeto de cualquier tipo, como una cadena, un objeto <xref:System.DateTime> o un <xref:System.Windows.UIElement> que sea un contenedor para elementos adicionales.</span><span class="sxs-lookup"><span data-stu-id="203dc-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="203dc-111">Por ejemplo, un <xref:System.Windows.Controls.Button> puede contener una imagen y texto. o un <xref:System.Windows.Controls.CheckBox> puede contener el valor de <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="203dc-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="203dc-112">tiene cuatro clases que pueden incluir contenido arbitrario.</span><span class="sxs-lookup"><span data-stu-id="203dc-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="203dc-113">En la tabla siguiente se enumeran las clases, que heredan de <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="203dc-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="203dc-114">Clase que incluye contenido arbitrario</span><span class="sxs-lookup"><span data-stu-id="203dc-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="203dc-115">Contenido</span><span class="sxs-lookup"><span data-stu-id="203dc-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="203dc-116">Un único objeto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="203dc-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="203dc-117">Un encabezado y un único elemento; ambos son objetos arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="203dc-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="203dc-118">Una colección de objetos arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="203dc-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="203dc-119">Un encabezado y una colección de elementos; todos ellos son objetos arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="203dc-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="203dc-120">Los controles que heredan de estas clases pueden incluir el mismo tipo de contenido y tratarlo de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="203dc-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="203dc-121">En la ilustración siguiente se muestra un control de cada modelo de contenido que contiene una imagen y texto:</span><span class="sxs-lookup"><span data-stu-id="203dc-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![Captura de pantalla que muestra cuatro controles distintos, uno de cada modelo de contenido.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="203dc-123">Controles que incluyen un único objeto arbitrario</span><span class="sxs-lookup"><span data-stu-id="203dc-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="203dc-124">La clase <xref:System.Windows.Controls.ContentControl> contiene una sola parte de contenido arbitrario.</span><span class="sxs-lookup"><span data-stu-id="203dc-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="203dc-125">Su propiedad de contenido es <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="203dc-126">Los siguientes controles heredan de <xref:System.Windows.Controls.ContentControl> y utilizan su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="203dc-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="203dc-127">En la siguiente ilustración se muestran cuatro botones cuyo <xref:System.Windows.Controls.ContentControl.Content%2A> está establecido en una cadena, un objeto <xref:System.DateTime>, un <xref:System.Windows.Shapes.Rectangle>y un <xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>:</span><span class="sxs-lookup"><span data-stu-id="203dc-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![Captura de pantalla que muestra cuatro botones con distintos tipos de contenido.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="203dc-129">Para obtener un ejemplo de cómo establecer la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A>, vea <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="203dc-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="203dc-130">Controles que incluyen un encabezado y un único objeto arbitrario</span><span class="sxs-lookup"><span data-stu-id="203dc-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="203dc-131">La clase <xref:System.Windows.Controls.HeaderedContentControl> hereda de <xref:System.Windows.Controls.ContentControl> y muestra el contenido con un encabezado.</span><span class="sxs-lookup"><span data-stu-id="203dc-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="203dc-132">Hereda la propiedad de contenido, <xref:System.Windows.Controls.ContentControl.Content%2A>, de <xref:System.Windows.Controls.ContentControl> y define la propiedad <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> que es de tipo <xref:System.Object>; por lo tanto, ambos pueden ser un objeto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="203dc-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="203dc-133">Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedContentControl> y utilizan su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="203dc-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="203dc-134">En la ilustración siguiente se muestran dos objetos <xref:System.Windows.Controls.TabItem>.</span><span class="sxs-lookup"><span data-stu-id="203dc-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="203dc-135">La primera <xref:System.Windows.Controls.TabItem> tiene <xref:System.Windows.UIElement> objetos como <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="203dc-136">La <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> se establece en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="203dc-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="203dc-137">La <xref:System.Windows.Controls.ContentControl.Content%2A> se establece en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Controls.TextBlock> y un <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="203dc-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="203dc-138">El segundo <xref:System.Windows.Controls.TabItem> tiene una cadena en el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y un <xref:System.Windows.Controls.TextBlock> en el <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![TabControl que usa tipos diferentes en la propiedad header.](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="203dc-140">Para obtener un ejemplo de cómo crear objetos de <xref:System.Windows.Controls.TabItem>, vea <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="203dc-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="203dc-141">Controles que incluyen una colección de objetos arbitrarios</span><span class="sxs-lookup"><span data-stu-id="203dc-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="203dc-142">La clase <xref:System.Windows.Controls.ItemsControl> hereda de <xref:System.Windows.Controls.Control> y puede contener varios elementos, como cadenas, objetos u otros elementos.</span><span class="sxs-lookup"><span data-stu-id="203dc-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="203dc-143">Sus propiedades de contenido se <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> y <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="203dc-144">normalmente <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> se utiliza para rellenar el <xref:System.Windows.Controls.ItemsControl> con una colección de datos.</span><span class="sxs-lookup"><span data-stu-id="203dc-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="203dc-145">Si no desea usar una colección para rellenar el <xref:System.Windows.Controls.ItemsControl>, puede agregar elementos mediante la propiedad <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="203dc-146">Los siguientes controles heredan de <xref:System.Windows.Controls.ItemsControl> y utilizan su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="203dc-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="203dc-147">En la ilustración siguiente se muestra una <xref:System.Windows.Controls.ListBox> que contiene estos tipos de elementos:</span><span class="sxs-lookup"><span data-stu-id="203dc-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="203dc-148">Una cadena.</span><span class="sxs-lookup"><span data-stu-id="203dc-148">A string.</span></span>  
  
- <span data-ttu-id="203dc-149">Objeto <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="203dc-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="203dc-150"><xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="203dc-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="203dc-151"><xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="203dc-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![Captura de pantalla que muestra un cuadro de lista con cuatro tipos de contenido.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="203dc-153">Controles que incluyen un encabezado y una colección de objetos arbitrarios</span><span class="sxs-lookup"><span data-stu-id="203dc-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="203dc-154">La clase <xref:System.Windows.Controls.HeaderedItemsControl> hereda de <xref:System.Windows.Controls.ItemsControl> y puede contener varios elementos, como cadenas, objetos u otros elementos, y un encabezado.</span><span class="sxs-lookup"><span data-stu-id="203dc-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="203dc-155">Hereda las propiedades de contenido <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>y <xref:System.Windows.Controls.ItemsControl.Items%2A>, y define la propiedad <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> que puede ser un objeto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="203dc-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="203dc-156">Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedItemsControl> y utilizan su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="203dc-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="203dc-157">Clases que incluyen una colección de objetos UIElement</span><span class="sxs-lookup"><span data-stu-id="203dc-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="203dc-158">La clase <xref:System.Windows.Controls.Panel> coloca y organiza los objetos <xref:System.Windows.UIElement> secundarios.</span><span class="sxs-lookup"><span data-stu-id="203dc-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="203dc-159">Su propiedad de contenido es <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="203dc-160">Las siguientes clases heredan de la clase <xref:System.Windows.Controls.Panel> y utilizan su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="203dc-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="203dc-161">Para obtener más información, consulte [Información general sobre elementos Panel](panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="203dc-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="203dc-162">Clases que afectan a la apariencia de un objeto UIElement</span><span class="sxs-lookup"><span data-stu-id="203dc-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="203dc-163">La clase <xref:System.Windows.Controls.Decorator> aplica efectos visuales a un solo <xref:System.Windows.UIElement>secundario o alrededor de él.</span><span class="sxs-lookup"><span data-stu-id="203dc-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="203dc-164">Su propiedad de contenido es <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="203dc-165">Las siguientes clases heredan de <xref:System.Windows.Controls.Decorator> y utilizan su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="203dc-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="203dc-166">En la ilustración siguiente se muestra un <xref:System.Windows.Controls.TextBox> que tiene (se decora con) un <xref:System.Windows.Controls.Border> alrededor.</span><span class="sxs-lookup"><span data-stu-id="203dc-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="203dc-167">![TextBox con borde negro](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="203dc-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="203dc-168">TextBlock con borde</span><span class="sxs-lookup"><span data-stu-id="203dc-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="203dc-169">Clases que proporcionan comentarios visuales sobre un objeto UIElement</span><span class="sxs-lookup"><span data-stu-id="203dc-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="203dc-170">La clase <xref:System.Windows.Documents.Adorner> proporciona indicaciones visuales a un usuario.</span><span class="sxs-lookup"><span data-stu-id="203dc-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="203dc-171">Por ejemplo, utilice un <xref:System.Windows.Documents.Adorner> para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.</span><span class="sxs-lookup"><span data-stu-id="203dc-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="203dc-172">La clase <xref:System.Windows.Documents.Adorner> proporciona un marco para que pueda crear sus propios adornos.</span><span class="sxs-lookup"><span data-stu-id="203dc-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="203dc-173">no proporciona ningún adorno implementado.</span><span class="sxs-lookup"><span data-stu-id="203dc-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="203dc-174">Para más información, consulte [Información general sobre adornos](adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="203dc-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="203dc-175">Clases que permiten a los usuarios escribir texto</span><span class="sxs-lookup"><span data-stu-id="203dc-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="203dc-176">WPF proporciona tres controles principales que permiten a los usuarios escribir texto.</span><span class="sxs-lookup"><span data-stu-id="203dc-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="203dc-177">Cada control muestra el texto de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="203dc-177">Each control displays the text differently.</span></span> <span data-ttu-id="203dc-178">En la tabla siguiente, se muestran estos tres controles relacionados con el texto, sus funcionalidades cuando muestran texto y las propiedades que contienen el texto del control.</span><span class="sxs-lookup"><span data-stu-id="203dc-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="203dc-179">Control</span><span class="sxs-lookup"><span data-stu-id="203dc-179">Control</span></span>|<span data-ttu-id="203dc-180">El texto se muestra como</span><span class="sxs-lookup"><span data-stu-id="203dc-180">Text is displayed as</span></span>|<span data-ttu-id="203dc-181">Propiedad de contenido</span><span class="sxs-lookup"><span data-stu-id="203dc-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="203dc-182">Texto sin formato</span><span class="sxs-lookup"><span data-stu-id="203dc-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="203dc-183">Texto con formato</span><span class="sxs-lookup"><span data-stu-id="203dc-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="203dc-184">Texto oculto (se enmascaran los caracteres)</span><span class="sxs-lookup"><span data-stu-id="203dc-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="203dc-185">Clases que muestran el texto</span><span class="sxs-lookup"><span data-stu-id="203dc-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="203dc-186">Se pueden usar varias clases para mostrar texto sin formato o con él.</span><span class="sxs-lookup"><span data-stu-id="203dc-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="203dc-187">Puede usar <xref:System.Windows.Controls.TextBlock> para mostrar pequeñas cantidades de texto.</span><span class="sxs-lookup"><span data-stu-id="203dc-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="203dc-188">Si desea mostrar grandes cantidades de texto, utilice los controles <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="203dc-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="203dc-189">El <xref:System.Windows.Controls.TextBlock> tiene dos propiedades de contenido: <xref:System.Windows.Controls.TextBlock.Text%2A> y <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="203dc-190">Si desea mostrar texto que utiliza un formato coherente, la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> suele ser la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="203dc-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="203dc-191">Si piensa utilizar un formato diferente en todo el texto, use la propiedad <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="203dc-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="203dc-192">La propiedad <xref:System.Windows.Controls.TextBlock.Inlines%2A> es una colección de objetos <xref:System.Windows.Documents.Inline>, que especifican cómo dar formato al texto.</span><span class="sxs-lookup"><span data-stu-id="203dc-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="203dc-193">En la tabla siguiente se muestra la propiedad de contenido para las clases <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>y <xref:System.Windows.Controls.FlowDocumentScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="203dc-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="203dc-194">Control</span><span class="sxs-lookup"><span data-stu-id="203dc-194">Control</span></span>|<span data-ttu-id="203dc-195">Propiedad de contenido</span><span class="sxs-lookup"><span data-stu-id="203dc-195">Content property</span></span>|<span data-ttu-id="203dc-196">Tipo de propiedad de contenido</span><span class="sxs-lookup"><span data-stu-id="203dc-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="203dc-197">Documento</span><span class="sxs-lookup"><span data-stu-id="203dc-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="203dc-198">Documento</span><span class="sxs-lookup"><span data-stu-id="203dc-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="203dc-199">Documento</span><span class="sxs-lookup"><span data-stu-id="203dc-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="203dc-200">El <xref:System.Windows.Documents.FlowDocument> implementa la interfaz de <xref:System.Windows.Documents.IDocumentPaginatorSource>; por lo tanto, las tres clases pueden tomar un <xref:System.Windows.Documents.FlowDocument> como contenido.</span><span class="sxs-lookup"><span data-stu-id="203dc-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="203dc-201">Clases que dan formato al texto</span><span class="sxs-lookup"><span data-stu-id="203dc-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="203dc-202"><xref:System.Windows.Documents.TextElement> y sus clases relacionadas le permiten dar formato al texto.</span><span class="sxs-lookup"><span data-stu-id="203dc-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="203dc-203"><xref:System.Windows.Documents.TextElement> objetos contienen y dan formato al texto de los objetos <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="203dc-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="203dc-204">Los dos tipos principales de objetos <xref:System.Windows.Documents.TextElement> son <xref:System.Windows.Documents.Block> elementos y <xref:System.Windows.Documents.Inline> elementos.</span><span class="sxs-lookup"><span data-stu-id="203dc-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="203dc-205">Un elemento <xref:System.Windows.Documents.Block> representa un bloque de texto, como un párrafo o una lista.</span><span class="sxs-lookup"><span data-stu-id="203dc-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="203dc-206">Un elemento <xref:System.Windows.Documents.Inline> representa una parte del texto de un bloque.</span><span class="sxs-lookup"><span data-stu-id="203dc-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="203dc-207">Muchas clases de <xref:System.Windows.Documents.Inline> especifican el formato del texto al que se aplican.</span><span class="sxs-lookup"><span data-stu-id="203dc-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="203dc-208">Cada <xref:System.Windows.Documents.TextElement> tiene su propio modelo de contenido.</span><span class="sxs-lookup"><span data-stu-id="203dc-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="203dc-209">Para más información, consulte [Información general sobre el modelo de contenido de TextElement](../advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="203dc-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203dc-210">Consulte también</span><span class="sxs-lookup"><span data-stu-id="203dc-210">See also</span></span>

- [<span data-ttu-id="203dc-211">Avanzadas</span><span class="sxs-lookup"><span data-stu-id="203dc-211">Advanced</span></span>](../advanced/index.md)
