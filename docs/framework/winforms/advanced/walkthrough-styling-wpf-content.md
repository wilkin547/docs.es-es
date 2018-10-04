---
title: 'Tutorial: Aplicar estilos al contenido de WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: bd056bb9d5ad429e35e0b2625dee99ae5f18b527
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780146"
---
# <a name="walkthrough-styling-wpf-content"></a><span data-ttu-id="179dd-102">Tutorial: Aplicar estilos al contenido de WPF</span><span class="sxs-lookup"><span data-stu-id="179dd-102">Walkthrough: Styling WPF Content</span></span>
<span data-ttu-id="179dd-103">En este tutorial se muestra cómo aplicar un estilo a un control de Windows Presentation Foundation (WPF) hospedado en un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="179dd-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="179dd-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="179dd-104">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="179dd-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="179dd-105">Create the project.</span></span>

-   <span data-ttu-id="179dd-106">Crear el tipo de control WPF.</span><span class="sxs-lookup"><span data-stu-id="179dd-106">Create the WPF control type.</span></span>

-   <span data-ttu-id="179dd-107">Aplicar un estilo al control WPF.</span><span class="sxs-lookup"><span data-stu-id="179dd-107">Apply a style to the WPF control.</span></span>

> [!NOTE]
>  <span data-ttu-id="179dd-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="179dd-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="179dd-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="179dd-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="179dd-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="179dd-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="179dd-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="179dd-111">Prerequisites</span></span>  
 <span data-ttu-id="179dd-112">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="179dd-112">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="179dd-113">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="179dd-113">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="179dd-114">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="179dd-114">Creating the Project</span></span>  
 <span data-ttu-id="179dd-115">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="179dd-115">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="179dd-116">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="179dd-116">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="179dd-117">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="179dd-117">To create the project</span></span>  
  
-   <span data-ttu-id="179dd-118">Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `StylingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="179dd-118">Create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="179dd-119">Crear los tipos de control WPF</span><span class="sxs-lookup"><span data-stu-id="179dd-119">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="179dd-120">Después de agregar un tipo de control WPF al proyecto, puede hospedarlo en un control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="179dd-120">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="179dd-121">Para crear tipos de control WPF</span><span class="sxs-lookup"><span data-stu-id="179dd-121">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="179dd-122">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="179dd-122">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="179dd-123">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="179dd-123">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="179dd-124">Para obtener más información, consulte [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="179dd-124">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="179dd-125">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="179dd-125">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="179dd-126">Para obtener más información, consulte [Cómo: seleccionar y mover elementos en la superficie de diseño](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="179dd-126">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="179dd-127">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.</span><span class="sxs-lookup"><span data-stu-id="179dd-127">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="179dd-128">Agregar un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad **cancelar**.</span><span class="sxs-lookup"><span data-stu-id="179dd-128">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>  
  
5.  <span data-ttu-id="179dd-129">Agregue un segundo <xref:System.Windows.Controls.Button?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="179dd-129">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>  
  
6.  <span data-ttu-id="179dd-130">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="179dd-130">Build the project.</span></span>  
  
## <a name="applying-a-style-to-a-wpf-control"></a><span data-ttu-id="179dd-131">Aplicar un estilo a un control WPF</span><span class="sxs-lookup"><span data-stu-id="179dd-131">Applying a Style to a WPF Control</span></span>  
 <span data-ttu-id="179dd-132">Puede aplicar diferentes estilos a un control WPF para cambiar su apariencia y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="179dd-132">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a><span data-ttu-id="179dd-133">Para aplicar un estilo a un control WPF</span><span class="sxs-lookup"><span data-stu-id="179dd-133">To apply a style to a WPF control</span></span>  
  
1.  <span data-ttu-id="179dd-134">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="179dd-134">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="179dd-135">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="179dd-135">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="179dd-136">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="179dd-136">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="179dd-137">En el panel de etiquetas inteligentes para `elementHost1`, haga clic en **editar contenido hospedado** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="179dd-137">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>  
  
     <span data-ttu-id="179dd-138">`UserControl1` se abre en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="179dd-138">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="179dd-139">En la vista XAML, inserte el código XAML siguiente después de la etiqueta de apertura `<UserControl>`.</span><span class="sxs-lookup"><span data-stu-id="179dd-139">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>  
  
     <span data-ttu-id="179dd-140">Este código XAML crea un degradado con un borde de degradado en contraste.</span><span class="sxs-lookup"><span data-stu-id="179dd-140">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="179dd-141">Al hacer clic en el control, los degradados cambian para generar el aspecto de un botón presionado.</span><span class="sxs-lookup"><span data-stu-id="179dd-141">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="179dd-142">Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="179dd-142">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
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
  
1.  <span data-ttu-id="179dd-143">Aplique el estilo `SimpleButton` definido en el paso anterior al botón Cancelar insertando el código XAML siguiente en la etiqueta `<Button>` del botón Cancelar.</span><span class="sxs-lookup"><span data-stu-id="179dd-143">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     <span data-ttu-id="179dd-144">La declaración del botón será similar al código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="179dd-144">Your button declaration will resemble the following XAML.</span></span>  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1.  <span data-ttu-id="179dd-145">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="179dd-145">Build the project.</span></span>  
  
2.  <span data-ttu-id="179dd-146">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="179dd-146">Open `Form1` in the Windows Forms Designer.</span></span>  
  
3.  <span data-ttu-id="179dd-147">El nuevo estilo se aplica al control de botón.</span><span class="sxs-lookup"><span data-stu-id="179dd-147">The new style is applied to the button control.</span></span>  
  
4.  <span data-ttu-id="179dd-148">Desde el **depurar** menú, seleccione **Iniciar depuración** para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="179dd-148">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>  
  
5.  <span data-ttu-id="179dd-149">Haga clic en los botones Aceptar y Cancelar y vea las diferencias.</span><span class="sxs-lookup"><span data-stu-id="179dd-149">Click the OK and Cancel buttons and view the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="179dd-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="179dd-150">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="179dd-151">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="179dd-151">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="179dd-152">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="179dd-152">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="179dd-153">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="179dd-153">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 [<span data-ttu-id="179dd-154">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="179dd-154">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="179dd-155">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="179dd-155">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
