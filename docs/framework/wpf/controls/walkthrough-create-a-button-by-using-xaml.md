---
title: 'Tutorial: Crear un botón mediante el uso de XAML'
description: Use este tutorial para aprender a crear un botón animado para usarlo en una aplicación Windows Presentation Foundation mediante XAML.
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 136d1ad5d6fefd70f0d977e5287ae75f06c52d36
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164849"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="7fefa-103">Tutorial: Crear un botón mediante el uso de XAML</span><span class="sxs-lookup"><span data-stu-id="7fefa-103">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="7fefa-104">El objetivo de este tutorial es aprender a crear un botón animado para usarlo en una aplicación Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="7fefa-104">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="7fefa-105">En este tutorial se usan estilos y una plantilla para crear un recurso de botón personalizado que permite la reutilización del código y la separación de la lógica del botón desde la declaración del botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-105">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="7fefa-106">Este tutorial se ha escrito en su totalidad en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7fefa-106">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fefa-107">Este tutorial le guía a través de los pasos necesarios para crear la aplicación escribiendo o copiando y pegando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7fefa-107">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="7fefa-108">Si prefiere obtener información sobre cómo usar un diseñador para crear la misma aplicación, vea [crear un botón mediante Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="7fefa-108">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="7fefa-109">En la ilustración siguiente se muestran los botones terminados.</span><span class="sxs-lookup"><span data-stu-id="7fefa-109">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="7fefa-110">![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="7fefa-110">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="7fefa-111">Crear botones básicos</span><span class="sxs-lookup"><span data-stu-id="7fefa-111">Create Basic Buttons</span></span>

<span data-ttu-id="7fefa-112">Comencemos por crear un nuevo proyecto y agregando algunos botones a la ventana.</span><span class="sxs-lookup"><span data-stu-id="7fefa-112">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="7fefa-113">Para crear un nuevo proyecto de WPF y agregar botones a la ventana</span><span class="sxs-lookup"><span data-stu-id="7fefa-113">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="7fefa-114">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7fefa-114">Start Visual Studio.</span></span>

