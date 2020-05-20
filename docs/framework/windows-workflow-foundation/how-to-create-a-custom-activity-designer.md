---
title: Procedimiento para crear un diseñador de actividad personalizado
description: En este artículo se describe cómo crear un diseñador de actividad personalizado de Workflow Foundation que tiene una zona de colocación en la que se puede colocar una actividad arbitraria.
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: 015efd1e482e2b531d28b9caec411c76116c9653
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419790"
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="864eb-103">Procedimiento para crear un diseñador de actividad personalizado</span><span class="sxs-lookup"><span data-stu-id="864eb-103">How to: Create a Custom Activity Designer</span></span>

<span data-ttu-id="864eb-104">Normalmente los diseñadores de actividad personalizados se implementan de forma que sus actividades asociadas admitan composición con otras actividades cuyos diseñadores se pueden colocar en la superficie de diseño con ellas.</span><span class="sxs-lookup"><span data-stu-id="864eb-104">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="864eb-105">Esta funcionalidad requiere que un diseñador de actividad personalizado proporcione una "zona de colocación" donde se pueda colocar una actividad arbitraria y también los medios para administrar la colección de elementos resultante en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="864eb-105">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="864eb-106">En este tema se describe cómo crear un diseñador de actividad personalizado que contenga esta área de colocación y cómo crear un diseñador de actividad personalizado que proporcione la funcionalidad de edición necesaria para administrar la colección de elementos del diseñador.</span><span class="sxs-lookup"><span data-stu-id="864eb-106">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>

<span data-ttu-id="864eb-107">Por lo general, los diseñadores de actividad personalizados heredan de <xref:System.Activities.Presentation.ActivityDesigner>, el tipo de diseñador de actividades base predeterminado para cualquier actividad sin un diseñador específico.</span><span class="sxs-lookup"><span data-stu-id="864eb-107">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="864eb-108">Este tipo proporciona la experiencia de interactuar en tiempo de diseño con la cuadrícula de propiedades y de configurar los aspectos básicos como la administración de colores e iconos.</span><span class="sxs-lookup"><span data-stu-id="864eb-108">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>

<span data-ttu-id="864eb-109"><xref:System.Activities.Presentation.ActivityDesigner> usa dos controles del asistente, <xref:System.Activities.Presentation.WorkflowItemPresenter> y <xref:System.Activities.Presentation.WorkflowItemsPresenter>, para facilitar el desarrollo de diseñadores de actividad personalizados.</span><span class="sxs-lookup"><span data-stu-id="864eb-109"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="864eb-110">Administran funciones comunes como arrastrar y colocar elementos secundarios, además de la eliminación, selección y adición de esos elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="864eb-110">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="864eb-111"><xref:System.Activities.Presentation.WorkflowItemPresenter>Permite un único elemento secundario de la interfaz de usuario en, que proporciona la "zona de colocación", mientras que <xref:System.Activities.Presentation.WorkflowItemsPresenter> puede proporcionar compatibilidad con varios elementos de la interfaz de usuario, incluida funcionalidad adicional, como la ordenación, el movimiento, la eliminación y la adición de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="864eb-111">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>

<span data-ttu-id="864eb-112">La otra parte clave del caso que necesita resaltarse en la implementación de un diseñador de actividad personalizado se refiere a la manera en que las ediciones visuales se enlazan mediante el enlace de datos de WPF a la instancia almacenada en la memoria de lo que estamos editando en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="864eb-112">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using WPF data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="864eb-113">Esto se lleva a cabo mediante el árbol de elementos de modelo, que también es responsable de la habilitación de la notificación de cambios y del seguimiento de eventos como los cambios en los estados.</span><span class="sxs-lookup"><span data-stu-id="864eb-113">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>

<span data-ttu-id="864eb-114">En este tema se describen dos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="864eb-114">This topic outlines two procedures.</span></span>

