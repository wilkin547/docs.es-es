---
title: "Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b529d1c150f686fb4a39f968001c9ac03c7c1dc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo
El <xref:System.Activities.Presentation.WorkflowItemPresenter> es un tipo de clave en el modelo de programación Diseñador de WF que permite la creación de una "zona de colocación" donde se puede colocar una actividad arbitraria. Este ejemplo muestra cómo compilar un diseñador de actividades que muestre este tipo "zona de colocación."  
  
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
  
 Observe el uso de enlace de datos de WPF para enlazarse a `ModelItem.Body`. `ModelItem`es la propiedad de <xref:System.Activities.Presentation.ActivityDesigner> que hace referencia al objeto subyacente para el diseñador está usándola para, en este caso, **SimpleNativeActivity**.  
  
#### <a name="to-setup-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [Desarrollar aplicaciones con el Diseñador de flujo de trabajo](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