2. <span data-ttu-id="7fefa-115">**Cree un nuevo proyecto de WPF:** En el menú **archivo** , seleccione **nuevo**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7fefa-115">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="7fefa-116">Busque la plantilla **aplicación para Windows (WPF)** y asigne al proyecto el nombre "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="7fefa-116">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="7fefa-117">Esto creará el esqueleto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7fefa-117">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="7fefa-118">**Agregar botones predeterminados básicos:** Todos los archivos que necesita para este tutorial se proporcionan en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7fefa-118">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="7fefa-119">Haga doble clic en el archivo Window1. XAML para abrirlo en Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="7fefa-119">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="7fefa-120">De forma predeterminada, hay un <xref:System.Windows.Controls.Grid> elemento en Window1. Xaml.</span><span class="sxs-lookup"><span data-stu-id="7fefa-120">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="7fefa-121">Quite el <xref:System.Windows.Controls.Grid> elemento y agregue algunos botones a la página; para [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ello, escriba o copie y pegue el siguiente código resaltado en Window1. XAML:</span><span class="sxs-lookup"><span data-stu-id="7fefa-121">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

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

     <span data-ttu-id="7fefa-122">Presione F5 para ejecutar la aplicación; debería ver un conjunto de botones que se parece a la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="7fefa-122">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="7fefa-123">![Tres botones básicos](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="7fefa-123">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="7fefa-124">Ahora que ha creado los botones básicos, ha terminado de trabajar en el archivo Window1. Xaml.</span><span class="sxs-lookup"><span data-stu-id="7fefa-124">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="7fefa-125">El resto del tutorial se centra en el archivo app. XAML, lo que define los estilos y una plantilla para los botones.</span><span class="sxs-lookup"><span data-stu-id="7fefa-125">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="7fefa-126">Establecer propiedades básicas</span><span class="sxs-lookup"><span data-stu-id="7fefa-126">Set Basic Properties</span></span>

<span data-ttu-id="7fefa-127">A continuación, vamos a establecer algunas propiedades en estos botones para controlar la apariencia y el diseño del botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-127">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="7fefa-128">En lugar de establecer las propiedades de los botones individualmente, usará los recursos para definir las propiedades del botón para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7fefa-128">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="7fefa-129">Los recursos de la aplicación son conceptualmente similares a los Hojas de estilo CSS externos (CSS) para las páginas Web. sin embargo, los recursos son mucho más eficaces que Hojas de estilo CSS (CSS), como verá al final de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="7fefa-129">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="7fefa-130">Para obtener más información sobre los recursos, vea [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="7fefa-130">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="7fefa-131">Para usar estilos para establecer las propiedades básicas de los botones</span><span class="sxs-lookup"><span data-stu-id="7fefa-131">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="7fefa-132">**Defina un bloque Application. Resources:** Abra app. XAML y agregue el siguiente marcado resaltado si aún no está ahí:</span><span class="sxs-lookup"><span data-stu-id="7fefa-132">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

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

     <span data-ttu-id="7fefa-133">El ámbito del recurso está determinado por la ubicación en la que se define el recurso.</span><span class="sxs-lookup"><span data-stu-id="7fefa-133">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="7fefa-134">La definición de recursos en `Application.Resources` en el archivo app. Xaml permite que el recurso se use desde cualquier parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7fefa-134">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="7fefa-135">Para obtener más información sobre cómo definir el ámbito de los recursos, vea [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="7fefa-135">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="7fefa-136">**Cree un estilo y defina los valores de propiedad básicos con él:** Agregue el marcado siguiente al `Application.Resources` bloque.</span><span class="sxs-lookup"><span data-stu-id="7fefa-136">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="7fefa-137">Este marcado crea un <xref:System.Windows.Style> que se aplica a todos los botones de la aplicación, estableciendo el <xref:System.Windows.FrameworkElement.Width%2A> de los botones en 90 y <xref:System.Windows.FrameworkElement.Margin%2A> en 10:</span><span class="sxs-lookup"><span data-stu-id="7fefa-137">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="7fefa-138">La <xref:System.Windows.Style.TargetType%2A> propiedad especifica que el estilo se aplica a todos los objetos de tipo <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="7fefa-138">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="7fefa-139">Cada <xref:System.Windows.Setter> establece un valor de propiedad diferente para <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="7fefa-139">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="7fefa-140">Por lo tanto, en este punto, cada botón de la aplicación tiene un ancho de 90 y un margen de 10.</span><span class="sxs-lookup"><span data-stu-id="7fefa-140">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="7fefa-141">Si presiona F5 para ejecutar la aplicación, verá la siguiente ventana.</span><span class="sxs-lookup"><span data-stu-id="7fefa-141">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="7fefa-142">![Botones con un ancho de 90 y un margen de 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="7fefa-142">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="7fefa-143">Hay mucho más que puede hacer con los estilos, como una variedad de formas de ajustar los objetos de destino, especificar valores de propiedad complejos e incluso usar estilos como entrada para otros estilos.</span><span class="sxs-lookup"><span data-stu-id="7fefa-143">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="7fefa-144">Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7fefa-144">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="7fefa-145">**Establezca un valor de propiedad de estilo en un recurso:** Los recursos permiten una forma sencilla de reutilizar objetos y valores definidos comúnmente.</span><span class="sxs-lookup"><span data-stu-id="7fefa-145">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="7fefa-146">Es especialmente útil definir valores complejos mediante recursos para que el código sea más modular.</span><span class="sxs-lookup"><span data-stu-id="7fefa-146">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="7fefa-147">Agregue el siguiente marcado resaltado a app. Xaml.</span><span class="sxs-lookup"><span data-stu-id="7fefa-147">Add the following highlighted markup to app.xaml.</span></span>

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

     <span data-ttu-id="7fefa-148">Directamente en el `Application.Resources` bloque, ha creado un recurso denominado "GrayBlueGradientBrush".</span><span class="sxs-lookup"><span data-stu-id="7fefa-148">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="7fefa-149">Este recurso define un degradado horizontal.</span><span class="sxs-lookup"><span data-stu-id="7fefa-149">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="7fefa-150">Este recurso se puede usar como un valor de propiedad desde cualquier parte de la aplicación, incluso dentro del establecedor de estilo de botón para la <xref:System.Windows.Controls.Control.Background%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7fefa-150">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="7fefa-151">Ahora, todos los botones tienen un <xref:System.Windows.Controls.Control.Background%2A> valor de propiedad de este degradado.</span><span class="sxs-lookup"><span data-stu-id="7fefa-151">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="7fefa-152">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7fefa-152">Press F5 to run the application.</span></span> <span data-ttu-id="7fefa-153">Debería tener un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="7fefa-153">It should look like the following.</span></span>

     <span data-ttu-id="7fefa-154">![Botones con un fondo degradado](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="7fefa-154">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="7fefa-155">Crear una plantilla que defina el aspecto del botón</span><span class="sxs-lookup"><span data-stu-id="7fefa-155">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="7fefa-156">En esta sección, creará una plantilla que personaliza la apariencia (presentación) del botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-156">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="7fefa-157">La presentación del botón se compone de varios objetos, incluidos los rectángulos y otros componentes, para dar al botón una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="7fefa-157">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="7fefa-158">Hasta ahora, el control de cómo se muestran los botones en la aplicación se ha limitado a cambiar las propiedades del botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-158">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="7fefa-159">¿Qué ocurre si desea realizar cambios más radicales en la apariencia del botón?</span><span class="sxs-lookup"><span data-stu-id="7fefa-159">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="7fefa-160">Las plantillas permiten un control eficaz sobre la presentación de un objeto.</span><span class="sxs-lookup"><span data-stu-id="7fefa-160">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="7fefa-161">Dado que las plantillas se pueden usar dentro de los estilos, puede aplicar una plantilla a todos los objetos a los que se aplica el estilo (en este tutorial, el botón).</span><span class="sxs-lookup"><span data-stu-id="7fefa-161">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="7fefa-162">Para usar la plantilla para definir el aspecto del botón</span><span class="sxs-lookup"><span data-stu-id="7fefa-162">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="7fefa-163">**Configure la plantilla:** Dado que los controles como <xref:System.Windows.Controls.Button> tienen una <xref:System.Windows.Controls.Control.Template%2A> propiedad, puede definir el valor de la propiedad de plantilla de la misma manera que los demás valores de propiedad que hemos establecido en un <xref:System.Windows.Style> mediante <xref:System.Windows.Setter> .</span><span class="sxs-lookup"><span data-stu-id="7fefa-163">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="7fefa-164">Agregue el siguiente marcado resaltado al estilo de botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-164">Add the following highlighted markup to your button style.</span></span>

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

2. <span data-ttu-id="7fefa-165">**Presentación del botón modificar:** En este punto, debe definir la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7fefa-165">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="7fefa-166">Agregue el siguiente marcado resaltado.</span><span class="sxs-lookup"><span data-stu-id="7fefa-166">Add the following highlighted markup.</span></span> <span data-ttu-id="7fefa-167">Este marcado especifica dos <xref:System.Windows.Shapes.Rectangle> elementos con bordes redondeados, seguidos de un <xref:System.Windows.Controls.DockPanel> .</span><span class="sxs-lookup"><span data-stu-id="7fefa-167">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="7fefa-168"><xref:System.Windows.Controls.DockPanel>Se utiliza para hospedar el <xref:System.Windows.Controls.ContentPresenter> del botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-168">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="7fefa-169"><xref:System.Windows.Controls.ContentPresenter>Muestra el contenido del botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-169">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="7fefa-170">En este tutorial, el contenido es texto ("botón 1", "botón 2", "botón 3").</span><span class="sxs-lookup"><span data-stu-id="7fefa-170">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="7fefa-171">Todos los componentes de plantilla (los rectángulos y <xref:System.Windows.Controls.DockPanel> ) se colocan dentro de un <xref:System.Windows.Controls.Grid> .</span><span class="sxs-lookup"><span data-stu-id="7fefa-171">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

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

     <span data-ttu-id="7fefa-172">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7fefa-172">Press F5 to run the application.</span></span> <span data-ttu-id="7fefa-173">Debería tener un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="7fefa-173">It should look like the following.</span></span>

     ![Ventana con 3 botones](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="7fefa-175">**Agregue un glasseffect a la plantilla:** A continuación, agregará el cristal.</span><span class="sxs-lookup"><span data-stu-id="7fefa-175">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="7fefa-176">En primer lugar, cree algunos recursos que creen un efecto de degradado de cristal.</span><span class="sxs-lookup"><span data-stu-id="7fefa-176">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="7fefa-177">Agregue estos recursos de degradado en cualquier parte del `Application.Resources` bloque:</span><span class="sxs-lookup"><span data-stu-id="7fefa-177">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

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

     <span data-ttu-id="7fefa-178">Estos recursos se utilizan como <xref:System.Windows.Shapes.Shape.Fill%2A> para un rectángulo que se inserta en <xref:System.Windows.Controls.Grid> de la plantilla de botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-178">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="7fefa-179">Agregue el siguiente marcado resaltado a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7fefa-179">Add the following highlighted markup to the template.</span></span>

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

     <span data-ttu-id="7fefa-180">Observe que el <xref:System.Windows.UIElement.Opacity%2A> del rectángulo con la `x:Name` propiedad de "glassCube" es 0, por lo que, al ejecutar el ejemplo, no verá el rectángulo de cristal superpuesto en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="7fefa-180">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="7fefa-181">Esto se debe a que más adelante se agregarán desencadenadores a la plantilla para cuando el usuario interactúe con el botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-181">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="7fefa-182">Sin embargo, puede ver el aspecto del botón ahora cambiando el <xref:System.Windows.UIElement.Opacity%2A> valor a 1 y ejecutando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7fefa-182">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="7fefa-183">Consulte la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="7fefa-183">See the following figure.</span></span> <span data-ttu-id="7fefa-184">Antes de continuar con el paso siguiente, cambie el <xref:System.Windows.UIElement.Opacity%2A> valor de nuevo a 0.</span><span class="sxs-lookup"><span data-stu-id="7fefa-184">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="7fefa-185">![Botones personalizados creados mediante XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="7fefa-185">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="7fefa-186">Crear interactividad del botón</span><span class="sxs-lookup"><span data-stu-id="7fefa-186">Create Button Interactivity</span></span>

<span data-ttu-id="7fefa-187">En esta sección, creará desencadenadores de propiedades y desencadenadores de eventos para cambiar los valores de propiedad y ejecutar animaciones en respuesta a las acciones del usuario, como mover el puntero del mouse sobre el botón y hacer clic en.</span><span class="sxs-lookup"><span data-stu-id="7fefa-187">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="7fefa-188">Una manera fácil de agregar interactividad (pasar el mouse sobre, salir del mouse, hacer clic, etc.) es definir desencadenadores dentro de la plantilla o el estilo.</span><span class="sxs-lookup"><span data-stu-id="7fefa-188">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="7fefa-189">Para crear una <xref:System.Windows.Trigger> , defina una "condición" de propiedad como: el valor de la <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad Button es igual a `true` .</span><span class="sxs-lookup"><span data-stu-id="7fefa-189">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="7fefa-190">A continuación, defina los establecedores (acciones) que tienen lugar cuando se cumple la condición del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="7fefa-190">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="7fefa-191">Para crear interactividad del botón</span><span class="sxs-lookup"><span data-stu-id="7fefa-191">To create button interactivity</span></span>

1. <span data-ttu-id="7fefa-192">**Agregar desencadenadores de plantilla:** Agregue el marcado resaltado a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7fefa-192">**Add template triggers:** Add the highlighted markup to your template.</span></span>

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

2. <span data-ttu-id="7fefa-193">**Agregar desencadenadores de propiedad:** Agregue el marcado resaltado al `ControlTemplate.Triggers` bloque:</span><span class="sxs-lookup"><span data-stu-id="7fefa-193">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="7fefa-194">Presione F5 para ejecutar la aplicación y ver el efecto al ejecutar el puntero del mouse sobre los botones.</span><span class="sxs-lookup"><span data-stu-id="7fefa-194">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="7fefa-195">**Agregar un desencadenador de foco:** A continuación, agregaremos algunos establecedores similares para controlar el caso cuando el botón tenga el foco (por ejemplo, después de que el usuario haga clic en él).</span><span class="sxs-lookup"><span data-stu-id="7fefa-195">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

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

     <span data-ttu-id="7fefa-196">Presione F5 para ejecutar la aplicación y haga clic en uno de los botones.</span><span class="sxs-lookup"><span data-stu-id="7fefa-196">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="7fefa-197">Tenga en cuenta que el botón permanece resaltado después de hacer clic en él porque todavía tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="7fefa-197">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="7fefa-198">Si hace clic en otro botón, el nuevo botón gana el foco mientras el último lo pierde.</span><span class="sxs-lookup"><span data-stu-id="7fefa-198">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="7fefa-199">**Agregar animaciones para** <xref:System.Windows.UIElement.MouseEnter> **y** <xref:System.Windows.UIElement.MouseLeave> **:** A continuación, se agregan algunas animaciones a los desencadenadores.  </span><span class="sxs-lookup"><span data-stu-id="7fefa-199">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="7fefa-200">Agregue el siguiente marcado en cualquier parte dentro del `ControlTemplate.Triggers` bloque.</span><span class="sxs-lookup"><span data-stu-id="7fefa-200">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

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

     <span data-ttu-id="7fefa-201">El rectángulo Glass se reduce cuando el puntero del mouse se mueve sobre el botón y vuelve al tamaño normal cuando el puntero sale.</span><span class="sxs-lookup"><span data-stu-id="7fefa-201">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="7fefa-202">Hay dos animaciones que se desencadenan cuando el puntero pasa por encima del botón ( <xref:System.Windows.UIElement.MouseEnter> se genera el evento).</span><span class="sxs-lookup"><span data-stu-id="7fefa-202">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="7fefa-203">Estas animaciones reducen el rectángulo de cristal a lo largo del eje X e y.</span><span class="sxs-lookup"><span data-stu-id="7fefa-203">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="7fefa-204">Observe las propiedades de los <xref:System.Windows.Media.Animation.DoubleAnimation> elementos, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> .</span><span class="sxs-lookup"><span data-stu-id="7fefa-204">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="7fefa-205"><xref:System.Windows.Media.Animation.Timeline.Duration%2A>Especifica que la animación se produce más de medio segundo y <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> especifica que el cristal se reduce en un 10%.</span><span class="sxs-lookup"><span data-stu-id="7fefa-205">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="7fefa-206">El segundo desencadenador de eventos ( <xref:System.Windows.UIElement.MouseLeave> ) simplemente detiene el primero.</span><span class="sxs-lookup"><span data-stu-id="7fefa-206">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="7fefa-207">Al detener <xref:System.Windows.Media.Animation.Storyboard> , todas las propiedades animadas vuelven a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="7fefa-207">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="7fefa-208">Por lo tanto, cuando el usuario mueve el puntero sobre el botón, el botón vuelve a la manera en que estaba antes de que se moviera el puntero del mouse sobre el botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-208">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="7fefa-209">Para obtener más información sobre las animaciones, vea [información general sobre animaciones](../graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7fefa-209">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="7fefa-210">**Agregue una animación para cuando se haga clic en el botón:** El paso final consiste en agregar un desencadenador para cuando el usuario haga clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="7fefa-210">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="7fefa-211">Agregue el siguiente marcado en cualquier parte dentro del `ControlTemplate.Triggers` bloque:</span><span class="sxs-lookup"><span data-stu-id="7fefa-211">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

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

     <span data-ttu-id="7fefa-212">Presione F5 para ejecutar la aplicación y haga clic en uno de los botones.</span><span class="sxs-lookup"><span data-stu-id="7fefa-212">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="7fefa-213">Al hacer clic en un botón, el rectángulo de cristal gira alrededor.</span><span class="sxs-lookup"><span data-stu-id="7fefa-213">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="7fefa-214">Resumen</span><span class="sxs-lookup"><span data-stu-id="7fefa-214">Summary</span></span>
 <span data-ttu-id="7fefa-215">En este tutorial, ha realizado los ejercicios siguientes:</span><span class="sxs-lookup"><span data-stu-id="7fefa-215">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="7fefa-216">Se destina <xref:System.Windows.Style> a un tipo de objeto ( <xref:System.Windows.Controls.Button> ).</span><span class="sxs-lookup"><span data-stu-id="7fefa-216">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="7fefa-217">Propiedades básicas controladas de los botones de toda la aplicación mediante <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="7fefa-217">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="7fefa-218">Se crearon recursos como degradados que se van a usar para los valores de propiedad de los <xref:System.Windows.Style> establecedores.</span><span class="sxs-lookup"><span data-stu-id="7fefa-218">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="7fefa-219">Personalizar el aspecto de los botones de toda la aplicación aplicando una plantilla a los botones.</span><span class="sxs-lookup"><span data-stu-id="7fefa-219">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="7fefa-220">Comportamiento personalizado de los botones en respuesta a las acciones del usuario (como <xref:System.Windows.UIElement.MouseEnter> , <xref:System.Windows.UIElement.MouseLeave> y <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ) que incluyen efectos de animación.</span><span class="sxs-lookup"><span data-stu-id="7fefa-220">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fefa-221">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fefa-221">See also</span></span>

- [<span data-ttu-id="7fefa-222">Crear un botón mediante Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="7fefa-222">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="7fefa-223">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="7fefa-223">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="7fefa-224">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="7fefa-224">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="7fefa-225">Información general sobre el dibujo con colores sólidos y degradados</span><span class="sxs-lookup"><span data-stu-id="7fefa-225">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="7fefa-226">Información general sobre efectos de imagen</span><span class="sxs-lookup"><span data-stu-id="7fefa-226">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