1. <span data-ttu-id="864eb-115">El primer procedimiento describe cómo crear un diseñador de actividad personalizado con una clase <xref:System.Activities.Presentation.WorkflowItemPresenter> que proporciona el área de colocación que recibe a otras actividades.</span><span class="sxs-lookup"><span data-stu-id="864eb-115">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="864eb-116">Este procedimiento se basa en el ejemplo de [presentación de elementos de flujo de trabajo de los diseñadores compuestos personalizados](./samples/custom-composite-designers-workflow-item-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="864eb-116">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>

2. <span data-ttu-id="864eb-117">El segundo procedimiento describe cómo crear un diseñador de actividad personalizado con una clase <xref:System.Activities.Presentation.WorkflowItemsPresenter> que proporciona la funcionalidad necesaria para editar una colección de elementos contenidos.</span><span class="sxs-lookup"><span data-stu-id="864eb-117">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="864eb-118">Este procedimiento se basa en el ejemplo de presentación de los [elementos de flujo de trabajo de los diseñadores compuestos personalizados](./samples/custom-composite-designers-workflow-items-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="864eb-118">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](./samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="864eb-119">Para crear un diseñador de actividad personalizado con un área de colocación mediante WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="864eb-119">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>

1. <span data-ttu-id="864eb-120">Inicie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="864eb-120">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="864eb-121">En el menú **archivo** , seleccione **nuevo**y, a continuación, seleccione **proyecto..**..</span><span class="sxs-lookup"><span data-stu-id="864eb-121">On the **File** menu, point to **New**, and then select **Project…**.</span></span>

     <span data-ttu-id="864eb-122">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="864eb-122">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="864eb-123">En el panel **plantillas instaladas** , seleccione **Windows** en la categoría de idioma que prefiera.</span><span class="sxs-lookup"><span data-stu-id="864eb-123">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>

4. <span data-ttu-id="864eb-124">En el panel **plantillas** , seleccione **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="864eb-124">In the **Templates** pane, select **WPF Application**.</span></span>

5. <span data-ttu-id="864eb-125">En el cuadro **nombre** , escriba `UsingWorkflowItemPresenter` .</span><span class="sxs-lookup"><span data-stu-id="864eb-125">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>

6. <span data-ttu-id="864eb-126">En el cuadro **Ubicación** , escriba el directorio en el que desea guardar el proyecto o haga clic en **examinar** para desplazarse hasta él.</span><span class="sxs-lookup"><span data-stu-id="864eb-126">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>

7. <span data-ttu-id="864eb-127">En el cuadro **solución** , acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="864eb-127">In the **Solution** box, accept the default value.</span></span>

8. <span data-ttu-id="864eb-128">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="864eb-128">Click **OK**.</span></span>

9. <span data-ttu-id="864eb-129">Haga clic con el botón secundario en el archivo *MainWindows. Xaml* en el **Explorador de soluciones**, seleccione **eliminar** y confirme **Aceptar** en el cuadro de diálogo **Microsoft Visual Studio** .</span><span class="sxs-lookup"><span data-stu-id="864eb-129">Right-click the *MainWindows.xaml* file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialog box.</span></span>

10. <span data-ttu-id="864eb-130">Haga clic con el botón derecho en el proyecto UsingWorkflowItemPresenter de **Explorador de soluciones**, seleccione **Agregar**y, a continuación, **nuevo elemento.** ..</span><span class="sxs-lookup"><span data-stu-id="864eb-130">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="864eb-131">para abrir el cuadro de diálogo **Agregar nuevo elemento** y seleccione la categoría **WPF** en la sección **plantillas instaladas** de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="864eb-131">to bring up the **Add New Item** dialog and select the **WPF** category from the **Installed Templates** section on the left.</span></span>

11. <span data-ttu-id="864eb-132">Seleccione la plantilla **ventana (WPF)** , asígnele el nombre `RehostingWFDesigner` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="864eb-132">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>

12. <span data-ttu-id="864eb-133">Abra el archivo *RehostingWFDesigner. Xaml* y pegue el siguiente código en él para definir la interfaz de usuario de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="864eb-133">Open the *RehostingWFDesigner.xaml* file and paste the following code into it to define the UI for the application:</span></span>

    ```xaml
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"
            xmlns:sys="clr-namespace:System;assembly=mscorlib"
            Title="Window1" Height="600" Width="900">
        <Window.Resources>
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>
        </Window.Resources>
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="2*"/>
                <ColumnDefinition Width="7*"/>
                <ColumnDefinition Width="3*"/>
            </Grid.ColumnDefinitions>
            <Border Grid.Column="0">
                <sapt:ToolboxControl Name="Toolbox">
                    <sapt:ToolboxCategory CategoryName="Basic">
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.Sequence
                            </sapt:ToolboxItemWrapper.ToolName>
                           </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.WriteLine
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.If
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.While
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                    </sapt:ToolboxCategory>
                </sapt:ToolboxControl>
            </Border>
            <Border Grid.Column="1" Name="DesignerBorder"/>
            <Border Grid.Column="2" Name="PropertyBorder"/>
        </Grid>
    </Window>
    ```

13. <span data-ttu-id="864eb-134">Para asociar un diseñador de actividad a un tipo de actividad, debe registrar ese diseñador de actividad con el almacén de metadatos.</span><span class="sxs-lookup"><span data-stu-id="864eb-134">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="864eb-135">Para ello, agregue el método `RegisterMetadata` a la clase `RehostingWFDesigner`.</span><span class="sxs-lookup"><span data-stu-id="864eb-135">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="864eb-136">Dentro del ámbito del método `RegisterMetadata`, cree un objeto <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> y llame al método <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> para agregar los atributos a él.</span><span class="sxs-lookup"><span data-stu-id="864eb-136">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="864eb-137">Llame al método <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> para agregar <xref:System.Activities.Presentation.Metadata.AttributeTable> al almacén de metadatos.</span><span class="sxs-lookup"><span data-stu-id="864eb-137">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="864eb-138">El siguiente código contiene la lógica de rehospedaje para el diseñador.</span><span class="sxs-lookup"><span data-stu-id="864eb-138">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="864eb-139">Registra los metadatos, coloca `SimpleNativeActivity` en el cuadro de herramientas y crea el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="864eb-139">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="864eb-140">Coloque este código en el archivo *RehostingWFDesigner.Xaml.CS* .</span><span class="sxs-lookup"><span data-stu-id="864eb-140">Put this code into the *RehostingWFDesigner.xaml.cs* file.</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Presentation.Toolbox;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespace UsingWorkflowItemPresenter
    {
        // Interaction logic for RehostingWFDesigner.xaml
        public partial class RehostingWFDesigner
        {
            public RehostingWFDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();
                // Add custom activity to toolbox.
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

14. <span data-ttu-id="864eb-141">Haga clic con el botón derecho en el directorio References en Explorador de soluciones y seleccione **Agregar referencia..** .</span><span class="sxs-lookup"><span data-stu-id="864eb-141">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="864eb-142">para mostrar el cuadro de diálogo **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="864eb-142">to bring up the **Add Reference** dialog.</span></span>

15. <span data-ttu-id="864eb-143">Haga clic en la pestaña **.net** , busque el ensamblado denominado **System. Activities. Core. Presentation**, selecciónelo y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="864eb-143">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>

16. <span data-ttu-id="864eb-144">Con el mismo procedimiento, agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="864eb-144">Using the same procedure, add references to the following assemblies:</span></span>

    1. <span data-ttu-id="864eb-145">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="864eb-145">System.Data.DataSetExtensions.dll</span></span>

    2. <span data-ttu-id="864eb-146">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="864eb-146">System.Activities.Presentation.dll</span></span>

    3. <span data-ttu-id="864eb-147">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="864eb-147">System.ServiceModel.Activities.dll</span></span>

17. <span data-ttu-id="864eb-148">Abra el archivo *app. Xaml* y cambie el valor de StartUpUri a "RehostingWFDesigner. xaml".</span><span class="sxs-lookup"><span data-stu-id="864eb-148">Open the *App.xaml* file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>

18. <span data-ttu-id="864eb-149">Haga clic con el botón derecho en el proyecto UsingWorkflowItemPresenter de **Explorador de soluciones**, seleccione **Agregar**y, a continuación, **nuevo elemento.** ..</span><span class="sxs-lookup"><span data-stu-id="864eb-149">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="864eb-150">para abrir el cuadro de diálogo **Agregar nuevo elemento** y seleccione la categoría de **flujo de trabajo** , en la sección **plantillas instaladas** de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="864eb-150">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

19. <span data-ttu-id="864eb-151">Seleccione la plantilla **Diseñador de actividad** , asígnele un nombre `SimpleNativeDesigner` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="864eb-151">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>

20. <span data-ttu-id="864eb-152">Abra el archivo *SimpleNativeDesigner. Xaml* y pegue el código siguiente en él.</span><span class="sxs-lookup"><span data-stu-id="864eb-152">Open the *SimpleNativeDesigner.xaml* file and paste the following code into it.</span></span> <span data-ttu-id="864eb-153">Observe que este código utiliza <xref:System.Activities.Presentation.ActivityDesigner> como elemento raíz y muestra cómo se usa el enlace para integrar <xref:System.Activities.Presentation.WorkflowItemPresenter> en el diseñador de forma que se pueda mostrar un tipo secundario en el diseñador de actividad compuesto.</span><span class="sxs-lookup"><span data-stu-id="864eb-153">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="864eb-154">El esquema para <xref:System.Activities.Presentation.ActivityDesigner> permite agregar únicamente un elemento secundario a la definición personalizada del diseñador de actividad; sin embargo, este elemento podría ser un `StackPanel`, `Grid` o algún otro elemento compuesto de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="864eb-154">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <StackPanel>
                    <TextBlock>This is the collapsed view</TextBlock>
                </StackPanel>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock>Custom Text</TextBlock>
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                            HintText="Please drop an activity here" />
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
        </Grid>
    </sap:ActivityDesigner>
    ```

21. <span data-ttu-id="864eb-155">Haga clic con el botón derecho en el proyecto UsingWorkflowItemPresenter de **Explorador de soluciones**, seleccione **Agregar**y, a continuación, **nuevo elemento.** ..</span><span class="sxs-lookup"><span data-stu-id="864eb-155">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="864eb-156">para abrir el cuadro de diálogo **Agregar nuevo elemento** y seleccione la categoría de **flujo de trabajo** , en la sección **plantillas instaladas** de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="864eb-156">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

22. <span data-ttu-id="864eb-157">Seleccione la plantilla de **actividad de código** , asígnele un nombre `SimpleNativeActivity` y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="864eb-157">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>

23. <span data-ttu-id="864eb-158">Implemente la `SimpleNativeActivity` clase escribiendo el código siguiente en el archivo *SimpleNativeActivity.CS* :</span><span class="sxs-lookup"><span data-stu-id="864eb-158">Implement the `SimpleNativeActivity` class by entering the following code into the *SimpleNativeActivity.cs* file:</span></span>

    ```csharp
    using System.Activities;

    namespace UsingWorkflowItemPresenter
    {
        public sealed class SimpleNativeActivity : NativeActivity
        {
            // this property contains an activity that will be scheduled in the execute method
            // the WorkflowItemPresenter in the designer is bound to this to enable editing
            // of the value
            public Activity Body { get; set; }

            protected override void CacheMetadata(NativeActivityMetadata metadata)
            {
               metadata.AddChild(Body);
               base.CacheMetadata(metadata);

            }

            protected override void Execute(NativeActivityContext context)
            {
                context.ScheduleActivity(Body);
            }
        }
    }
    ```

24. <span data-ttu-id="864eb-159">Seleccione **compilar solución** en el menú **compilar** .</span><span class="sxs-lookup"><span data-stu-id="864eb-159">Select **Build Solution** from the **Build** menu.</span></span>

25. <span data-ttu-id="864eb-160">Seleccione **iniciar sin depurar** en el menú **depurar** para abrir la ventana de diseño personalizado hospedada en otro host.</span><span class="sxs-lookup"><span data-stu-id="864eb-160">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="864eb-161">Para crear un diseñador de actividad personalizado mediante WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="864eb-161">To create a custom activity designer using WorkflowItemsPresenter</span></span>

1. <span data-ttu-id="864eb-162">El procedimiento para el segundo diseñador de actividad personalizado es el paralelo el primero con algunas modificaciones, el primero de los cuales es asignar un nombre a la segunda aplicación `UsingWorkflowItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="864eb-162">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="864eb-163">Esta aplicación tampoco define una nueva actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="864eb-163">Also this application does not define a new custom activity.</span></span>

2. <span data-ttu-id="864eb-164">Las diferencias clave están contenidas en los archivos *CustomParallelDesigner. Xaml* y *RehostingWFDesigner.Xaml.CS* .</span><span class="sxs-lookup"><span data-stu-id="864eb-164">Key differences are contained in the *CustomParallelDesigner.xaml* and *RehostingWFDesigner.xaml.cs* files.</span></span> <span data-ttu-id="864eb-165">Este es el código del archivo *CustomParallelDesigner. Xaml* que define la interfaz de usuario:</span><span class="sxs-lookup"><span data-stu-id="864eb-165">Here is the code from the *CustomParallelDesigner.xaml* file that defines the UI:</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <TextBlock>This is the Collapsed View</TextBlock>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"
                                        Items="{Binding Path=ModelItem.Branches}">
                        <sap:WorkflowItemsPresenter.SpacerTemplate>
                            <DataTemplate>
                                <Ellipse Width="10" Height="10" Fill="Black"/>
                            </DataTemplate>
                        </sap:WorkflowItemsPresenter.SpacerTemplate>
                        <sap:WorkflowItemsPresenter.ItemsPanel>
                            <ItemsPanelTemplate>
                                <StackPanel Orientation="Horizontal"/>
                            </ItemsPanelTemplate>
                        </sap:WorkflowItemsPresenter.ItemsPanel>
                    </sap:WorkflowItemsPresenter>
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
        </Grid>
    </sap:ActivityDesigner>
    ```

3. <span data-ttu-id="864eb-166">Este es el código del archivo *RehostingWFDesigner.Xaml.CS* que proporciona la lógica de rehospedaje:</span><span class="sxs-lookup"><span data-stu-id="864eb-166">Here is the code from the *RehostingWFDesigner.xaml.cs* file that provides the rehosting logic:</span></span>

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespaceUsingWorkflowItemsPresenter
    {
        public partial class RehostingWfDesigner : Window
        {
            public RehostingWfDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="864eb-167">Consulta también</span><span class="sxs-lookup"><span data-stu-id="864eb-167">See also</span></span>

- <xref:System.Activities.Presentation.ActivityDesigner>
- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- <xref:System.Activities.Presentation.WorkflowViewElement>
- <xref:System.Activities.Presentation.Model.ModelItem>
- [<span data-ttu-id="864eb-168">Personalizar la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="864eb-168">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
