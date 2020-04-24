---
title: 'Tutorial: Estilo WPF contenido'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646329"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="23252-102">Tutorial: Estilo WPF contenido</span><span class="sxs-lookup"><span data-stu-id="23252-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="23252-103">En este artículo se muestra cómo aplicar estilos a un control de Windows Presentation Foundation (WPF) hospedado en un formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23252-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23252-104">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="23252-104">Prerequisites</span></span>

<span data-ttu-id="23252-105">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="23252-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="23252-106">Creación del proyecto</span><span class="sxs-lookup"><span data-stu-id="23252-106">Create the project</span></span>

<span data-ttu-id="23252-107">Abra Visual Studio y cree un nuevo proyecto de aplicación `StylingWpfContent`de formularios Windows Forms en Visual Basic o Visual C. denominado .</span><span class="sxs-lookup"><span data-stu-id="23252-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="23252-108">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="23252-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="23252-109">Crear los tipos de control WPFWPF</span><span class="sxs-lookup"><span data-stu-id="23252-109">Create the WPF control types</span></span>

<span data-ttu-id="23252-110">Después de agregar un tipo de control WPF al proyecto, puede hospedarlo en un control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="23252-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="23252-111">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="23252-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="23252-112">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="23252-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="23252-113">Para obtener más información, vea [Tutorial: crear nuevo contenido de WPF en formularios Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño .</span><span class="sxs-lookup"><span data-stu-id="23252-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="23252-114">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="23252-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="23252-115">En la ventana **Propiedades,** establezca <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> el valor de las propiedades y en **200**.</span><span class="sxs-lookup"><span data-stu-id="23252-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="23252-116">Agregue <xref:System.Windows.Controls.Button?displayProperty=nameWithType> un control <xref:System.Windows.Controls.UserControl> al valor y <xref:System.Windows.Controls.ContentControl.Content%2A> establezca el valor de la propiedad en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="23252-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="23252-117">Agregue un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> segundo <xref:System.Windows.Controls.UserControl> control al valor <xref:System.Windows.Controls.ContentControl.Content%2A> y establezca el valor de la propiedad en **OK**.</span><span class="sxs-lookup"><span data-stu-id="23252-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="23252-118">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="23252-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="23252-119">Aplicar un style a un control WPFWPF</span><span class="sxs-lookup"><span data-stu-id="23252-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="23252-120">Puede aplicar diferentes estilos a un control WPF para cambiar su apariencia y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="23252-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="23252-121">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23252-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="23252-122">En el **cuadro**de `UserControl1` herramientas , `UserControl1` haga doble clic para crear una instancia del formulario.</span><span class="sxs-lookup"><span data-stu-id="23252-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="23252-123">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="23252-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="23252-124">En el panel `elementHost1`de etiquetas inteligentes para , haga clic en **Editar contenido hospedado** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="23252-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="23252-125">`UserControl1`Se abre en el Diseñador wpfWPF.</span><span class="sxs-lookup"><span data-stu-id="23252-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="23252-126">En la vista XAML, inserte el código XAML siguiente después de la etiqueta de apertura `<UserControl>`.</span><span class="sxs-lookup"><span data-stu-id="23252-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="23252-127">Este código XAML crea un degradado con un borde de degradado en contraste.</span><span class="sxs-lookup"><span data-stu-id="23252-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="23252-128">Al hacer clic en el control, los degradados cambian para generar el aspecto de un botón presionado.</span><span class="sxs-lookup"><span data-stu-id="23252-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="23252-129">Para obtener más información, consulte [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="23252-129">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

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

1. <span data-ttu-id="23252-130">Aplique `SimpleButton` el estilo definido en el paso anterior al botón `<Button>` Cancelar insertando el siguiente XAML en la etiqueta del botón **Cancelar.**</span><span class="sxs-lookup"><span data-stu-id="23252-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="23252-131">La declaración de botón será similar al siguiente XAML:</span><span class="sxs-lookup"><span data-stu-id="23252-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="23252-132">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="23252-132">Build the project.</span></span>

1. <span data-ttu-id="23252-133">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23252-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="23252-134">El nuevo estilo se aplica al control de botón.</span><span class="sxs-lookup"><span data-stu-id="23252-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="23252-135">En el menú **Depurar,** seleccione **Iniciar depuración** para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23252-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="23252-136">Haga clic en los botones **Aceptar** y **Cancelar** y vea las diferencias.</span><span class="sxs-lookup"><span data-stu-id="23252-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="23252-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23252-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="23252-138">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="23252-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="23252-139">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="23252-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="23252-140">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23252-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="23252-141">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="23252-141">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="23252-142">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="23252-142">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
