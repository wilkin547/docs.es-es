---
title: Rehospedaje del diseñador
ms.date: 03/30/2017
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
ms.openlocfilehash: b72e3450799db40988c8b99e4db3707de330d8ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182818"
---
# <a name="designer-rehosting"></a><span data-ttu-id="a1a98-102">Rehospedaje del diseñador</span><span class="sxs-lookup"><span data-stu-id="a1a98-102">Designer Rehosting</span></span>
<span data-ttu-id="a1a98-103">El rehospedaje del diseñador es un escenario común que hace referencia al hospedaje del lienzo de diseño de flujo de trabajo dentro de una aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a1a98-103">Designer rehosting is a common scenario that refers to hosting the workflow design canvas inside of a custom application.</span></span> <span data-ttu-id="a1a98-104">La aplicación de hospedaje con la que están familiarizados la mayoría de los usuarios es Visual Studio; sin embargo, hay varios escenarios donde puede resultar útil mostrar el diseñador de flujo de trabajo en una aplicación:</span><span class="sxs-lookup"><span data-stu-id="a1a98-104">The hosting application most people are familiar with is Visual Studio, however there are a number of scenarios where showing the workflow designer in an application may be useful:</span></span>  
  
- <span data-ttu-id="a1a98-105">Aplicaciones de supervisión (que permiten a un usuario final visualizar el proceso, así como datos en tiempo de ejecución sobre el proceso, como el estado activo actual, los datos de tiempo de ejecución agregados o información de otro tipo sobre una instancia del flujo de trabajo).</span><span class="sxs-lookup"><span data-stu-id="a1a98-105">Monitoring applications (allowing an end user to visualize the process, as well as runtime data about the process such as the currently active state, aggregate execution time data, or other information about an instance of the workflow).</span></span>  
  
- <span data-ttu-id="a1a98-106">Aplicaciones que permiten a un usuario personalizar el proceso con un conjunto limitado de actividades.</span><span class="sxs-lookup"><span data-stu-id="a1a98-106">Applications that allow a user to customize the process with a limited set of activities.</span></span>  
  
 <span data-ttu-id="a1a98-107">Para admitir estos tipos de aplicaciones, el diseñador de flujo de trabajo se distribuye dentro de .NET Framework y se puede hospedar dentro de una aplicación WPF o en una aplicación Winforms con el código de hospedaje de WPF adecuado.</span><span class="sxs-lookup"><span data-stu-id="a1a98-107">To support these types of applications, the workflow designer ships inside the .NET Framework, and can be hosted inside a WPF application, or in a WinForms application with the appropriate WPF hosting code.</span></span> <span data-ttu-id="a1a98-108">En este ejemplo se muestra:</span><span class="sxs-lookup"><span data-stu-id="a1a98-108">This sample demonstrates:</span></span>  
  
- <span data-ttu-id="a1a98-109">Rehospedar el diseñador WF.</span><span class="sxs-lookup"><span data-stu-id="a1a98-109">Rehosting the WF designer.</span></span>  
  
- <span data-ttu-id="a1a98-110">Utilizar el cuadro de herramientas y la cuadrícula de propiedad hospedados en otro host.</span><span class="sxs-lookup"><span data-stu-id="a1a98-110">Using the rehosted toolbox and property grid as well.</span></span>  
  
## <a name="rehosting-the-designer"></a><span data-ttu-id="a1a98-111">Rehospedar el diseñador</span><span class="sxs-lookup"><span data-stu-id="a1a98-111">Rehosting the designer</span></span>  
 <span data-ttu-id="a1a98-112">En este ejemplo se muestra cómo crear el diseño de WPF para contener el diseñador, que se ve en el siguiente diseño de cuadrícula (el código del cuadro de herramientas se omite por problemas de espacio).</span><span class="sxs-lookup"><span data-stu-id="a1a98-112">This sample shows how to create the WPF layout to contain the designer, seen in the following grid layout (Toolbox code omitted for space concerns).</span></span> <span data-ttu-id="a1a98-113">Tenga en cuenta la denominación de los bordes que contienen el diseñador y la cuadrícula de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a1a98-113">Note the naming of the borders which contain the designer and property grid.</span></span>  
  
