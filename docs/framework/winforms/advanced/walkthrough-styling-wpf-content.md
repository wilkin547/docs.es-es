---
title: 'Tutorial: Aplicar estilos a contenido de WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 32ca9658ddf4ab6e8690f29797b7ac7b09df2ca7
ms.sourcegitcommit: d98fdb087d9c8aba7d2cb93fe4b4ee35a2308cee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2019
ms.locfileid: "69012959"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="432a1-102">Tutorial: Contenido de estilo WPF</span><span class="sxs-lookup"><span data-stu-id="432a1-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="432a1-103">En este tutorial se muestra cómo aplicar un estilo a un control de Windows Presentation Foundation (WPF) hospedado en un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="432a1-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="432a1-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="432a1-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="432a1-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="432a1-105">Create the project.</span></span>

- <span data-ttu-id="432a1-106">Crear el tipo de control WPF.</span><span class="sxs-lookup"><span data-stu-id="432a1-106">Create the WPF control type.</span></span>

- <span data-ttu-id="432a1-107">Aplicar un estilo al control WPF.</span><span class="sxs-lookup"><span data-stu-id="432a1-107">Apply a style to the WPF control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="432a1-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="432a1-108">Prerequisites</span></span>

<span data-ttu-id="432a1-109">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="432a1-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="432a1-110">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="432a1-110">Create the project</span></span>

<span data-ttu-id="432a1-111">Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o `StylingWpfContent`en Visual denominado.</span><span class="sxs-lookup"><span data-stu-id="432a1-111">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="432a1-112">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="432a1-112">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="432a1-113">Crear los tipos de control WPF</span><span class="sxs-lookup"><span data-stu-id="432a1-113">Create the WPF control types</span></span>

<span data-ttu-id="432a1-114">Después de agregar un tipo de control WPF al proyecto, puede hospedarlo en un control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="432a1-114">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="432a1-115">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="432a1-115">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="432a1-116">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="432a1-116">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="432a1-117">Para obtener más información, vea [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño.</span><span class="sxs-lookup"><span data-stu-id="432a1-117">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="432a1-118">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="432a1-118">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="432a1-119">Para obtener más información, vea [Cómo: Seleccione y mueva los elementos en el](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="432a1-119">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="432a1-120">En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en `200`.</span><span class="sxs-lookup"><span data-stu-id="432a1-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="432a1-121">Agregue un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> <xref:System.Windows.Controls.UserControl> control a y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="432a1-121">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="432a1-122">Agregue un segundo <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control <xref:System.Windows.Controls.UserControl> a y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad en **OK**.</span><span class="sxs-lookup"><span data-stu-id="432a1-122">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="432a1-123">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="432a1-123">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="432a1-124">Aplicar un estilo a un control WPF</span><span class="sxs-lookup"><span data-stu-id="432a1-124">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="432a1-125">Puede aplicar diferentes estilos a un control WPF para cambiar su apariencia y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="432a1-125">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="432a1-126">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="432a1-126">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="432a1-127">En el **cuadro de herramientas**, haga `UserControl1` doble clic en para crear `UserControl1` una instancia de en el formulario.</span><span class="sxs-lookup"><span data-stu-id="432a1-127">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="432a1-128">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="432a1-128">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="432a1-129">En el panel de etiquetas inteligentes `elementHost1`de, haga clic en **editar contenido hospedado** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="432a1-129">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

     <span data-ttu-id="432a1-130">`UserControl1` se abre en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="432a1-130">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

1. <span data-ttu-id="432a1-131">En la vista XAML, inserte el código XAML siguiente después de la etiqueta de apertura `<UserControl>`.</span><span class="sxs-lookup"><span data-stu-id="432a1-131">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>

     <span data-ttu-id="432a1-132">Este código XAML crea un degradado con un borde de degradado en contraste.</span><span class="sxs-lookup"><span data-stu-id="432a1-132">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="432a1-133">Al hacer clic en el control, los degradados cambian para generar el aspecto de un botón presionado.</span><span class="sxs-lookup"><span data-stu-id="432a1-133">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="432a1-134">Para obtener más información, consulte [Aplicar estilos y plantillas](../../wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="432a1-134">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. <span data-ttu-id="432a1-135">Aplique el estilo `SimpleButton` definido en el paso anterior al botón Cancelar insertando el código XAML siguiente en la etiqueta `<Button>` del botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="432a1-135">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="432a1-136">La declaración del botón será similar al código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="432a1-136">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="432a1-137">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="432a1-137">Build the project.</span></span>

1. <span data-ttu-id="432a1-138">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="432a1-138">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="432a1-139">El nuevo estilo se aplica al control de botón.</span><span class="sxs-lookup"><span data-stu-id="432a1-139">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="432a1-140">En el menú Depurar, seleccione **iniciar** depuración para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="432a1-140">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="432a1-141">Haga clic en los botones Aceptar y Cancelar y vea las diferencias.</span><span class="sxs-lookup"><span data-stu-id="432a1-141">Click the OK and Cancel buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="432a1-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="432a1-142">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="432a1-143">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="432a1-143">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="432a1-144">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="432a1-144">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="432a1-145">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="432a1-145">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="432a1-146">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="432a1-146">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="432a1-147">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="432a1-147">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
