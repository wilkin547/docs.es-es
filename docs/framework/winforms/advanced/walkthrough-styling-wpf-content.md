---
title: 'Tutorial: Aplicar estilos a contenido de WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 287ed08db8a4266e5044a81d47a697949257e113
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658483"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="f3b31-102">Tutorial: Contenido de estilo WPF</span><span class="sxs-lookup"><span data-stu-id="f3b31-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="f3b31-103">En este artículo se muestra cómo aplicar el estilo a un control de Windows Presentation Foundation (WPF) hospedado en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f3b31-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f3b31-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f3b31-104">Prerequisites</span></span>

<span data-ttu-id="f3b31-105">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="f3b31-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f3b31-106">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="f3b31-106">Create the project</span></span>

<span data-ttu-id="f3b31-107">Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o `StylingWpfContent`en Visual denominado.</span><span class="sxs-lookup"><span data-stu-id="f3b31-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="f3b31-108">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f3b31-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="f3b31-109">Crear los tipos de control WPF</span><span class="sxs-lookup"><span data-stu-id="f3b31-109">Create the WPF control types</span></span>

<span data-ttu-id="f3b31-110">Después de agregar un tipo de control WPF al proyecto, puede hospedarlo en un control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="f3b31-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="f3b31-111">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="f3b31-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="f3b31-112">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="f3b31-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="f3b31-113">Para obtener más información, vea [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño.</span><span class="sxs-lookup"><span data-stu-id="f3b31-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="f3b31-114">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f3b31-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="f3b31-115">En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en **200**.</span><span class="sxs-lookup"><span data-stu-id="f3b31-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="f3b31-116">Agregue un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> <xref:System.Windows.Controls.UserControl> control a y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="f3b31-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="f3b31-117">Agregue un segundo <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control <xref:System.Windows.Controls.UserControl> a y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad en **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b31-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="f3b31-118">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3b31-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="f3b31-119">Aplicar un estilo a un control WPF</span><span class="sxs-lookup"><span data-stu-id="f3b31-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="f3b31-120">Puede aplicar diferentes estilos a un control WPF para cambiar su apariencia y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f3b31-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="f3b31-121">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f3b31-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="f3b31-122">En el **cuadro de herramientas**, haga `UserControl1` doble clic en para crear `UserControl1` una instancia de en el formulario.</span><span class="sxs-lookup"><span data-stu-id="f3b31-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="f3b31-123">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="f3b31-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="f3b31-124">En el panel de etiquetas inteligentes `elementHost1`de, haga clic en **editar contenido hospedado** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f3b31-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="f3b31-125">`UserControl1`se abre en WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="f3b31-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="f3b31-126">En la vista XAML, inserte el código XAML siguiente después de la etiqueta de apertura `<UserControl>`.</span><span class="sxs-lookup"><span data-stu-id="f3b31-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="f3b31-127">Este código XAML crea un degradado con un borde de degradado en contraste.</span><span class="sxs-lookup"><span data-stu-id="f3b31-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="f3b31-128">Al hacer clic en el control, los degradados cambian para generar el aspecto de un botón presionado.</span><span class="sxs-lookup"><span data-stu-id="f3b31-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="f3b31-129">Para obtener más información, consulte [Aplicar estilos y plantillas](../../wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="f3b31-129">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

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

1. <span data-ttu-id="f3b31-130">Aplique el `<Button>` estilo definido en el paso anterior al botón Cancelar insertando el código XAML siguiente en la etiqueta del botón **Cancelar.** `SimpleButton`</span><span class="sxs-lookup"><span data-stu-id="f3b31-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="f3b31-131">La declaración del botón será similar al código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="f3b31-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="f3b31-132">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f3b31-132">Build the project.</span></span>

1. <span data-ttu-id="f3b31-133">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f3b31-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="f3b31-134">El nuevo estilo se aplica al control de botón.</span><span class="sxs-lookup"><span data-stu-id="f3b31-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="f3b31-135">En el menú Depurar, seleccione **iniciar** depuración para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3b31-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="f3b31-136">Haga clic en los botones **Aceptar** y **Cancelar** y vea las diferencias.</span><span class="sxs-lookup"><span data-stu-id="f3b31-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3b31-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3b31-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="f3b31-138">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="f3b31-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="f3b31-139">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="f3b31-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="f3b31-140">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3b31-140">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="f3b31-141">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="f3b31-141">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="f3b31-142">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="f3b31-142">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
