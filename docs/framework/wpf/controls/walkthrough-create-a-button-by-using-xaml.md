---
title: 'Tutorial: Crear un botón mediante el uso de XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646476"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="ffedf-102">Tutorial: Crear un botón mediante el uso de XAML</span><span class="sxs-lookup"><span data-stu-id="ffedf-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="ffedf-103">El objetivo de este tutorial es aprender a crear un botón animado para su uso en una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ffedf-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="ffedf-104">Este tutorial usa estilos y una plantilla para crear un recurso de botón personalizado que permite la reutilización del código y la separación de la lógica de botón de la declaración de botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="ffedf-105">Este tutorial está escrito [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]completamente en .</span><span class="sxs-lookup"><span data-stu-id="ffedf-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffedf-106">Este tutorial le guía a través de los pasos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para crear la aplicación escribiendo o copiando y pegando en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffedf-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="ffedf-107">Si prefiere aprender a usar un diseñador para crear la misma aplicación, consulte [Crear un botón mediante Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="ffedf-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="ffedf-108">La figura siguiente muestra los botones terminados.</span><span class="sxs-lookup"><span data-stu-id="ffedf-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="ffedf-109">![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="ffedf-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="ffedf-110">Crear botones básicos</span><span class="sxs-lookup"><span data-stu-id="ffedf-110">Create Basic Buttons</span></span>

