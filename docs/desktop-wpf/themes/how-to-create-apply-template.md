---
title: Crear una plantilla en WPF - .NET Desktop
description: Aprenda a crear y hacer referencia a una plantilla de control en Windows Presentation Foundation y .NET Core.
author: thraka
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
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432543"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="8c343-103">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="8c343-103">Create a template for a control</span></span>

<span data-ttu-id="8c343-104">Con Windows Presentation Foundation (WPF), puede personalizar la estructura visual y el comportamiento de un control existente con su propia plantilla reutilizable.</span><span class="sxs-lookup"><span data-stu-id="8c343-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="8c343-105">Las plantillas se pueden aplicar globalmente a la aplicación, ventanas y páginas, o directamente a los controles.</span><span class="sxs-lookup"><span data-stu-id="8c343-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="8c343-106">La mayoría de los escenarios que requieren que cree un nuevo control se pueden cubrir creando en su lugar una nueva plantilla para un control existente.</span><span class="sxs-lookup"><span data-stu-id="8c343-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="8c343-107">En este artículo, explorará la <xref:System.Windows.Controls.ControlTemplate> creación <xref:System.Windows.Controls.Button> de un nuevo para el control.</span><span class="sxs-lookup"><span data-stu-id="8c343-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="8c343-108">Cuándo crear un ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8c343-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="8c343-109">Los controles tienen muchas <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.Control.Foreground%2A>propiedades, <xref:System.Windows.Controls.Control.FontFamily%2A>como , , y .</span><span class="sxs-lookup"><span data-stu-id="8c343-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="8c343-110">Estas propiedades controlan diferentes aspectos de la apariencia del control, pero los cambios que puede realizar estableciendo estas propiedades son limitados.</span><span class="sxs-lookup"><span data-stu-id="8c343-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="8c343-111">Por ejemplo, puede <xref:System.Windows.Controls.Control.Foreground%2A> establecer la <xref:System.Windows.Controls.Control.FontStyle%2A> propiedad en <xref:System.Windows.Controls.CheckBox>azul y en cursiva en un archivo .</span><span class="sxs-lookup"><span data-stu-id="8c343-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="8c343-112">Si desea personalizar la apariencia del control más allá de lo que puede <xref:System.Windows.Controls.ControlTemplate>hacer la configuración de las otras propiedades del control, cree un archivo .</span><span class="sxs-lookup"><span data-stu-id="8c343-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="8c343-113">En la mayoría de las interfaces de usuario, un botón tiene la misma apariencia general: un rectángulo con algún texto.</span><span class="sxs-lookup"><span data-stu-id="8c343-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="8c343-114">Si desea crear un botón redondeado, puede crear un nuevo control que herede del botón o volver a crear la funcionalidad del botón.</span><span class="sxs-lookup"><span data-stu-id="8c343-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="8c343-115">Además, el nuevo control de usuario proporcionaría el objeto visual circular.</span><span class="sxs-lookup"><span data-stu-id="8c343-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="8c343-116">Puede evitar la creación de nuevos controles personalizando el diseño visual de un control existente.</span><span class="sxs-lookup"><span data-stu-id="8c343-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="8c343-117">Con un botón redondeado, se crea un <xref:System.Windows.Controls.ControlTemplate> diseño visual con el diseño visual deseado.</span><span class="sxs-lookup"><span data-stu-id="8c343-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="8c343-118">Por otro lado, si necesita un control con nueva funcionalidad, propiedades diferentes y <xref:System.Windows.Controls.UserControl>nueva configuración, crearía un nuevo archivo .</span><span class="sxs-lookup"><span data-stu-id="8c343-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c343-119">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="8c343-119">Prerequisites</span></span>

<span data-ttu-id="8c343-120">Cree una nueva aplicación WPF y en *MainWindow.xaml* (u otra ventana \*\* \<\*\* de su elección) establezca las siguientes propiedades en el elemento>Window:</span><span class="sxs-lookup"><span data-stu-id="8c343-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="8c343-121">Establezca el contenido del elemento \*\* \<Window>\*\* en el siguiente XAML:</span><span class="sxs-lookup"><span data-stu-id="8c343-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="8c343-122">Al final, el archivo *MainWindow.xaml* debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8c343-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="8c343-123">Si ejecuta la aplicación, tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="8c343-123">If you run the application, it looks like the following:</span></span>

