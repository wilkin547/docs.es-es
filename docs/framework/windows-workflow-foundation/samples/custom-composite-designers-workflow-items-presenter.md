---
title: Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: 403b0125e6b1966d201c891448ad25ec83f42be5
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881929"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a><span data-ttu-id="b0e5f-102">Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b0e5f-102">Custom Composite Designers - Workflow Items Presenter</span></span>

<span data-ttu-id="b0e5f-103"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> es un tipo clave en el modelo de programación de diseñador de WF que permite la edición de una colección de elementos incluidos.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-103">The <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> is a key type in the WF designer programming model that allows for the editing of a collection of contained elements.</span></span> <span data-ttu-id="b0e5f-104">En este ejemplo se muestra cómo compilar un diseñador de actividad que muestra este tipo de colección modificable.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-104">This sample shows how to build an activity designer that surfaces such an editable collection.</span></span>

<span data-ttu-id="b0e5f-105">En este ejemplo se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="b0e5f-105">This sample demonstrates:</span></span>

- <span data-ttu-id="b0e5f-106">Crear un diseñador de actividad personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="b0e5f-107">Creación de un diseñador de actividad con una vista "contraída" y "expandida".</span><span class="sxs-lookup"><span data-stu-id="b0e5f-107">Creating an activity designer with a "collapsed" and "expanded" view.</span></span>

- <span data-ttu-id="b0e5f-108">Invalidar un diseñador predeterminado en una aplicación hospedada en otro host.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-108">Overriding a default designer in a rehosted application.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0e5f-109">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0e5f-109">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="b0e5f-110">Abra el **UsingWorkflowItemsPresenter.sln** solución de ejemplo para C# o VB en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-110">Open the **UsingWorkflowItemsPresenter.sln** sample solution for C# or for VB in Visual Studio 2010.</span></span>

2. <span data-ttu-id="b0e5f-111">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-111">Build and run the solution.</span></span> <span data-ttu-id="b0e5f-112">Se debe abrir una aplicación de diseñador de flujo de trabajo hospedada en otro host; puede arrastrar actividades al lienzo.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-112">A rehosted workflow designer application should open, and you can drag activities onto the canvas.</span></span>

## <a name="sample-highlights"></a><span data-ttu-id="b0e5f-113">Aspectos que se deben destacar del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0e5f-113">Sample Highlights</span></span>

<span data-ttu-id="b0e5f-114">El código de este ejemplo muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0e5f-114">The code for this sample shows the following:</span></span>

- <span data-ttu-id="b0e5f-115">La actividad para la que se compila un diseñador: `Parallel`</span><span class="sxs-lookup"><span data-stu-id="b0e5f-115">The activity a designer is built for:  `Parallel`</span></span>

- <span data-ttu-id="b0e5f-116">La creación de un diseñador de actividades personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-116">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b0e5f-117">Elementos que se deben señalar:</span><span class="sxs-lookup"><span data-stu-id="b0e5f-117">A few things to point out:</span></span>

  - <span data-ttu-id="b0e5f-118">Observe el uso de enlace de datos de WPF para enlazarse a `ModelItem.Branches`.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-118">Note the use of WPF data binding to bind to `ModelItem.Branches`.</span></span> <span data-ttu-id="b0e5f-119">`ModelItem` es la propiedad de `WorkflowElementDesigner` que hace referencia al objeto subyacente para el que se está usando el diseñador, en este caso nuestro `Parallel`.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-119">`ModelItem` is the property on `WorkflowElementDesigner` that refers to the underlying object the designer is being used for, in this case, our `Parallel`.</span></span>

  - <span data-ttu-id="b0e5f-120">La propiedad <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> se puede utilizar para colocar un elemento visual que se mostrará entre los elementos individuales de la colección.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-120">The <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> can be used to put a visual to display between the individual items in the collection.</span></span>

  - <span data-ttu-id="b0e5f-121">La propiedad <xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> es una plantilla que se puede proporcionar para determinar el diseño de los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> is a template that can be provided to determine the layout of the items in the collection.</span></span> <span data-ttu-id="b0e5f-122">En este caso, se usa un panel de apilamiento horizontal.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-122">In this case, a horizontal stack panel is used.</span></span>

  <span data-ttu-id="b0e5f-123">El ejemplo de código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-123">This following example code shows this.</span></span>
  
  ```xaml
  <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                Items="{Binding Path=ModelItem.Branches}">
      <sad:WorkflowItemsPresenter.SpacerTemplate>
        <DataTemplate>
          <Ellipse Width="10" Height="10" Fill="Black"/>
        </DataTemplate>
      </sad:WorkflowItemsPresenter.SpacerTemplate>
      <sad:WorkflowItemsPresenter.ItemsPanel>
        <ItemsPanelTemplate>
          <StackPanel Orientation="Horizontal"/>
        </ItemsPanelTemplate>
      </sad:WorkflowItemsPresenter.ItemsPanel>
    </sad:WorkflowItemsPresenter>
  ```

