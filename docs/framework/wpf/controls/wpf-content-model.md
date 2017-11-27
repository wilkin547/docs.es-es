---
title: Modelo de contenido de WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52cb3a5391d6e24643b03a880d3695a11baceca3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="wpf-content-model"></a><span data-ttu-id="7fe09-102">Modelo de contenido de WPF</span><span class="sxs-lookup"><span data-stu-id="7fe09-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="7fe09-103"> es una plataforma de presentación que proporciona muchos controles y tipos semejantes a controles cuyo propósito principal es mostrar diferentes tipos de contenido.</span><span class="sxs-lookup"><span data-stu-id="7fe09-103"> is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="7fe09-104">Para determinar qué control usar o de qué control derivar, debe entender los tipos de objetos que un control determinado puede mostrar mejor.</span><span class="sxs-lookup"><span data-stu-id="7fe09-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="7fe09-105">En este tema se resume el modelo de contenido para controles y tipos semejantes a controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fe09-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="7fe09-106">El modelo de contenido describe el contenido que se puede utilizar en un control.</span><span class="sxs-lookup"><span data-stu-id="7fe09-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="7fe09-107">En este tema también se incluyen las propiedades de contenido para cada modelo de contenido.</span><span class="sxs-lookup"><span data-stu-id="7fe09-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="7fe09-108">Una propiedad de contenido es aquella que se utiliza para almacenar el contenido del objeto.</span><span class="sxs-lookup"><span data-stu-id="7fe09-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="7fe09-109">Clases que incluyen contenido arbitrario</span><span class="sxs-lookup"><span data-stu-id="7fe09-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="7fe09-110">Algunos controles pueden contener un objeto de cualquier tipo, como una cadena, un <xref:System.DateTime> objeto, o un <xref:System.Windows.UIElement> que es un contenedor para elementos adicionales.</span><span class="sxs-lookup"><span data-stu-id="7fe09-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="7fe09-111">Por ejemplo, un <xref:System.Windows.Controls.Button> puede contener una imagen y texto; o una <xref:System.Windows.Controls.CheckBox> puede contener el valor de <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="7fe09-112"> tiene cuatro clases que pueden incluir contenido arbitrario.</span><span class="sxs-lookup"><span data-stu-id="7fe09-112"> has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="7fe09-113">En la tabla siguiente se enumera las clases que heredan de <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="7fe09-114">Clase que incluye contenido arbitrario</span><span class="sxs-lookup"><span data-stu-id="7fe09-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="7fe09-115">Contenido</span><span class="sxs-lookup"><span data-stu-id="7fe09-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="7fe09-116">Un único objeto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="7fe09-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="7fe09-117">Un encabezado y un único elemento; ambos son objetos arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="7fe09-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="7fe09-118">Una colección de objetos arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="7fe09-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="7fe09-119">Un encabezado y una colección de elementos; todos ellos son objetos arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="7fe09-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="7fe09-120">Los controles que heredan de estas clases pueden incluir el mismo tipo de contenido y tratarlo de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="7fe09-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="7fe09-121">En la ilustración siguiente se muestra un control de cada modelo de contenido que incluye una imagen y texto.</span><span class="sxs-lookup"><span data-stu-id="7fe09-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="7fe09-122">![Button, GroupBox, ListBox, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="7fe09-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="7fe09-123">Controles que incluyen un único objeto arbitrario</span><span class="sxs-lookup"><span data-stu-id="7fe09-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="7fe09-124">La <xref:System.Windows.Controls.ContentControl> clase contiene una parte única de contenido arbitrario.</span><span class="sxs-lookup"><span data-stu-id="7fe09-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="7fe09-125">La propiedad content es <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="7fe09-126">Los siguientes controles heredan de <xref:System.Windows.Controls.ContentControl> y utilizar su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="7fe09-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 <span data-ttu-id="7fe09-127">La siguiente ilustración muestra cuatro botones cuya <xref:System.Windows.Controls.ContentControl.Content%2A> se establece en una cadena, un <xref:System.DateTime> objeto, un <xref:System.Windows.Shapes.Rectangle>y un <xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="7fe09-128">![Cuatro botones](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="7fe09-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="7fe09-129">Cuatro botones con distintos tipos de contenido</span><span class="sxs-lookup"><span data-stu-id="7fe09-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="7fe09-130">Para obtener un ejemplo de cómo establecer el <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad, vea <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="7fe09-131">Controles que incluyen un encabezado y un único objeto arbitrario</span><span class="sxs-lookup"><span data-stu-id="7fe09-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="7fe09-132">El <xref:System.Windows.Controls.HeaderedContentControl> clase hereda de <xref:System.Windows.Controls.ContentControl> y muestra el contenido con un encabezado.</span><span class="sxs-lookup"><span data-stu-id="7fe09-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="7fe09-133">Hereda la propiedad de contenido, <xref:System.Windows.Controls.ContentControl.Content%2A>, de <xref:System.Windows.Controls.ContentControl> y define la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> propiedad que es del tipo <xref:System.Object>; por lo tanto, ambos pueden ser un objeto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="7fe09-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="7fe09-134">Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedContentControl> y utilizar su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="7fe09-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="7fe09-135">En la siguiente ilustración se muestra dos <xref:System.Windows.Controls.TabItem> objetos.</span><span class="sxs-lookup"><span data-stu-id="7fe09-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="7fe09-136">La primera <xref:System.Windows.Controls.TabItem> tiene <xref:System.Windows.UIElement> objetos como la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="7fe09-137">El <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> está establecido en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Shapes.Ellipse> y <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="7fe09-138">El <xref:System.Windows.Controls.ContentControl.Content%2A> está establecido en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="7fe09-139">El segundo <xref:System.Windows.Controls.TabItem> tiene una cadena el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y un <xref:System.Windows.Controls.TextBlock> en el <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="7fe09-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="7fe09-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="7fe09-141">TabControl que usa tipos diferentes en la propiedad Header</span><span class="sxs-lookup"><span data-stu-id="7fe09-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="7fe09-142">Para obtener un ejemplo de cómo crear <xref:System.Windows.Controls.TabItem> los objetos, vea <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="7fe09-143">Controles que incluyen una colección de objetos arbitrarios</span><span class="sxs-lookup"><span data-stu-id="7fe09-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="7fe09-144">El <xref:System.Windows.Controls.ItemsControl> clase hereda de <xref:System.Windows.Controls.Control> y puede contener varios elementos, como cadenas, objetos u otros elementos.</span><span class="sxs-lookup"><span data-stu-id="7fe09-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="7fe09-145">Sus propiedades de contenido son <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> y <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="7fe09-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>Normalmente se usa para rellenar la <xref:System.Windows.Controls.ItemsControl> con una colección de datos.</span><span class="sxs-lookup"><span data-stu-id="7fe09-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="7fe09-147">Si no desea usar una colección para rellenar el <xref:System.Windows.Controls.ItemsControl>, puede agregar elementos mediante el <xref:System.Windows.Controls.ItemsControl.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7fe09-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="7fe09-148">Los siguientes controles heredan de <xref:System.Windows.Controls.ItemsControl> y utilizar su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="7fe09-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="7fe09-149">La siguiente ilustración muestra un <xref:System.Windows.Controls.ListBox> que contiene estos tipos de elementos:</span><span class="sxs-lookup"><span data-stu-id="7fe09-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="7fe09-150">Una cadena.</span><span class="sxs-lookup"><span data-stu-id="7fe09-150">A string.</span></span>  
  