![Ventana WPF con dos botones sin estilo](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="8c343-125">Creación de una clase ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="8c343-125">Create a ControlTemplate</span></span>

<span data-ttu-id="8c343-126">La forma más común <xref:System.Windows.Controls.ControlTemplate> de declarar a `Resources` es como un recurso en la sección de un archivo XAML.</span><span class="sxs-lookup"><span data-stu-id="8c343-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="8c343-127">Dado que las plantillas son recursos, obedecen las mismas reglas de ámbito que se aplican a todos los recursos.</span><span class="sxs-lookup"><span data-stu-id="8c343-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="8c343-128">En pocas palabras, donde se declara una plantilla afecta a dónde se puede aplicar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8c343-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="8c343-129">Por ejemplo, si declara la plantilla en el elemento raíz del archivo XAML de definición de aplicación, la plantilla se puede usar en cualquier lugar de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8c343-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="8c343-130">Si define la plantilla en una ventana, solo los controles de esa ventana pueden usar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8c343-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="8c343-131">Para empezar, agregue `Window.Resources` un elemento al archivo *MainWindow.xaml:*</span><span class="sxs-lookup"><span data-stu-id="8c343-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="8c343-132">Cree un nuevo \*\* \<>ControlTemplate\*\* con las siguientes propiedades establecidas:</span><span class="sxs-lookup"><span data-stu-id="8c343-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="8c343-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="8c343-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="8c343-134">Esta plantilla de control será simple:</span><span class="sxs-lookup"><span data-stu-id="8c343-134">This control template will be simple:</span></span>

- <span data-ttu-id="8c343-135">un elemento raíz para el control, un<xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="8c343-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="8c343-136">y <xref:System.Windows.Shapes.Ellipse> dibujar la apariencia redondeada del botón</span><span class="sxs-lookup"><span data-stu-id="8c343-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="8c343-137"><xref:System.Windows.Controls.ContentPresenter> a para mostrar el contenido del botón especificado por el usuario</span><span class="sxs-lookup"><span data-stu-id="8c343-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="8c343-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="8c343-138">TemplateBinding</span></span>

<span data-ttu-id="8c343-139">Al crear un <xref:System.Windows.Controls.ControlTemplate>nuevo , es posible que desee usar las propiedades públicas para cambiar la apariencia del control.</span><span class="sxs-lookup"><span data-stu-id="8c343-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="8c343-140">El [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) extensión de marcado enlaza una propiedad <xref:System.Windows.Controls.ControlTemplate> de un elemento que se encuentra en el a una propiedad pública definida por el control.</span><span class="sxs-lookup"><span data-stu-id="8c343-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="8c343-141">Cuando se usa [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), se habilitan las propiedades del control para que actúen como parámetros de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8c343-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="8c343-142">Es decir, cuando se establece una propiedad de un control, ese valor se pasa al elemento que tiene la extensión [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="8c343-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="8c343-143">Elipse</span><span class="sxs-lookup"><span data-stu-id="8c343-143">Ellipse</span></span>

<span data-ttu-id="8c343-144">Observe que **:::no-loc text="Fill":::** **:::no-loc text="Stroke":::** las propiedades y del \*\* \<elemento de>\*\* <xref:System.Windows.Controls.Control.Background> Ellipse están enlazadas a las propiedades y propiedades del <xref:System.Windows.Controls.Control.Foreground> control.</span><span class="sxs-lookup"><span data-stu-id="8c343-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="8c343-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="8c343-145">ContentPresenter</span></span>

<span data-ttu-id="8c343-146">Un [ \<Elemento de>ContentPresenter](xref:System.Windows.Controls.ContentPresenter) también se agrega a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8c343-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="8c343-147">Dado que esta plantilla está diseñada para un botón, tenga en cuenta que el botón hereda de <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="8c343-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="8c343-148">El botón presenta el contenido del elemento.</span><span class="sxs-lookup"><span data-stu-id="8c343-148">The button presents the content of the element.</span></span> <span data-ttu-id="8c343-149">Puede establecer cualquier cosa dentro del botón, como texto sin formato o incluso otro control.</span><span class="sxs-lookup"><span data-stu-id="8c343-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="8c343-150">Ambos de los siguientes son botones válidos:</span><span class="sxs-lookup"><span data-stu-id="8c343-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="8c343-151">En los dos ejemplos anteriores, el texto y la casilla de verificación se establecen como la propiedad [Button.Content.](xref:System.Windows.Controls.ContentControl.Content)</span><span class="sxs-lookup"><span data-stu-id="8c343-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="8c343-152">Lo que se establece como el contenido se puede presentar a través de un \*\* \<ContentPresenter>\*\*, que es lo que hace la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8c343-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="8c343-153">Si <xref:System.Windows.Controls.ControlTemplate> se aplica <xref:System.Windows.Controls.ContentControl> a un tipo, como un `Button`, <xref:System.Windows.Controls.ContentPresenter> se busca en el árbol de elementos.</span><span class="sxs-lookup"><span data-stu-id="8c343-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="8c343-154">Si `ContentPresenter` se encuentra, la plantilla enlaza automáticamente <xref:System.Windows.Controls.ContentControl.Content> la `ContentPresenter`propiedad del control a la .</span><span class="sxs-lookup"><span data-stu-id="8c343-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="8c343-155">Uso de la plantilla</span><span class="sxs-lookup"><span data-stu-id="8c343-155">Use the template</span></span>

<span data-ttu-id="8c343-156">Busque los botones que se declararon al principio de este artículo.</span><span class="sxs-lookup"><span data-stu-id="8c343-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="8c343-157">Establezca la propiedad <xref:System.Windows.Controls.Control.Template> del segundo `roundbutton` botón en el recurso:</span><span class="sxs-lookup"><span data-stu-id="8c343-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="8c343-158">Si ejecuta el proyecto y observa el resultado, verá que el botón tiene un fondo redondeado.</span><span class="sxs-lookup"><span data-stu-id="8c343-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![Ventana WPF con un botón ovalado de plantilla](media/create-apply-template/styled-button.png)

<span data-ttu-id="8c343-160">Es posible que haya notado que el botón no es un círculo, pero está sesgado.</span><span class="sxs-lookup"><span data-stu-id="8c343-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="8c343-161">Debido a la forma en que funciona el \*\* \<elemento elipse>,\*\* siempre se expande para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="8c343-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="8c343-162">Haga que el círculo sea **:::no-loc text="width":::** uniforme **:::no-loc text="height":::** cambiando las propiedades y el botón al mismo valor:</span><span class="sxs-lookup"><span data-stu-id="8c343-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Ventana WPF con un botón circular de plantilla](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="8c343-164">Añadir un disparador</span><span class="sxs-lookup"><span data-stu-id="8c343-164">Add a Trigger</span></span>

<span data-ttu-id="8c343-165">Aunque un botón con una plantilla aplicada tiene un aspecto diferente, se comporta igual que cualquier otro botón.</span><span class="sxs-lookup"><span data-stu-id="8c343-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="8c343-166">Si pulsa el botón, el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento se activa.</span><span class="sxs-lookup"><span data-stu-id="8c343-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="8c343-167">Sin embargo, es posible que haya notado que cuando mueve el ratón sobre el botón, los objetos visuales del botón no cambian.</span><span class="sxs-lookup"><span data-stu-id="8c343-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="8c343-168">Todas estas interacciones visuales se definen mediante la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8c343-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="8c343-169">Con los sistemas de propiedades y eventos dinámicos que WPFWPF proporciona, puede ver una propiedad específica para un valor y, a continuación, cambiar el estilo de la plantilla cuando corresponda.</span><span class="sxs-lookup"><span data-stu-id="8c343-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="8c343-170">En este ejemplo, verá la propiedad <xref:System.Windows.UIElement.IsMouseOver> del botón.</span><span class="sxs-lookup"><span data-stu-id="8c343-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="8c343-171">Cuando el ratón está sobre el control, el estilo de la \*\* \<Elipse>\*\* con un nuevo color.</span><span class="sxs-lookup"><span data-stu-id="8c343-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="8c343-172">Este tipo de desencadenador se conoce como *PropertyTrigger*.</span><span class="sxs-lookup"><span data-stu-id="8c343-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="8c343-173">Para que esto funcione, deberá agregar un \*\* \<\*\* nombre a la>Ellipse a la que puede hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="8c343-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="8c343-174">Asír como el nombre **backgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="8c343-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="8c343-175">A continuación, <xref:System.Windows.Trigger> agregue un nuevo a la [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) colección.</span><span class="sxs-lookup"><span data-stu-id="8c343-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="8c343-176">El desencadenador observará el `IsMouseOver` `true`evento para el valor .</span><span class="sxs-lookup"><span data-stu-id="8c343-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="8c343-177">A continuación, agregue un \*\* \<>Setter\*\* al \*\* \<desencadenador>\*\* que cambia el **Fill** propiedad de la \*\* \<Ellipse>\*\* a un nuevo color.</span><span class="sxs-lookup"><span data-stu-id="8c343-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="8c343-178">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c343-178">Run the project.</span></span> <span data-ttu-id="8c343-179">Tenga en cuenta que al mover el ratón sobre el botón, el color de la \*\* \<Elipse>\*\* cambia.</span><span class="sxs-lookup"><span data-stu-id="8c343-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![ratón se mueve sobre el botón WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="8c343-181">Usar un VisualState</span><span class="sxs-lookup"><span data-stu-id="8c343-181">Use a VisualState</span></span>

<span data-ttu-id="8c343-182">Los estados visuales se definen y desencadenan mediante un control.</span><span class="sxs-lookup"><span data-stu-id="8c343-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="8c343-183">Por ejemplo, cuando el mouse se mueve `CommonStates.MouseOver` en la parte superior del control, se desencadena el estado.</span><span class="sxs-lookup"><span data-stu-id="8c343-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="8c343-184">Puede animar los cambios de propiedad en función del estado actual del control.</span><span class="sxs-lookup"><span data-stu-id="8c343-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="8c343-185">En la sección anterior, se usaba un `AliceBlue` `IsMouseOver` `true` \*\* \<>PropertyTrigger\*\* para cambiar el primer plano del botón a cuando la propiedad era .</span><span class="sxs-lookup"><span data-stu-id="8c343-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="8c343-186">En su lugar, cree un estado visual que anime el cambio de este color, proporcionando una transición suave.</span><span class="sxs-lookup"><span data-stu-id="8c343-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="8c343-187">Para obtener más información acerca de *VisualStates*, vea [Estilos y plantillas en WPF](../fundamentals/styles-templates-overview.md#visual-states).</span><span class="sxs-lookup"><span data-stu-id="8c343-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="8c343-188">Para convertir el \*\* \<PropertyTrigger>\*\* en un estado visual animado, En primer lugar, quite el \*\* \<ControlTemplate.Triggers>\*\* elemento de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8c343-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="8c343-189">A continuación, \*\* \<\*\* en la cuadrícula>raíz de la plantilla de control, agregue el `CommonStates` \*\* \<VisualStateManager.VisualStateGroups>\*\* elemento con un \*\* \<VisualStateGroup>\*\* para .</span><span class="sxs-lookup"><span data-stu-id="8c343-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="8c343-190">Defina dos `Normal` estados `MouseOver`y .</span><span class="sxs-lookup"><span data-stu-id="8c343-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="8c343-191">Las animaciones definidas en un \*\* \<>VisualState\*\* se aplican cuando se desencadena ese estado.</span><span class="sxs-lookup"><span data-stu-id="8c343-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="8c343-192">Cree animaciones para cada estado.</span><span class="sxs-lookup"><span data-stu-id="8c343-192">Create animations for each state.</span></span> <span data-ttu-id="8c343-193">Las animaciones se colocan dentro de un \*\* \<elemento de>Storyboard.\*\*</span><span class="sxs-lookup"><span data-stu-id="8c343-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="8c343-194">Para obtener más información acerca de los guiones gráficos, vea Información general sobre [guiones gráficos](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8c343-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="8c343-195">Normal</span><span class="sxs-lookup"><span data-stu-id="8c343-195">Normal</span></span>

  <span data-ttu-id="8c343-196">Este estado anima el relleno de elipse, `Background` restableciéndolo al color del control.</span><span class="sxs-lookup"><span data-stu-id="8c343-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="8c343-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="8c343-197">MouseOver</span></span>

  <span data-ttu-id="8c343-198">Este estado anima `Background` el color de `Yellow`elipse a un nuevo color: .</span><span class="sxs-lookup"><span data-stu-id="8c343-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="8c343-199">El \*\* \<>ControlTemplate\*\* ahora debería tener el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="8c343-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="8c343-200">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8c343-200">Run the project.</span></span> <span data-ttu-id="8c343-201">Tenga en cuenta que al mover el ratón sobre el botón, el color de la \*\* \<Elipse>\*\* se anima.</span><span class="sxs-lookup"><span data-stu-id="8c343-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![ratón se mueve sobre el botón WPF para cambiar el color de relleno](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="8c343-203">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8c343-203">Next steps</span></span>

- [<span data-ttu-id="8c343-204">Crear un estilo para un control en WPFWPF</span><span class="sxs-lookup"><span data-stu-id="8c343-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="8c343-205">Estilos y plantillas en WPF</span><span class="sxs-lookup"><span data-stu-id="8c343-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="8c343-206">Descripción general de los recursos XAML</span><span class="sxs-lookup"><span data-stu-id="8c343-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
