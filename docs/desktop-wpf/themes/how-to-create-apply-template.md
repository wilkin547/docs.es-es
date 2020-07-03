---
title: 'Creación de una plantilla en WPF: Escritorio de .NET'
description: Obtenga información sobre cómo crear una plantilla de control y hacer referencia a esta en Windows Presentation Foundation y .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c372659676b450cde789c96e45c7ec5de2aea194
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325728"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="b3cc1-103">Creación de una plantilla de un control</span><span class="sxs-lookup"><span data-stu-id="b3cc1-103">Create a template for a control</span></span>

<span data-ttu-id="b3cc1-104">Con Windows Presentation Foundation (WPF), puede usar su propia plantilla reutilizable para personalizar la estructura visual y el comportamiento de un control existente.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="b3cc1-105">Las plantillas se pueden aplicar de forma global a la aplicación, las ventanas y las páginas, o bien directamente a los controles.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="b3cc1-106">La mayoría de los escenarios en los que es necesario crear un control se pueden solventar creando en su lugar una plantilla para un control existente.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="b3cc1-107">En este artículo, veremos cómo crear un objeto <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="b3cc1-108">Cuándo crear un objeto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b3cc1-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="b3cc1-109">Los controles tienen muchas propiedades, como <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontFamily%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="b3cc1-110">Estas propiedades se encargan de distintos aspectos relacionados con la apariencia del control, pero los cambios que se pueden realizar configurando estas propiedades son limitados.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="b3cc1-111">Por ejemplo, la propiedad <xref:System.Windows.Controls.Control.Foreground%2A> se puede establecer en azul y <xref:System.Windows.Controls.Control.FontStyle%2A> en cursiva en un objeto <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="b3cc1-112">Si queremos personalizar la apariencia del control de forma diferente a como lo hace la configuración de las demás propiedades del control, hay que crear un objeto <xref:System.Windows.Controls.ControlTemplate>.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="b3cc1-113">En la mayoría de las interfaces de usuario, los botones tienen la misma apariencia en general: un rectángulo con texto.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="b3cc1-114">Si quisiéramos crear un botón redondeado, podríamos crear un control que herede del botón o que vuelva a crear la funcionalidad del botón</span><span class="sxs-lookup"><span data-stu-id="b3cc1-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="b3cc1-115">y que, además, aporte el elemento visual circular.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="b3cc1-116">Para no tener que crear más controles, se puede personalizar el diseño visual de un control existente.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="b3cc1-117">En el caso del botón redondeado, hay que crear un objeto <xref:System.Windows.Controls.ControlTemplate> con el diseño visual que buscamos.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="b3cc1-118">Por otra parte, si necesitamos un control con nueva funcionalidad, con propiedades diferentes y con nuevas configuraciones, crearíamos un objeto <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3cc1-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b3cc1-119">Prerequisites</span></span>

<span data-ttu-id="b3cc1-120">Cree una aplicación de WPF y, en *MainWindow.xaml* (o en otra ventana de su elección), configure las siguientes propiedades en el elemento **\<Window>** :</span><span class="sxs-lookup"><span data-stu-id="b3cc1-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **Title**         | `Template Intro Sample` |
| **SizeToContent** | `WidthAndHeight` |
| **MinWidth**      | `250` |

<span data-ttu-id="b3cc1-121">Configure el contenido del elemento **\<Window>** en el siguiente código XAML:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="b3cc1-122">Al final del proceso, el archivo *MainWindow.xaml* debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="b3cc1-123">Si la aplicación se ejecuta, tendrá el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-123">If you run the application, it looks like the following:</span></span>

