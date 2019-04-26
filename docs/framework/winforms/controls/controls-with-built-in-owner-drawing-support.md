---
title: Controles compatibles con dibujos propietarios integrados
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: 1807170b2f5df2333ec3b271a11f9b929c1e7993
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011585"
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="907cf-102">Controles compatibles con dibujos propietarios integrados</span><span class="sxs-lookup"><span data-stu-id="907cf-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="907cf-103">Los dibujos propietarios en formularios Windows Forms, que también se conocen como dibujos personalizados, es una técnica para cambiar la apariencia visual de determinados controles.</span><span class="sxs-lookup"><span data-stu-id="907cf-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="907cf-104">La palabra "control" en este tema se usa para indicar las clases que derivan de <xref:System.Windows.Forms.Control> o <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="907cf-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="907cf-105">Normalmente, Windows controla el dibujo automático mediante el uso de valores de propiedad como <xref:System.Windows.Forms.Control.BackColor%2A> para determinar la apariencia de un control.</span><span class="sxs-lookup"><span data-stu-id="907cf-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="907cf-106">Con el dibujo del propietario, toma el control sobre el proceso de dibujo, con lo que puede cambiar los elementos de apariencia que no están disponibles mediante las propiedades.</span><span class="sxs-lookup"><span data-stu-id="907cf-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="907cf-107">Por ejemplo, muchos controles le permiten establecer el color del texto que se muestra, pero está limitado a un único color.</span><span class="sxs-lookup"><span data-stu-id="907cf-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="907cf-108">El dibujo del propietario le permite realizar tareas como mostrar una parte del texto en negro y otra en rojo.</span><span class="sxs-lookup"><span data-stu-id="907cf-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="907cf-109">En la práctica, el dibujo del propietario es similar a dibujar gráficos en un formulario.</span><span class="sxs-lookup"><span data-stu-id="907cf-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="907cf-110">Por ejemplo, podría utilizar métodos gráficos en un controlador para el formulario <xref:System.Windows.Forms.Control.Paint> eventos para emular un `ListBox` control, pero tendría que escribir su propio código para controlar toda la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="907cf-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="907cf-111">Con el dibujo del propietario, el control utiliza su código para dibujar el contenido, pero por lo demás conserva todas sus funciones intrínsecas.</span><span class="sxs-lookup"><span data-stu-id="907cf-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="907cf-112">Puede utilizar métodos gráficos para dibujar cada elemento en el control o personalizar algunos aspectos de cada elemento mientras utiliza la apariencia predeterminada para otros aspectos de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="907cf-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="907cf-113">Dibujo del propietario en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="907cf-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="907cf-114">Para realizar el dibujo propietario en controles compatibles, normalmente establece una propiedad y controla uno o más eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="907cf-115">La mayoría de los controles que admiten el dibujo del propietario tienen una propiedad `OwnerDraw` o `DrawMode` que indica si el control generará eventos relacionados con el dibujo cuando se pinta a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="907cf-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="907cf-116">Los controles que no tienen una propiedad `OwnerDraw` o `DrawMode` incluyen el control `DataGridView`, que proporciona eventos de dibujo que se producen automáticamente, y el control `ToolStrip`, que se dibuja utilizando una clase de representación externa que tiene sus propios eventos relacionados con el dibujo.</span><span class="sxs-lookup"><span data-stu-id="907cf-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="907cf-117">Hay muchos tipos diferentes de eventos de dibujo, pero se produce un evento de dibujo típico con el fin de dibujar un solo elemento dentro de un control.</span><span class="sxs-lookup"><span data-stu-id="907cf-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="907cf-118">El controlador de eventos recibe un objeto `EventArgs` que contiene información sobre el elemento que se va a dibujar y herramientas que puede utilizar para dibujarlo.</span><span class="sxs-lookup"><span data-stu-id="907cf-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="907cf-119">Por ejemplo, este objeto contiene normalmente el número de índice del elemento en la colección primaria, un <xref:System.Drawing.Rectangle> que indica el elemento Mostrar límites y un <xref:System.Drawing.Graphics> objeto para llamar a métodos de dibujo.</span><span class="sxs-lookup"><span data-stu-id="907cf-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="907cf-120">En algunos eventos, el objeto `EventArgs` proporciona información adicional sobre el elemento y los métodos que puede llamar para dibujar algunos aspectos del elemento de forma predeterminada, como el fondo o un rectángulo de enfoque.</span><span class="sxs-lookup"><span data-stu-id="907cf-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="907cf-121">Para crear un control reutilizable que contenga sus personalizaciones para dibujo del propietario, cree una nueva clase que derive de una clase de control que admita el dibujo del propietario.</span><span class="sxs-lookup"><span data-stu-id="907cf-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="907cf-122">En lugar de controlar eventos de dibujo, incluya el código de dibujo del propietario en invalidaciones para el método o los métodos `On`*EventName* de la clase nueva.</span><span class="sxs-lookup"><span data-stu-id="907cf-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="907cf-123">Asegúrese de llamar al método o los métodos `On`*EventName* de la clase base en este caso para que los usuarios de su control puedan controlar eventos del dibujo del propietario y proporcionar una personalización adicional.</span><span class="sxs-lookup"><span data-stu-id="907cf-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="907cf-124">Los siguientes controles de formularios Windows Forms son compatibles con el dibujo del propietario en todas las versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="907cf-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <span data-ttu-id="907cf-125"><xref:System.Windows.Forms.MenuItem> (usa <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="907cf-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="907cf-126">Los controles siguientes son compatibles solamente con el dibujo del propietario en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="907cf-126">The following controls support owner drawing only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="907cf-127">Los controles siguientes son compatibles con el dibujo del propietario y son nuevos en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="907cf-127">The following controls support owner drawing and are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="907cf-128">Las secciones siguientes ofrecen detalles adicionales para cada uno de estos controles.</span><span class="sxs-lookup"><span data-stu-id="907cf-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="907cf-129">Controles ListBox y ComboBox</span><span class="sxs-lookup"><span data-stu-id="907cf-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="907cf-130">El <xref:System.Windows.Forms.ListBox> y <xref:System.Windows.Forms.ComboBox> controles le permiten dibujar elementos individuales en el control en un tamaño, o en diferentes tamaños.</span><span class="sxs-lookup"><span data-stu-id="907cf-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="907cf-131">Aunque el <xref:System.Windows.Forms.CheckedListBox> control se deriva el <xref:System.Windows.Forms.ListBox> control, no admite el dibujo del propietario.</span><span class="sxs-lookup"><span data-stu-id="907cf-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="907cf-132">Para dibujar cada elemento del mismo tamaño, establezca el `DrawMode` propiedad <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> y controlar el `DrawItem` eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="907cf-133">Para dibujar cada elemento con un tamaño distinto, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> y controlar tanto el `MeasureItem` y `DrawItem` eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="907cf-134">El evento `MeasureItem` le permite indicar el tamaño de un elemento antes de que se produzca el evento `DrawItem` para ese elemento.</span><span class="sxs-lookup"><span data-stu-id="907cf-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="907cf-135">Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-135">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [<span data-ttu-id="907cf-136">Cómo: Crear texto de tamaño Variable en un Control ComboBox</span><span class="sxs-lookup"><span data-stu-id="907cf-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="907cf-137">Componente MenuItem</span><span class="sxs-lookup"><span data-stu-id="907cf-137">MenuItem Component</span></span>  
 <span data-ttu-id="907cf-138">El <xref:System.Windows.Forms.MenuItem> componente representa un solo elemento de menú en un <xref:System.Windows.Forms.MainMenu> o <xref:System.Windows.Forms.ContextMenu> componente.</span><span class="sxs-lookup"><span data-stu-id="907cf-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="907cf-139">Para dibujar un <xref:System.Windows.Forms.MenuItem>, establezca su `OwnerDraw` propiedad `true` y controlar su `DrawItem` eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="907cf-140">Para personalizar el tamaño del elemento de menú antes de que se produzca el evento `DrawItem`, controle el evento `MeasureItem` del elemento.</span><span class="sxs-lookup"><span data-stu-id="907cf-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="907cf-141">Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-141">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="907cf-142">TabControl (Control)</span><span class="sxs-lookup"><span data-stu-id="907cf-142">TabControl Control</span></span>  
 <span data-ttu-id="907cf-143">El <xref:System.Windows.Forms.TabControl> control le permite dibujar pestañas individuales en el control.</span><span class="sxs-lookup"><span data-stu-id="907cf-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="907cf-144">Dibujo del propietario afecta solo las pestañas; el <xref:System.Windows.Forms.TabPage> no afecta al contenido.</span><span class="sxs-lookup"><span data-stu-id="907cf-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="907cf-145">Para dibujar cada pestaña un <xref:System.Windows.Forms.TabControl>, establezca el `DrawMode` propiedad <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> y controlar el `DrawItem` eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="907cf-146">Este evento se produce una vez para cada pestaña solo cuando la pestaña está visible en el control.</span><span class="sxs-lookup"><span data-stu-id="907cf-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="907cf-147">Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-147">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="907cf-148">ToolTip</span><span class="sxs-lookup"><span data-stu-id="907cf-148">ToolTip Component</span></span>  
 <span data-ttu-id="907cf-149">El <xref:System.Windows.Forms.ToolTip> componente le permite dibujar la información sobre herramientas completa cuando se muestre.</span><span class="sxs-lookup"><span data-stu-id="907cf-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="907cf-150">Para dibujar un <xref:System.Windows.Forms.ToolTip>, establezca su `OwnerDraw` propiedad `true` y controlar su `Draw` eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="907cf-151">Para personalizar el tamaño de la <xref:System.Windows.Forms.ToolTip> antes de la `Draw` se produce un evento, controlar el `Popup` evento y establecer el <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> propiedad en el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="907cf-152">Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-152">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="907cf-153">Control ListView</span><span class="sxs-lookup"><span data-stu-id="907cf-153">ListView Control</span></span>  
 <span data-ttu-id="907cf-154">El <xref:System.Windows.Forms.ListView> control le permite dibujar elementos individuales, subelementos y encabezados de columna en el control.</span><span class="sxs-lookup"><span data-stu-id="907cf-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="907cf-155">Para habilitar el dibujo propietario en el control, establezca la propiedad `OwnerDraw` en `true`.</span><span class="sxs-lookup"><span data-stu-id="907cf-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="907cf-156">Para dibujar cada elemento en el control, controle el evento `DrawItem`.</span><span class="sxs-lookup"><span data-stu-id="907cf-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="907cf-157">Para dibujar cada subelemento o encabezado de columna en el control cuando el <xref:System.Windows.Forms.ListView.View%2A> propiedad está establecida en <xref:System.Windows.Forms.View.Details>, controlar el `DrawSubItem` y `DrawColumnHeader` eventos.</span><span class="sxs-lookup"><span data-stu-id="907cf-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="907cf-158">Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-158">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="907cf-159">TreeView (Control)</span><span class="sxs-lookup"><span data-stu-id="907cf-159">TreeView Control</span></span>  
 <span data-ttu-id="907cf-160">El <xref:System.Windows.Forms.TreeView> control le permite dibujar nodos individuales en el control.</span><span class="sxs-lookup"><span data-stu-id="907cf-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="907cf-161">Para dibujar solo el texto mostrado en cada nodo, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> y controlar el `DrawNode` eventos para dibujar el texto.</span><span class="sxs-lookup"><span data-stu-id="907cf-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="907cf-162">Para dibujar todos los elementos de cada nodo, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> y controlar el `DrawNode` eventos para dibujar cualquier elemento que necesite, como texto, iconos, casillas, signos, más y menos y líneas que conectan los nodos.</span><span class="sxs-lookup"><span data-stu-id="907cf-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="907cf-163">Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-163">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="907cf-164">Control DataGridView</span><span class="sxs-lookup"><span data-stu-id="907cf-164">DataGridView Control</span></span>  
 <span data-ttu-id="907cf-165">El <xref:System.Windows.Forms.DataGridView> control le permite dibujar celdas y filas individuales en el control.</span><span class="sxs-lookup"><span data-stu-id="907cf-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="907cf-166">Para dibujar celdas individuales, controle el evento `CellPainting`.</span><span class="sxs-lookup"><span data-stu-id="907cf-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="907cf-167">Para dibujar filas o elementos de filas, controle uno o ambos eventos `RowPrePaint` y `RowPostPaint`.</span><span class="sxs-lookup"><span data-stu-id="907cf-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="907cf-168">El evento `RowPrePaint` se produce antes de que se dibujen las celdas en una fila, y el evento `RowPostPaint` se produce después de dibujar las celdas.</span><span class="sxs-lookup"><span data-stu-id="907cf-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="907cf-169">Puede controlar ambos eventos y el evento `CellPainting` para pintar el fondo de una fila, celdas individuales y el primer plano de una fila por separado, o bien puede proporcionar personalizaciones específicas donde las necesite y usar la vista predeterminada para otros elementos de la fila.</span><span class="sxs-lookup"><span data-stu-id="907cf-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="907cf-170">Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-170">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [<span data-ttu-id="907cf-171">Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="907cf-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [<span data-ttu-id="907cf-172">Cómo: Personalizar la apariencia de las filas en el Control DataGridView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="907cf-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="907cf-173">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="907cf-173">ToolStrip Control</span></span>  
 <span data-ttu-id="907cf-174"><xref:System.Windows.Forms.ToolStrip> y los controles derivados le permiten personalizar cualquier aspecto de su apariencia.</span><span class="sxs-lookup"><span data-stu-id="907cf-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="907cf-175">Para proporcionar una representación personalizada para <xref:System.Windows.Forms.ToolStrip> controles, establezca el `Renderer` propiedad de un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, o <xref:System.Windows.Forms.ToolStripContentPanel> a un `ToolStripRenderer` de objetos y controle uno o varios de los muchos eventos de dibujos proporcionados por el `ToolStripRenderer` clase.</span><span class="sxs-lookup"><span data-stu-id="907cf-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="907cf-176">Como alternativa, establezca un `Renderer` propiedad a una instancia de su propia clase derivada de `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, o <xref:System.Windows.Forms.ToolStripSystemRenderer> que implementa o reemplaza específico `On` *EventName* métodos.</span><span class="sxs-lookup"><span data-stu-id="907cf-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="907cf-177">Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="907cf-177">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [<span data-ttu-id="907cf-178">Cómo: Crear y establecer a un representador personalizado para el Control ToolStrip de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="907cf-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [<span data-ttu-id="907cf-179">Cómo: Dibujar un Control ToolStrip personalizada</span><span class="sxs-lookup"><span data-stu-id="907cf-179">How to: Custom Draw a ToolStrip Control</span></span>](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="907cf-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="907cf-180">See also</span></span>

- [<span data-ttu-id="907cf-181">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="907cf-181">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