-   <span data-ttu-id="7fe09-151">Objeto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="7fe09-152">Objeto <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="7fe09-153">A <xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="7fe09-154">![ListBox con cuatro tipos de contenido](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="7fe09-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="7fe09-155">ListBox con varios tipos de objeto</span><span class="sxs-lookup"><span data-stu-id="7fe09-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="7fe09-156">Controles que incluyen un encabezado y una colección de objetos arbitrarios</span><span class="sxs-lookup"><span data-stu-id="7fe09-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="7fe09-157">El <xref:System.Windows.Controls.HeaderedItemsControl> clase hereda de <xref:System.Windows.Controls.ItemsControl> y pueden contener varios elementos, como cadenas, objetos, u otros elementos y un encabezado.</span><span class="sxs-lookup"><span data-stu-id="7fe09-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="7fe09-158">Hereda el <xref:System.Windows.Controls.ItemsControl> contenido propiedades, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, y <xref:System.Windows.Controls.ItemsControl.Items%2A>, y define la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad que puede ser un objeto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="7fe09-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="7fe09-159">Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedItemsControl> y utilizar su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="7fe09-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="7fe09-160">Clases que incluyen una colección de objetos UIElement</span><span class="sxs-lookup"><span data-stu-id="7fe09-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="7fe09-161">El <xref:System.Windows.Controls.Panel> clase coloca y organiza secundarios <xref:System.Windows.UIElement> objetos.</span><span class="sxs-lookup"><span data-stu-id="7fe09-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="7fe09-162">La propiedad content es <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="7fe09-163">Las siguientes clases heredan de la <xref:System.Windows.Controls.Panel> clase y utilizar su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="7fe09-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="7fe09-164">Para más información, consulte [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7fe09-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="7fe09-165">Clases que afectan a la apariencia de un objeto UIElement</span><span class="sxs-lookup"><span data-stu-id="7fe09-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="7fe09-166">El <xref:System.Windows.Controls.Decorator> clase aplica efectos visuales en o en torno a un único elemento secundario <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="7fe09-167">La propiedad content es <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="7fe09-168">Las siguientes clases heredan de <xref:System.Windows.Controls.Decorator> y utilizar su modelo de contenido:</span><span class="sxs-lookup"><span data-stu-id="7fe09-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="7fe09-169">La siguiente ilustración muestra un <xref:System.Windows.Controls.TextBox> que tiene (está decorado con) un <xref:System.Windows.Controls.Border> alrededor de ella.</span><span class="sxs-lookup"><span data-stu-id="7fe09-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="7fe09-170">![TextBox con borde negro](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="7fe09-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="7fe09-171">TextBlock con borde</span><span class="sxs-lookup"><span data-stu-id="7fe09-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="7fe09-172">Clases que proporcionan comentarios visuales sobre un objeto UIElement</span><span class="sxs-lookup"><span data-stu-id="7fe09-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="7fe09-173">La <xref:System.Windows.Documents.Adorner> clase proporciona indicaciones visuales a un usuario.</span><span class="sxs-lookup"><span data-stu-id="7fe09-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="7fe09-174">Por ejemplo, use un <xref:System.Windows.Documents.Adorner> para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.</span><span class="sxs-lookup"><span data-stu-id="7fe09-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="7fe09-175">La <xref:System.Windows.Documents.Adorner> clase proporciona un marco de trabajo para que pueda crear sus propios adornos.</span><span class="sxs-lookup"><span data-stu-id="7fe09-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="7fe09-176"> no proporciona ningún adorno implementado.</span><span class="sxs-lookup"><span data-stu-id="7fe09-176"> does not provide any implemented adorners.</span></span> <span data-ttu-id="7fe09-177">Para más información, consulte [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7fe09-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="7fe09-178">Clases que permiten a los usuarios escribir texto</span><span class="sxs-lookup"><span data-stu-id="7fe09-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="7fe09-179">WPF proporciona tres controles principales que permiten a los usuarios escribir texto.</span><span class="sxs-lookup"><span data-stu-id="7fe09-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="7fe09-180">Cada control muestra el texto de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="7fe09-180">Each control displays the text differently.</span></span> <span data-ttu-id="7fe09-181">En la tabla siguiente, se muestran estos tres controles relacionados con el texto, sus funcionalidades cuando muestran texto y las propiedades que contienen el texto del control.</span><span class="sxs-lookup"><span data-stu-id="7fe09-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="7fe09-182">Control</span><span class="sxs-lookup"><span data-stu-id="7fe09-182">Control</span></span>|<span data-ttu-id="7fe09-183">El texto se muestra como</span><span class="sxs-lookup"><span data-stu-id="7fe09-183">Text is displayed as</span></span>|<span data-ttu-id="7fe09-184">Propiedad de contenido</span><span class="sxs-lookup"><span data-stu-id="7fe09-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="7fe09-185">Texto sin formato</span><span class="sxs-lookup"><span data-stu-id="7fe09-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="7fe09-186">Texto con formato</span><span class="sxs-lookup"><span data-stu-id="7fe09-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="7fe09-187">Texto oculto (se enmascaran los caracteres)</span><span class="sxs-lookup"><span data-stu-id="7fe09-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="7fe09-188">Clases que muestran el texto</span><span class="sxs-lookup"><span data-stu-id="7fe09-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="7fe09-189">Se pueden usar varias clases para mostrar texto sin formato o con él.</span><span class="sxs-lookup"><span data-stu-id="7fe09-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="7fe09-190">Puede usar <xref:System.Windows.Controls.TextBlock> para mostrar pequeñas cantidades de texto.</span><span class="sxs-lookup"><span data-stu-id="7fe09-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="7fe09-191">Si desea mostrar grandes cantidades de texto, use la <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, o <xref:System.Windows.Controls.FlowDocumentScrollViewer> controles.</span><span class="sxs-lookup"><span data-stu-id="7fe09-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="7fe09-192">El <xref:System.Windows.Controls.TextBlock> tiene dos propiedades de contenido: <xref:System.Windows.Controls.TextBlock.Text%2A> y <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fe09-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="7fe09-193">Cuando desea mostrar texto que usa un formato coherente, la <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad suele ser la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="7fe09-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="7fe09-194">Si tiene previsto utilizar un formato diferente en todo el texto, use la <xref:System.Windows.Controls.TextBlock.Inlines%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7fe09-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="7fe09-195">El <xref:System.Windows.Controls.TextBlock.Inlines%2A> propiedad es una colección de <xref:System.Windows.Documents.Inline> objetos, que especifican cómo dar formato al texto.</span><span class="sxs-lookup"><span data-stu-id="7fe09-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="7fe09-196">La tabla siguiente muestra la propiedad de contenido para <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, y <xref:System.Windows.Controls.FlowDocumentScrollViewer> clases.</span><span class="sxs-lookup"><span data-stu-id="7fe09-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="7fe09-197">Control</span><span class="sxs-lookup"><span data-stu-id="7fe09-197">Control</span></span>|<span data-ttu-id="7fe09-198">Propiedad de contenido</span><span class="sxs-lookup"><span data-stu-id="7fe09-198">Content property</span></span>|<span data-ttu-id="7fe09-199">Tipo de propiedad de contenido</span><span class="sxs-lookup"><span data-stu-id="7fe09-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="7fe09-200">Documento</span><span class="sxs-lookup"><span data-stu-id="7fe09-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="7fe09-201">Documento</span><span class="sxs-lookup"><span data-stu-id="7fe09-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="7fe09-202">Documento</span><span class="sxs-lookup"><span data-stu-id="7fe09-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="7fe09-203">El <xref:System.Windows.Documents.FlowDocument> implementa la <xref:System.Windows.Documents.IDocumentPaginatorSource> interfaz; por lo tanto, todas las tres clases pueden tomar un <xref:System.Windows.Documents.FlowDocument> como contenido.</span><span class="sxs-lookup"><span data-stu-id="7fe09-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="7fe09-204">Clases que dan formato al texto</span><span class="sxs-lookup"><span data-stu-id="7fe09-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="7fe09-205"><xref:System.Windows.Documents.TextElement>y sus clases relacionadas que pueda dar formato al texto.</span><span class="sxs-lookup"><span data-stu-id="7fe09-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="7fe09-206"><xref:System.Windows.Documents.TextElement>objetos contienen y dar formato al texto en <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> objetos.</span><span class="sxs-lookup"><span data-stu-id="7fe09-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="7fe09-207">Los dos tipos principales de <xref:System.Windows.Documents.TextElement> objetos son <xref:System.Windows.Documents.Block> elementos y <xref:System.Windows.Documents.Inline> elementos.</span><span class="sxs-lookup"><span data-stu-id="7fe09-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="7fe09-208">Un <xref:System.Windows.Documents.Block> elemento representa un bloque de texto, por ejemplo, un párrafo o una lista.</span><span class="sxs-lookup"><span data-stu-id="7fe09-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="7fe09-209">Un <xref:System.Windows.Documents.Inline> elemento representa una parte del texto en un bloque.</span><span class="sxs-lookup"><span data-stu-id="7fe09-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="7fe09-210">Muchos <xref:System.Windows.Documents.Inline> clases especifican el formato para el texto al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="7fe09-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="7fe09-211">Cada <xref:System.Windows.Documents.TextElement> tiene su propio modelo de contenido.</span><span class="sxs-lookup"><span data-stu-id="7fe09-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="7fe09-212">Para más información, consulte [Información general sobre el modelo de contenido de TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7fe09-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fe09-213">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fe09-213">See Also</span></span>  
 [<span data-ttu-id="7fe09-214">Avanzadas</span><span class="sxs-lookup"><span data-stu-id="7fe09-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)
