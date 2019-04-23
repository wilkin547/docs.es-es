---
title: Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: f3c7620f719b8412b6b34bda7be5d607dccda75f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311128"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="e12f8-102">Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e12f8-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="e12f8-103">El <xref:System.Activities.Presentation.WorkflowItemPresenter> es un tipo de clave en el modelo de programación Diseñador de WF que permite la creación de una "zona de colocación" donde se puede colocar una actividad arbitraria.</span><span class="sxs-lookup"><span data-stu-id="e12f8-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="e12f8-104">Este ejemplo muestra cómo crear a un diseñador de actividad que se muestra este tipo una "zona de colocación."</span><span class="sxs-lookup"><span data-stu-id="e12f8-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

 <span data-ttu-id="e12f8-105">En este ejemplo se explica cómo:</span><span class="sxs-lookup"><span data-stu-id="e12f8-105">This sample demonstrates:</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e12f8-106">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="e12f8-106">Demonstrates</span></span>

-   <span data-ttu-id="e12f8-107">Crear un diseñador de actividad personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="e12f8-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

-   <span data-ttu-id="e12f8-108">Registrar el diseñador personalizado mediante el almacén de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e12f8-108">Registering the custom designer using the metadata store.</span></span>

-   <span data-ttu-id="e12f8-109">Programar el cuadro de herramientas hospedado en otro host de manera imperativa o mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="e12f8-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="e12f8-110">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e12f8-110">Sample Details</span></span>
 <span data-ttu-id="e12f8-111">El código de este ejemplo muestra:</span><span class="sxs-lookup"><span data-stu-id="e12f8-111">The code for this sample shows:</span></span>

-   <span data-ttu-id="e12f8-112">La compilación del diseñador de actividades personalizado para la clase `SimpleNativeActivity`.</span><span class="sxs-lookup"><span data-stu-id="e12f8-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

-   <span data-ttu-id="e12f8-113">La creación de un diseñador de actividades personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="e12f8-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

```xaml
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"
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

 <span data-ttu-id="e12f8-114">Observe el uso de enlace de datos de WPF para enlazarse a `ModelItem.Body`.</span><span class="sxs-lookup"><span data-stu-id="e12f8-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="e12f8-115">`ModelItem` es la propiedad de <xref:System.Activities.Presentation.ActivityDesigner> que hace referencia al objeto subyacente es usando el diseñador, en este caso, **SimpleNativeActivity**.</span><span class="sxs-lookup"><span data-stu-id="e12f8-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="e12f8-116">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e12f8-116">To setup, build, and run the sample</span></span>

1. <span data-ttu-id="e12f8-117">Abra la solución en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="e12f8-117">Open the solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="e12f8-118">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e12f8-118">Press F5 to compile and run the application.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e12f8-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e12f8-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e12f8-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e12f8-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e12f8-121">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e12f8-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e12f8-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e12f8-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="e12f8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e12f8-123">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="e12f8-124">Desarrollar aplicaciones con el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e12f8-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