- <span data-ttu-id="b0e5f-124">Realice una asociación de `DesignerAttribute` al tipo `Parallel` y, a continuación, genere los atributos indicados.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-124">Perform an association of the `DesignerAttribute` to the `Parallel` type and then output the attributes reported.</span></span>

    - <span data-ttu-id="b0e5f-125">En primer lugar, registre todos los diseñadores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-125">First, register all of the default designers.</span></span>

    <span data-ttu-id="b0e5f-126">A continuación se muestra el ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-126">The following is the code example.</span></span>

    ```csharp
    // register metadata
    (new DesignerMetadata()).Register();
    RegisterCustomMetadata();
    ```

    ```vb
    ' register metadata
    Dim metadata = New DesignerMetadata()
    metadata.Register()
    ' register custom metadata
    RegisterCustomMetadata()
    ```

    - <span data-ttu-id="b0e5f-127">A continuación, invalide el paralelo en el método `RegisterCustomMetadata`.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-127">Then, override the parallel in `RegisterCustomMetadata` method.</span></span>

    <span data-ttu-id="b0e5f-128">El siguiente código muestra esta acción en C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-128">The following code shows this in C# and Visual Basic.</span></span>

    ```csharp
    void RegisterCustomMetadata()
    {
          AttributeTableBuilder builder = new AttributeTableBuilder();
          builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
          MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

    ```vb
    Sub RegisterCustomMetadata()
       Dim builder As New AttributeTableBuilder()
       builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))
       MetadataStore.AddAttributeTable(builder.CreateTable())
    End Sub
    ```

- <span data-ttu-id="b0e5f-129">Por último, observe el uso de diferentes plantillas de datos y desencadenadores para seleccionar la plantilla adecuada en función de la propiedad `IsRootDesigner`.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-129">Finally, note the use of differing data templates and triggers to select the appropriate template based on the `IsRootDesigner` property.</span></span>

  <span data-ttu-id="b0e5f-130">A continuación se muestra el ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-130">The following is the code example.</span></span>

  ```xaml
  <sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"
      xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">
    <sad:ActivityDesigner.Resources>
      <DataTemplate x:Key="Expanded">
        <StackPanel>
          <TextBlock>This is the Expanded View</TextBlock>
          <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                      Items="{Binding Path=ModelItem.Branches}">
            <sad:WorkflowItemsPresenter.SpacerTemplate>
              <DataTemplate>
                <Ellipse Width="10" Height="10" Fill="Black"/>
              </DataTemplate>
            </sad:WorkflowItemsPresenter.SpacerTemplate>
            <sad:WorkflowItemsPresenter.ItemsPanel>
              <ItemsPanelTemplate>
                <StackPanel Orientation="Horizontal"/>
              </ItemsPanelTemplate>
            </sad:WorkflowItemsPresenter.ItemsPanel>
          </sad:WorkflowItemsPresenter>
        </StackPanel>
      </DataTemplate>
      <DataTemplate x:Key="Collapsed">
        <TextBlock>This is the Collapsed View</TextBlock>
      </DataTemplate>
      <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
        <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
        <Style.Triggers>
          <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">
            <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
          </DataTrigger>
        </Style.Triggers>
      </Style>
    </sad: ActivityDesigner.Resources>
    <Grid>
      <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
    </Grid>
  </sad: ActivityDesigner>
  ```

> [!IMPORTANT]
> <span data-ttu-id="b0e5f-131">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b0e5f-132">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="b0e5f-133">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0e5f-134">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b0e5f-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`

## <a name="see-also"></a><span data-ttu-id="b0e5f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0e5f-135">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [<span data-ttu-id="b0e5f-136">Desarrollar aplicaciones con el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b0e5f-136">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
