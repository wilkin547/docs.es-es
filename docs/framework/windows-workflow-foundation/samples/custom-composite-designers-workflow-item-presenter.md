---
title: Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: f3c7620f719b8412b6b34bda7be5d607dccda75f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62005243"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo
El <xref:System.Activities.Presentation.WorkflowItemPresenter> es un tipo de clave en el modelo de programación Diseñador de WF que permite la creación de una "zona de colocación" donde se puede colocar una actividad arbitraria. Este ejemplo muestra cómo crear a un diseñador de actividad que se muestra este tipo una "zona de colocación."

 En este ejemplo se explica cómo:

## <a name="demonstrates"></a>Demostraciones

-   Crear un diseñador de actividad personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemPresenter>.

-   Registrar el diseñador personalizado mediante el almacén de metadatos.

-   Programar el cuadro de herramientas hospedado en otro host de manera imperativa o mediante declaración.

## <a name="sample-details"></a>Detalles del ejemplo
 El código de este ejemplo muestra:

-   La compilación del diseñador de actividades personalizado para la clase `SimpleNativeActivity`.

-   La creación de un diseñador de actividades personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemPresenter>.

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

 Observe el uso de enlace de datos de WPF para enlazarse a `ModelItem.Body`. `ModelItem` es la propiedad de <xref:System.Activities.Presentation.ActivityDesigner> que hace referencia al objeto subyacente es usando el diseñador, en este caso, **SimpleNativeActivity**.

#### <a name="to-setup-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo

1. Abra la solución en Visual Studio 2010.

2. Presione F5 para compilar y ejecutar la aplicación.

> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [Desarrollar aplicaciones con el Diseñador de flujo de trabajo](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