```xaml  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="2*"/>  
        <ColumnDefinition Width="7*"/>  
        <ColumnDefinition Width="3*"/>  
    </Grid.ColumnDefinitions>  
    <Border Grid.Column="0">  
        <sapt:ToolboxControl>...</sapt:ToolboxControl>  
    </Border>  
    <Border Grid.Column="1" Name="DesignerBorder"/>  
    <Border Grid.Column="2" Name="PropertyBorder"/>  
</Grid>  
```  
  
 <span data-ttu-id="a1a98-114">A continuación, el ejemplo crea el diseñador y asocia sus propiedades <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> y <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> primarias al contenedor adecuado en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a1a98-114">Next the sample creates the designer, and associates its primary <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> with the appropriate container in the user interface.</span></span> <span data-ttu-id="a1a98-115">Hay algunas líneas adicionales de código en el siguiente ejemplo que merecen explicación.</span><span class="sxs-lookup"><span data-stu-id="a1a98-115">There are a few additional lines of code in the following example that merit some explanation.</span></span> <span data-ttu-id="a1a98-116">La <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> llamada es necesaria para asociar los diseñadores de actividad predeterminados para las actividades incluidas con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a1a98-116">The <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> call is required to associate the default activity designers for the activities shipped with .NET Framework.</span></span> <span data-ttu-id="a1a98-117">Se llama a <xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> para pasar el elemento de WF que se va a editar.</span><span class="sxs-lookup"><span data-stu-id="a1a98-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> is called to pass in the WF item to be edited.</span></span> <span data-ttu-id="a1a98-118">Por último, las propiedades <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (lienzo primario) y <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (cuadrícula de propiedad) se colocan en la superficie de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a1a98-118">Finally, the <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primary canvas) and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (property grid) are placed onto the user interface surface.</span></span>  
  
```csharp  
protected override void OnInitialized(EventArgs e)  
{  
   base.OnInitialized(e);  
   // register metadata  
   (new DesignerMetadata()).Register();  
  
   // create the workflow designer  
   WorkflowDesigner wd = new WorkflowDesigner();  
   wd.Load(new Sequence());  
   DesignerBorder.Child = wd.View;  
   PropertyBorder.Child = wd.PropertyInspectorView;  
}  
```  
  
## <a name="using-the-rehosted-toolbox"></a><span data-ttu-id="a1a98-119">Utilizar el cuadro de herramientas hospedado en otro host</span><span class="sxs-lookup"><span data-stu-id="a1a98-119">Using the rehosted toolbox</span></span>  
 <span data-ttu-id="a1a98-120">Este ejemplo utiliza el control del cuadro de herramientas hospedado en otro host mediante declaración en XAML.</span><span class="sxs-lookup"><span data-stu-id="a1a98-120">This sample uses the rehosted toolbox control declaratively in XAML.</span></span> <span data-ttu-id="a1a98-121">Observe que en el código, se puede pasar un tipo al constructor <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper>.</span><span class="sxs-lookup"><span data-stu-id="a1a98-121">Note that in code, one can pass a type to the <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> constructor.</span></span>  
  
```xaml  
<!-- Copyright (c) Microsoft Corporation. All rights reserved-->  
<Window x:Class="Microsoft.Samples.DesignerRehosting.RehostingWfDesigner"  
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
            <sapt:ToolboxControl>  
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
  
#### <a name="using-the-sample"></a><span data-ttu-id="a1a98-122">Utilizar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1a98-122">Using the sample</span></span>  
  
1. <span data-ttu-id="a1a98-123">Abra la solución DesignerRehosting.sln en Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="a1a98-123">Open the DesignerRehosting.sln solution in Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="a1a98-124">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a1a98-124">Press F5 to compile and run the application.</span></span>  
  
3. <span data-ttu-id="a1a98-125">Una aplicación WPF se inicia con un diseñador hospedado en otro host.</span><span class="sxs-lookup"><span data-stu-id="a1a98-125">A WPF application starts with a rehosted designer.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a1a98-126">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a1a98-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a1a98-127">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a1a98-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a1a98-128">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a1a98-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a1a98-129">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a1a98-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`