![Ventana de WPF con dos botones sin estilo](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="b3cc1-125">Creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b3cc1-125">Create a ControlTemplate</span></span>

<span data-ttu-id="b3cc1-126">La forma más común de declarar un objeto <xref:System.Windows.Controls.ControlTemplate> es como un recurso en la sección `Resources` de un archivo XAML.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="b3cc1-127">Dado que las plantillas son recursos, siguen las mismas reglas de ámbito que se aplican a todos los recursos.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="b3cc1-128">Simplemente, la ubicación de la declaración de una plantilla afecta a dónde se puede aplicar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="b3cc1-129">Por ejemplo, si declara una plantilla en el elemento raíz del archivo XAML de definición de la aplicación, puede usar en cualquier parte de esta.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="b3cc1-130">Si la plantilla se define en una ventana, solo los controles de esa ventana podrán usarla.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="b3cc1-131">Para empezar, agregue un elemento `Window.Resources` al archivo *MainWindow.xaml*:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="b3cc1-132">Cree un valor **\<ControlTemplate>** nuevo con las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="b3cc1-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="b3cc1-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="b3cc1-134">Esta plantilla de control será sencilla:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-134">This control template will be simple:</span></span>

- <span data-ttu-id="b3cc1-135">Un elemento raíz del control, un elemento <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="b3cc1-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="b3cc1-136">Un elemento <xref:System.Windows.Shapes.Ellipse> para trazar el aspecto redondeado del botón</span><span class="sxs-lookup"><span data-stu-id="b3cc1-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="b3cc1-137">Un elemento <xref:System.Windows.Controls.ContentPresenter> para mostrar el contenido del botón especificado por el usuario</span><span class="sxs-lookup"><span data-stu-id="b3cc1-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="b3cc1-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="b3cc1-138">TemplateBinding</span></span>

<span data-ttu-id="b3cc1-139">Al crear un elemento <xref:System.Windows.Controls.ControlTemplate>, puede que quiera seguir usando las propiedades públicas para cambiar la apariencia del control.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="b3cc1-140">La extensión de marcado [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) enlaza una propiedad de un elemento que está en el elemento <xref:System.Windows.Controls.ControlTemplate> a una propiedad pública que está definida por el control.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="b3cc1-141">Cuando se usa [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), se habilitan propiedades en el control que actúan como parámetros de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="b3cc1-142">Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene la extensión [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="b3cc1-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="b3cc1-143">Ellipse</span><span class="sxs-lookup"><span data-stu-id="b3cc1-143">Ellipse</span></span>

<span data-ttu-id="b3cc1-144">Cabe decir que las propiedades **:::no-loc text="Fill":::** y **:::no-loc text="Stroke":::** del elemento **\<Ellipse>** están enlazadas a las propiedades <xref:System.Windows.Controls.Control.Foreground> y <xref:System.Windows.Controls.Control.Background> del control.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="b3cc1-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="b3cc1-145">ContentPresenter</span></span>

<span data-ttu-id="b3cc1-146">También se agrega a la plantilla un elemento [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter).</span><span class="sxs-lookup"><span data-stu-id="b3cc1-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="b3cc1-147">Dado que esta plantilla está diseñada para un botón, tenga en cuenta que el botón hereda de <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="b3cc1-148">El botón presenta el contenido del elemento.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-148">The button presents the content of the element.</span></span> <span data-ttu-id="b3cc1-149">Se puede establecer cualquier elemento dentro del botón, como texto sin formato o incluso otro control.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="b3cc1-150">Los dos botones siguientes son válidos:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="b3cc1-151">En estos dos ejemplos, el texto y la casilla se configuran como la propiedad [Button.Content](xref:System.Windows.Controls.ContentControl.Content).</span><span class="sxs-lookup"><span data-stu-id="b3cc1-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="b3cc1-152">Lo que se establezca como contenido se puede mostrar a través de un elemento **\<ContentPresenter>** , que es lo que la plantilla hace.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="b3cc1-153">Si el elemento <xref:System.Windows.Controls.ControlTemplate> se aplica a un tipo <xref:System.Windows.Controls.ContentControl>, como un elemento `Button`, se busca un elemento <xref:System.Windows.Controls.ContentPresenter> en el árbol de elementos.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="b3cc1-154">Si se halla el elemento `ContentPresenter`, la plantilla enlaza automáticamente la propiedad <xref:System.Windows.Controls.ContentControl.Content> del control a `ContentPresenter`.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="b3cc1-155">Uso de la plantilla</span><span class="sxs-lookup"><span data-stu-id="b3cc1-155">Use the template</span></span>

<span data-ttu-id="b3cc1-156">Busque los botones que se declararon al principio de este artículo.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="b3cc1-157">Establezca la propiedad <xref:System.Windows.Controls.Control.Template> del segundo botón en el recurso `roundbutton`:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="b3cc1-158">Si ejecuta el proyecto y observa el resultado, verá que el botón tiene un fondo redondeado.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![Ventana de WPF con un botón ovalado de plantilla](media/create-apply-template/styled-button.png)

<span data-ttu-id="b3cc1-160">Posiblemente se haya dado cuenta de que el botón no es un círculo perfecto, sino que está distorsionado.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="b3cc1-161">El elemento **\<Ellipse>** funciona de forma que se expande para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="b3cc1-162">Para que el círculo sea uniforme, cambie las propiedades **:::no-loc text="width":::** y **:::no-loc text="height":::** del botón al mismo valor:</span><span class="sxs-lookup"><span data-stu-id="b3cc1-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Ventana de WPF con un botón circular de plantilla](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="b3cc1-164">Incorporación de un desencadenador</span><span class="sxs-lookup"><span data-stu-id="b3cc1-164">Add a Trigger</span></span>

<span data-ttu-id="b3cc1-165">Aunque un botón que tiene una plantilla aplicada tiene un aspecto diferente, se comporta igual que cualquier otro botón.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="b3cc1-166">Si se presiona, se activa el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="b3cc1-167">Pese a ello, posiblemente se haya dado cuenta de que, al mover el ratón por el botón, sus elementos visuales no cambian.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="b3cc1-168">Todas estas interacciones visuales están definidas por la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="b3cc1-169">Gracias a los sistemas de propiedades y eventos dinámicos que WPF proporciona, se puede ver una propiedad específica de un valor y, después, volver a aplicar el estilo de la plantilla cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="b3cc1-170">En este ejemplo, veremos la propiedad <xref:System.Windows.UIElement.IsMouseOver> del botón.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="b3cc1-171">Cuando el mouse esté sobre el control, aplique el estilo **\<Ellipse>** con un nuevo color.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="b3cc1-172">Este tipo de desencadenador se conoce como *PropertyTrigger*.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="b3cc1-173">Para que funcione, hay que agregar un nombre al elemento **\<Ellipse>** al que poder hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="b3cc1-174">Asígnele el nombre **backgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="b3cc1-175">Después, agregue un nuevo elemento <xref:System.Windows.Trigger> a la colección [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers).</span><span class="sxs-lookup"><span data-stu-id="b3cc1-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="b3cc1-176">El desencadenador inspeccionará el evento `IsMouseOver` en busca del valor `true`.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="b3cc1-177">Después, agregue un elemento **\<Setter>** al elemento **\<Trigger>** , que cambia la propiedad **Fill** de **\<Ellipse>** a un nuevo color.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="b3cc1-178">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-178">Run the project.</span></span> <span data-ttu-id="b3cc1-179">Fíjese en que, al mover el mouse por el botón, el color de **\<Ellipse>** cambia.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![El ratón se mueve por el botón de WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="b3cc1-181">Uso de un elemento VisualState</span><span class="sxs-lookup"><span data-stu-id="b3cc1-181">Use a VisualState</span></span>

<span data-ttu-id="b3cc1-182">Los estados visuales se definen y desencadenan a través de un control.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="b3cc1-183">Por ejemplo, cuando el ratón se mueve por el control, se desencadena el estado `CommonStates.MouseOver`.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="b3cc1-184">Los cambios de propiedad se pueden animar en función del estado actual del control.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="b3cc1-185">En la sección anterior, usamos un elemento **\<PropertyTrigger>** para cambiar el primer plano del botón a `AliceBlue` cuando la propiedad `IsMouseOver` era `true`.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="b3cc1-186">Esta vez, cree un estado visual que anime el cambio de este color a través de una transición suave.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="b3cc1-187">Para más información sobre los elementos *VisualState*, vea [Estilos y plantillas en WPF](../fundamentals/styles-templates-overview.md#visual-states).</span><span class="sxs-lookup"><span data-stu-id="b3cc1-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="b3cc1-188">Para convertir **\<PropertyTrigger>** a un estado visual animado, quite en primer lugar el elemento **\<ControlTemplate.Triggers>** de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="b3cc1-189">A continuación, en la raíz **\<Grid>** de la plantilla de control, agregue el elemento **\<VisualStateManager.VisualStateGroups>** con un **\<VisualStateGroup>** para `CommonStates`.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="b3cc1-190">Defina dos estados, `Normal` y `MouseOver`.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="b3cc1-191">Cuando ese estado se desencadene, se aplicarán las animaciones definidas en el elemento **\<VisualState>** .</span><span class="sxs-lookup"><span data-stu-id="b3cc1-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="b3cc1-192">Cree animaciones para cada estado.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-192">Create animations for each state.</span></span> <span data-ttu-id="b3cc1-193">Las animaciones se colocan en un elemento **\<Storyboard>** .</span><span class="sxs-lookup"><span data-stu-id="b3cc1-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="b3cc1-194">Para obtener más información sobre los guiones gráficos, vea [Información general sobre guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b3cc1-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="b3cc1-195">Normal</span><span class="sxs-lookup"><span data-stu-id="b3cc1-195">Normal</span></span>

  <span data-ttu-id="b3cc1-196">Este estado anima el relleno de la elipse y lo restaura al color `Background` del control.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="b3cc1-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b3cc1-197">MouseOver</span></span>

  <span data-ttu-id="b3cc1-198">Este estado anima el color `Background` de la elipse hacia un nuevo color: `Yellow`.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="b3cc1-199">**\<ControlTemplate>** debería tener ahora un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="b3cc1-200">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-200">Run the project.</span></span> <span data-ttu-id="b3cc1-201">Fíjese en que, al mover el mouse por el botón, el color de **\<Ellipse>** se cobra movimiento.</span><span class="sxs-lookup"><span data-stu-id="b3cc1-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![El ratón se mueve por el botón de WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="b3cc1-203">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b3cc1-203">Next steps</span></span>

- [<span data-ttu-id="b3cc1-204">Creación de un estilo de un control en WPF</span><span class="sxs-lookup"><span data-stu-id="b3cc1-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="b3cc1-205">Estilos y plantillas en WPF</span><span class="sxs-lookup"><span data-stu-id="b3cc1-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="b3cc1-206">Información general de los recursos XAML</span><span class="sxs-lookup"><span data-stu-id="b3cc1-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