<span data-ttu-id="ffedf-111">Comencemos creando un nuevo proyecto y agregando algunos botones a la ventana.</span><span class="sxs-lookup"><span data-stu-id="ffedf-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="ffedf-112">Para crear un nuevo proyecto WPF y agregar botones a la ventana</span><span class="sxs-lookup"><span data-stu-id="ffedf-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="ffedf-113">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffedf-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="ffedf-114">**Cree un nuevo proyecto WPF:** En el menú **Archivo,** seleccione **Nuevo**y, a continuación, haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ffedf-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="ffedf-115">Busque la plantilla **Aplicación de Windows (WPF)** y asigne al proyecto el nombre "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="ffedf-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="ffedf-116">Esto creará el esqueleto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ffedf-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="ffedf-117">**Añadir botones predeterminados básicos:** La plantilla proporciona todos los archivos que necesita para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ffedf-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="ffedf-118">Abra el archivo Window1.xaml haciendo doble clic en él en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="ffedf-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="ffedf-119">De forma predeterminada, <xref:System.Windows.Controls.Grid> hay un elemento en Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="ffedf-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="ffedf-120">Quite <xref:System.Windows.Controls.Grid> el elemento y agregue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] algunos botones a la página escribiendo o copiando y pegando el siguiente código resaltado en Window1.xaml:</span><span class="sxs-lookup"><span data-stu-id="ffedf-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="ffedf-121">Presione F5 para ejecutar la aplicación; debería ver un conjunto de botones que se parece a la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="ffedf-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="ffedf-122">![Tres botones básicos](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="ffedf-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="ffedf-123">Ahora que ha creado los botones básicos, ha terminado de trabajar en el archivo Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="ffedf-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="ffedf-124">El resto del tutorial se centra en el archivo app.xaml, definiendo estilos y una plantilla para los botones.</span><span class="sxs-lookup"><span data-stu-id="ffedf-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="ffedf-125">Establecer propiedades básicas</span><span class="sxs-lookup"><span data-stu-id="ffedf-125">Set Basic Properties</span></span>

<span data-ttu-id="ffedf-126">A continuación, vamos a establecer algunas propiedades en estos botones para controlar la apariencia y el diseño del botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="ffedf-127">En lugar de establecer propiedades en los botones individualmente, usará recursos para definir propiedades de botón para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ffedf-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="ffedf-128">Los recursos de aplicación son conceptualmente similares a las hojas de estilos en cascada (CSS) externas para páginas Web; sin embargo, los recursos son mucho más eficaces que las hojas de estilos en cascada (CSS), como verá al final de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ffedf-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="ffedf-129">Para obtener más información sobre los recursos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="ffedf-129">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="ffedf-130">Usar estilos para establecer propiedades básicas en los botones</span><span class="sxs-lookup"><span data-stu-id="ffedf-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="ffedf-131">**Defina un bloque Application.Resources:** Abra app.xaml y agregue el siguiente marcado resaltado si aún no está allí:</span><span class="sxs-lookup"><span data-stu-id="ffedf-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="ffedf-132">El ámbito de recursos viene determinado por el lugar donde se define el recurso.</span><span class="sxs-lookup"><span data-stu-id="ffedf-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="ffedf-133">La definición `Application.Resources` de recursos en el archivo app.xaml permite usar el recurso desde cualquier lugar de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ffedf-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="ffedf-134">Para obtener más información sobre cómo definir el ámbito de los recursos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="ffedf-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="ffedf-135">**Cree un estilo y defina valores de propiedad básicos con él:** Agregue el siguiente `Application.Resources` marcado al bloque.</span><span class="sxs-lookup"><span data-stu-id="ffedf-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="ffedf-136">Este marcado <xref:System.Windows.Style> crea un que se aplica a <xref:System.Windows.FrameworkElement.Width%2A> todos los botones <xref:System.Windows.FrameworkElement.Margin%2A> de la aplicación, estableciendo los botones en 90 y 10:</span><span class="sxs-lookup"><span data-stu-id="ffedf-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="ffedf-137">La <xref:System.Windows.Style.TargetType%2A> propiedad especifica que el estilo se <xref:System.Windows.Controls.Button>aplica a todos los objetos de tipo .</span><span class="sxs-lookup"><span data-stu-id="ffedf-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="ffedf-138">Cada <xref:System.Windows.Setter> uno establece un <xref:System.Windows.Style>valor de propiedad diferente para el archivo .</span><span class="sxs-lookup"><span data-stu-id="ffedf-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="ffedf-139">Por lo tanto, en este punto cada botón de la aplicación tiene un ancho de 90 y un margen de 10.</span><span class="sxs-lookup"><span data-stu-id="ffedf-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="ffedf-140">Si presiona F5 para ejecutar la aplicación, verá la siguiente ventana.</span><span class="sxs-lookup"><span data-stu-id="ffedf-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="ffedf-141">![Botones con un ancho de 90 y un margen de 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="ffedf-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="ffedf-142">Hay mucho más que puede hacer con los estilos, incluida una variedad de formas de ajustar los objetos de destino, especificar valores de propiedad complejos e incluso usar estilos como entrada para otros estilos.</span><span class="sxs-lookup"><span data-stu-id="ffedf-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="ffedf-143">Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ffedf-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="ffedf-144">Establezca un valor de propiedad de estilo en **un recurso:** Los recursos permiten una forma sencilla de reutilizar los objetos y valores definidos con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="ffedf-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="ffedf-145">Es especialmente útil definir valores complejos mediante recursos para que el código sea más modular.</span><span class="sxs-lookup"><span data-stu-id="ffedf-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="ffedf-146">Agregue el siguiente marcado resaltado a app.xaml.</span><span class="sxs-lookup"><span data-stu-id="ffedf-146">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="ffedf-147">Directamente `Application.Resources` debajo del bloque, ha creado un recurso denominado "GrayBlueGradientBrush".</span><span class="sxs-lookup"><span data-stu-id="ffedf-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="ffedf-148">Este recurso define un degradado horizontal.</span><span class="sxs-lookup"><span data-stu-id="ffedf-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="ffedf-149">Este recurso se puede usar como un valor de propiedad desde cualquier <xref:System.Windows.Controls.Control.Background%2A> lugar de la aplicación, incluido dentro del establecedor de estilo de botón para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ffedf-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="ffedf-150">Ahora, todos los <xref:System.Windows.Controls.Control.Background%2A> botones tienen un valor de propiedad de este degradado.</span><span class="sxs-lookup"><span data-stu-id="ffedf-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="ffedf-151">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ffedf-151">Press F5 to run the application.</span></span> <span data-ttu-id="ffedf-152">Debería parecerse a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ffedf-152">It should look like the following.</span></span>

     <span data-ttu-id="ffedf-153">![Botones con un fondo degradado](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="ffedf-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="ffedf-154">Crear una plantilla que defina el aspecto del botón</span><span class="sxs-lookup"><span data-stu-id="ffedf-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="ffedf-155">En esta sección, creará una plantilla que personalice la apariencia (presentación) del botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="ffedf-156">La presentación del botón se compone de varios objetos, incluidos rectángulos y otros componentes para dar al botón un aspecto único.</span><span class="sxs-lookup"><span data-stu-id="ffedf-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="ffedf-157">Hasta ahora, el control de cómo se ven los botones en la aplicación se ha limitado a cambiar las propiedades del botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="ffedf-158">¿Qué pasa si quieres hacer cambios más radicales en la apariencia del botón?</span><span class="sxs-lookup"><span data-stu-id="ffedf-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="ffedf-159">Las plantillas permiten un control eficaz sobre la presentación de un objeto.</span><span class="sxs-lookup"><span data-stu-id="ffedf-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="ffedf-160">Dado que las plantillas se pueden usar dentro de estilos, puede aplicar una plantilla a todos los objetos a los que se aplica el estilo (en este tutorial, el botón).</span><span class="sxs-lookup"><span data-stu-id="ffedf-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="ffedf-161">Utilizar la plantilla para definir el aspecto del botón</span><span class="sxs-lookup"><span data-stu-id="ffedf-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="ffedf-162">**Configure la plantilla:** Dado que <xref:System.Windows.Controls.Button> los <xref:System.Windows.Controls.Control.Template%2A> controles como tienen una propiedad, puede definir el valor <xref:System.Windows.Style> de <xref:System.Windows.Setter>propiedad de plantilla al igual que los otros valores de propiedad que hemos establecido en un using a .</span><span class="sxs-lookup"><span data-stu-id="ffedf-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="ffedf-163">Agregue el siguiente marcado resaltado al estilo de botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-163">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="ffedf-164">**Modificar la presentación del botón:** En este punto, debe definir la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ffedf-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="ffedf-165">Agregue el siguiente marcado resaltado.</span><span class="sxs-lookup"><span data-stu-id="ffedf-165">Add the following highlighted markup.</span></span> <span data-ttu-id="ffedf-166">Este marcado especifica <xref:System.Windows.Shapes.Rectangle> dos elementos con <xref:System.Windows.Controls.DockPanel>bordes redondeados, seguidos de un archivo .</span><span class="sxs-lookup"><span data-stu-id="ffedf-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="ffedf-167">Se <xref:System.Windows.Controls.DockPanel> utiliza para <xref:System.Windows.Controls.ContentPresenter> alojar el botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="ffedf-168">A <xref:System.Windows.Controls.ContentPresenter> muestra el contenido del botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="ffedf-169">En este tutorial, el contenido es texto ("Botón 1", "Botón 2", "Botón 3").</span><span class="sxs-lookup"><span data-stu-id="ffedf-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="ffedf-170">Todos los componentes de la <xref:System.Windows.Controls.DockPanel>plantilla (los rectángulos <xref:System.Windows.Controls.Grid>y el ) se colocan dentro de un archivo .</span><span class="sxs-lookup"><span data-stu-id="ffedf-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="ffedf-171">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ffedf-171">Press F5 to run the application.</span></span> <span data-ttu-id="ffedf-172">Debería parecerse a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ffedf-172">It should look like the following.</span></span>

     ![Ventana con 3 botones](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="ffedf-174">**Agregue un efecto de vidrio a la plantilla:** A continuación, añadirá el vidrio.</span><span class="sxs-lookup"><span data-stu-id="ffedf-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="ffedf-175">En primer lugar, cree algunos recursos que creen un efecto de degradado de vidrio.</span><span class="sxs-lookup"><span data-stu-id="ffedf-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="ffedf-176">Agregue estos recursos de `Application.Resources` degradado en cualquier lugar dentro del bloque:</span><span class="sxs-lookup"><span data-stu-id="ffedf-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="ffedf-177">Estos recursos se <xref:System.Windows.Shapes.Shape.Fill%2A> utilizan como para un <xref:System.Windows.Controls.Grid> rectángulo que insertamos en la plantilla de botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="ffedf-178">Agregue el siguiente marcado resaltado a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ffedf-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="ffedf-179">Observe que <xref:System.Windows.UIElement.Opacity%2A> el rectángulo `x:Name` del rectángulo con la propiedad de "glassCube" es 0, por lo que al ejecutar la muestra, no verá el rectángulo de vidrio superpuesto en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="ffedf-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="ffedf-180">Esto se debe a que más adelante agregaremos desencadenadores a la plantilla para cuando el usuario interactúe con el botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="ffedf-181">Sin embargo, puede ver cómo se <xref:System.Windows.UIElement.Opacity%2A> ve el botón ahora cambiando el valor a 1 y ejecutando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ffedf-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="ffedf-182">Consulte la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="ffedf-182">See the following figure.</span></span> <span data-ttu-id="ffedf-183">Antes de continuar con el <xref:System.Windows.UIElement.Opacity%2A> paso siguiente, cambie la parte posterior a 0.</span><span class="sxs-lookup"><span data-stu-id="ffedf-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="ffedf-184">![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="ffedf-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="ffedf-185">Crear interactividad de botones</span><span class="sxs-lookup"><span data-stu-id="ffedf-185">Create Button Interactivity</span></span>

<span data-ttu-id="ffedf-186">En esta sección, creará desencadenadores de propiedades y desencadenadores de eventos para cambiar los valores de propiedad y ejecutar animaciones en respuesta a acciones del usuario, como mover el puntero del mouse sobre el botón y hacer clic.</span><span class="sxs-lookup"><span data-stu-id="ffedf-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="ffedf-187">Una manera fácil de agregar interactividad (ratón sobre, mouse-leave, clic, etc.) es definir desencadenadores dentro de su plantilla o estilo.</span><span class="sxs-lookup"><span data-stu-id="ffedf-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="ffedf-188">Para crear <xref:System.Windows.Trigger>un , se define una propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> "condición" `true`como: El valor de la propiedad button es igual a .</span><span class="sxs-lookup"><span data-stu-id="ffedf-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="ffedf-189">A continuación, defina los establecedores (acciones) que tienen lugar cuando la condición de desencadenador es true.</span><span class="sxs-lookup"><span data-stu-id="ffedf-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="ffedf-190">Para crear interactividad de botones</span><span class="sxs-lookup"><span data-stu-id="ffedf-190">To create button interactivity</span></span>

1. <span data-ttu-id="ffedf-191">**Agregar desencadenadores de plantilla:** Agregue el marcado resaltado a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ffedf-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="ffedf-192">**Agregar desencadenadores** de propiedad: Agregue el marcado resaltado `ControlTemplate.Triggers` al bloque:</span><span class="sxs-lookup"><span data-stu-id="ffedf-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="ffedf-193">Presione F5 para ejecutar la aplicación y ver el efecto al ejecutar el puntero del ratón sobre los botones.</span><span class="sxs-lookup"><span data-stu-id="ffedf-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="ffedf-194">**Agregue un desencadenador** de foco: A continuación, agregaremos algunos establecedores similares para controlar el caso cuando el botón tenga el foco (por ejemplo, después de que el usuario haga clic en él).</span><span class="sxs-lookup"><span data-stu-id="ffedf-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="ffedf-195">Presione F5 para ejecutar la aplicación y haga clic en uno de los botones.</span><span class="sxs-lookup"><span data-stu-id="ffedf-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="ffedf-196">Tenga en cuenta que el botón permanece resaltado después de hacer clic en él porque todavía tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="ffedf-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="ffedf-197">Si hace clic en otro botón, el nuevo botón gana el foco mientras que el último lo pierde.</span><span class="sxs-lookup"><span data-stu-id="ffedf-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="ffedf-198">**Añadir animaciones para** <xref:System.Windows.UIElement.MouseEnter> **y** <xref:System.Windows.UIElement.MouseLeave> **:** A continuación, añadimos algunas animaciones a los desencadenadores.  </span><span class="sxs-lookup"><span data-stu-id="ffedf-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="ffedf-199">Agregue el siguiente marcado `ControlTemplate.Triggers` en cualquier lugar dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="ffedf-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="ffedf-200">El rectángulo de vidrio se reduce cuando el puntero del mouse se mueve sobre el botón y vuelve al tamaño normal cuando el puntero sale.</span><span class="sxs-lookup"><span data-stu-id="ffedf-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="ffedf-201">Hay dos animaciones que se desencadenan cuando<xref:System.Windows.UIElement.MouseEnter> el puntero pasa por encima del botón (se genera el evento).</span><span class="sxs-lookup"><span data-stu-id="ffedf-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="ffedf-202">Estas animaciones reducen el rectángulo de cristal a lo largo del eje X e Y.</span><span class="sxs-lookup"><span data-stu-id="ffedf-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="ffedf-203">Observe las propiedades <xref:System.Windows.Media.Animation.DoubleAnimation> de <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>los elementos y .</span><span class="sxs-lookup"><span data-stu-id="ffedf-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="ffedf-204">Especifica <xref:System.Windows.Media.Animation.Timeline.Duration%2A> que la animación se produce <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> durante medio segundo y especifica que el vidrio se reduce en un 10%.</span><span class="sxs-lookup"><span data-stu-id="ffedf-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="ffedf-205">El segundo desencadenador<xref:System.Windows.UIElement.MouseLeave>de evento ( ) simplemente detiene el primero.</span><span class="sxs-lookup"><span data-stu-id="ffedf-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="ffedf-206">Cuando se <xref:System.Windows.Media.Animation.Storyboard>detiene un , todas las propiedades animadas vuelven a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="ffedf-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="ffedf-207">Por lo tanto, cuando el usuario mueve el puntero fuera del botón, el botón vuelve a la forma en que estaba antes de que el puntero del mouse se moviera sobre el botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="ffedf-208">Para obtener más información acerca de las animaciones, vea [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ffedf-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="ffedf-209">**Agregue una animación para cuando se haga clic en el botón:** El último paso es agregar un desencadenador para cuando el usuario hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="ffedf-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="ffedf-210">Agregue el siguiente marcado `ControlTemplate.Triggers` en cualquier lugar dentro del bloque:</span><span class="sxs-lookup"><span data-stu-id="ffedf-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="ffedf-211">Presione F5 para ejecutar la aplicación y haga clic en uno de los botones.</span><span class="sxs-lookup"><span data-stu-id="ffedf-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="ffedf-212">Al hacer clic en un botón, el rectángulo de vidrio gira alrededor.</span><span class="sxs-lookup"><span data-stu-id="ffedf-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="ffedf-213">Resumen</span><span class="sxs-lookup"><span data-stu-id="ffedf-213">Summary</span></span>
 <span data-ttu-id="ffedf-214">En este tutorial, ha realizado los siguientes ejercicios:</span><span class="sxs-lookup"><span data-stu-id="ffedf-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="ffedf-215">Dirigido <xref:System.Windows.Style> a un tipo<xref:System.Windows.Controls.Button>de objeto ( ).</span><span class="sxs-lookup"><span data-stu-id="ffedf-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="ffedf-216">Propiedades básicas controladas de los botones de toda la aplicación mediante el <xref:System.Windows.Style>archivo .</span><span class="sxs-lookup"><span data-stu-id="ffedf-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="ffedf-217">Se han creado recursos como degradados <xref:System.Windows.Style> que se usan para los valores de propiedad de los establecedores.</span><span class="sxs-lookup"><span data-stu-id="ffedf-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="ffedf-218">Se ha personalizado el aspecto de los botones de toda la aplicación aplicando una plantilla a los botones.</span><span class="sxs-lookup"><span data-stu-id="ffedf-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="ffedf-219">Comportamiento personalizado de los botones en <xref:System.Windows.UIElement.MouseEnter>respuesta <xref:System.Windows.UIElement.MouseLeave>a <xref:System.Windows.Controls.Primitives.ButtonBase.Click>las acciones del usuario (como , , y ) que incluían efectos de animación.</span><span class="sxs-lookup"><span data-stu-id="ffedf-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffedf-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ffedf-220">See also</span></span>

- [<span data-ttu-id="ffedf-221">Crear un botón mediante Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="ffedf-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="ffedf-222">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="ffedf-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ffedf-223">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="ffedf-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="ffedf-224">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="ffedf-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="ffedf-225">Información general sobre efectos de imagen</span><span class="sxs-lookup"><span data-stu-id="ffedf-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
