---
title: 'Extensibilidad de cuadrícula de propiedades: ejemplo de WF'
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: 130d8702795bccf0d5f28b5c0940bd7c25be3556
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715605"
---
# <a name="property-grid-extensibility"></a><span data-ttu-id="ee98a-102">Extensibilidad de cuadrícula de propiedades</span><span class="sxs-lookup"><span data-stu-id="ee98a-102">Property grid extensibility</span></span>

<span data-ttu-id="ee98a-103">Un desarrollador puede personalizar la cuadrícula de propiedad que se muestra cuando una actividad determinada se selecciona dentro del diseñador.</span><span class="sxs-lookup"><span data-stu-id="ee98a-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="ee98a-104">Esto se puede hacer para crear una experiencia de edición enriquecida.</span><span class="sxs-lookup"><span data-stu-id="ee98a-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="ee98a-105">En este ejemplo se muestra cómo llevarlo a cabo.</span><span class="sxs-lookup"><span data-stu-id="ee98a-105">This sample shows how this can be done.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ee98a-106">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="ee98a-106">Demonstrates</span></span>

<span data-ttu-id="ee98a-107">Extensibilidad de la cuadrícula de propiedad del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ee98a-107">Workflow designer property grid extensibility.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee98a-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ee98a-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ee98a-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ee98a-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="ee98a-110">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee98a-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee98a-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ee98a-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a><span data-ttu-id="ee98a-112">Discusión</span><span class="sxs-lookup"><span data-stu-id="ee98a-112">Discussion</span></span>

<span data-ttu-id="ee98a-113">Para ampliar la cuadrícula de propiedad, un desarrollador dispone de opciones para personalizar el aspecto alineado de un editor de cuadrícula de propiedad o para proporcionar un cuadro de diálogo que aparece para una superficie de edición más avanzada.</span><span class="sxs-lookup"><span data-stu-id="ee98a-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="ee98a-114">En este ejemplo se muestran dos editores diferentes; un editor alineado y un editor de cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ee98a-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>

## <a name="inline-editor"></a><span data-ttu-id="ee98a-115">Editor insertado</span><span class="sxs-lookup"><span data-stu-id="ee98a-115">Inline editor</span></span>

<span data-ttu-id="ee98a-116">En el ejemplo del editor alineado se muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee98a-116">The inline editor sample demonstrates the following:</span></span>

- <span data-ttu-id="ee98a-117">Crea un tipo que deriva de <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span><span class="sxs-lookup"><span data-stu-id="ee98a-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>

- <span data-ttu-id="ee98a-118">En el constructor, el valor de <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> se establece con una plantilla de datos de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ee98a-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="ee98a-119">Se puede enlazar a una plantilla XAML, pero en este ejemplo, se utiliza código para inicializar el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="ee98a-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>

- <span data-ttu-id="ee98a-120">La plantilla de datos tiene un contexto de datos de <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> del elemento presentado en la cuadrícula de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ee98a-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="ee98a-121">Observe en el siguiente código (de CustomInlineEditor.cs) que este contexto enlaza a la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="ee98a-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>

    ```csharp
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));
    Binding sliderBinding = new Binding("Value");
    sliderBinding.Mode = BindingMode.TwoWay;
    slider.SetValue(Slider.MinimumProperty, 0.0);
    slider.SetValue(Slider.MaximumProperty, 100.0);
    slider.SetValue(Slider.ValueProperty, sliderBinding);
    stack.AppendChild(slider);
    ```

- <span data-ttu-id="ee98a-122">Dado que la actividad y el diseñador se encuentran en el mismo ensamblado, el registro de los atributos del diseñador de actividad se realiza en el constructor estático de la propia actividad, tal como se muestra en el siguiente ejemplo de SimpleCodeActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="ee98a-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a><span data-ttu-id="ee98a-123">Editor de cuadros de diálogo</span><span class="sxs-lookup"><span data-stu-id="ee98a-123">Dialog editor</span></span>

<span data-ttu-id="ee98a-124">En el ejemplo del editor de cuadros de diálogo se muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee98a-124">The dialog editor sample demonstrates the following:</span></span>

1. <span data-ttu-id="ee98a-125">Crea un tipo que deriva de <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span><span class="sxs-lookup"><span data-stu-id="ee98a-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>

2. <span data-ttu-id="ee98a-126">Establece el valor de <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> en el constructor con una plantilla de datos de WPF.</span><span class="sxs-lookup"><span data-stu-id="ee98a-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a WPF data template.</span></span> <span data-ttu-id="ee98a-127">Se puede crear en XAML, pero en este ejemplo se crea en código.</span><span class="sxs-lookup"><span data-stu-id="ee98a-127">This can be created in XAML, but in this sample, this is created in code.</span></span>

3. <span data-ttu-id="ee98a-128">La plantilla de datos tiene un contexto de datos de <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> del elemento presentado en la cuadrícula de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ee98a-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="ee98a-129">En el siguiente código, a continuación se enlaza a la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="ee98a-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="ee98a-130">Es importante incluir también una clase <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> para proporcionar el botón que muestra el cuadro de diálogo en FilePickerEditor.cs.</span><span class="sxs-lookup"><span data-stu-id="ee98a-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>

    ```csharp
    this.InlineEditorTemplate = new DataTemplate();

    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));
    Binding labelBinding = new Binding("Value");
    label.SetValue(Label.ContentProperty, labelBinding);
    label.SetValue(Label.MaxWidthProperty, 90.0);

    stack.AppendChild(label);

    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));

    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);

    stack.AppendChild(editModeSwitch);

    this.InlineEditorTemplate.VisualTree = stack;
    ```

4. <span data-ttu-id="ee98a-131">Invalida el método <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> en el tipo de diseñador para administrar la presentación del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ee98a-131">Overrides the <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="ee98a-132">En este ejemplo, se muestra un objeto <xref:System.Windows.Forms.FileDialog> básico.</span><span class="sxs-lookup"><span data-stu-id="ee98a-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>

    ```csharp
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)
    {
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();
        if (ofd.ShowDialog() == true)
        {
            propertyValue.Value = ofd.FileName;
        }
    }
    ```

5. <span data-ttu-id="ee98a-133">Dado que la actividad y el diseñador se encuentran en el mismo ensamblado, el registro de los atributos del diseñador de actividad se realiza en el constructor estático de la propia actividad, tal como se muestra en el siguiente ejemplo de SimpleCodeActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="ee98a-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ee98a-134">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee98a-134">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="ee98a-135">Compile la solución y, a continuación, abra Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="ee98a-135">Build the solution, and then open Workflow1.xaml.</span></span>

2. <span data-ttu-id="ee98a-136">Arrastre un **SimpleCodeActivity** desde el cuadro de herramientas hasta el lienzo del diseñador.</span><span class="sxs-lookup"><span data-stu-id="ee98a-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>

3. <span data-ttu-id="ee98a-137">Haga clic en **SimpleCodeActivity** y, a continuación, abra la cuadrícula de propiedades donde hay un control deslizante y un control de selección de archivos.</span><span class="sxs-lookup"><span data-stu-id="ee98a-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee98a-138">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ee98a-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ee98a-139">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ee98a-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="ee98a-140">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee98a-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee98a-141">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ee98a-141">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
