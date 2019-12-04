---
title: Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: 542440d6bf9d6809abee1ec37c85c44ce72fd132
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715157"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a>Diseñadores compuestos personalizados - Moderador de elementos de flujo de trabajo

<xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> es un tipo clave en el modelo de programación de diseñador de WF que permite la edición de una colección de elementos incluidos. En este ejemplo se muestra cómo compilar un diseñador de actividad que muestra este tipo de colección modificable.

En este ejemplo se explica cómo:

- Crear un diseñador de actividad personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.

- Crear un diseñador de actividad con una vista "contraída" y "expandida".

- Invalidar un diseñador predeterminado en una aplicación hospedada en otro host.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Abra la solución de ejemplo **UsingWorkflowItemsPresenter. sln** para C# o para VB en Visual Studio 2010.

2. Compile y ejecute la solución. Se debe abrir una aplicación de diseñador de flujo de trabajo hospedada en otro host; puede arrastrar actividades al lienzo.

## <a name="sample-highlights"></a>Aspectos que se deben destacar del ejemplo

El código de este ejemplo muestra lo siguiente:

- La actividad para la que se compila un diseñador: `Parallel`

- La creación de un diseñador de actividades personalizado con un objeto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>. Elementos que se deben señalar:

  - Observe el uso de enlace de datos de WPF para enlazarse a `ModelItem.Branches`. `ModelItem` es la propiedad de `WorkflowElementDesigner` que hace referencia al objeto subyacente para el que se está usando el diseñador, en este caso nuestro `Parallel`.

  - La propiedad <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> se puede utilizar para colocar un elemento visual que se mostrará entre los elementos individuales de la colección.

  - La propiedad <xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> es una plantilla que se puede proporcionar para determinar el diseño de los elementos de la colección. En este caso, se usa un panel de apilamiento horizontal.

  El ejemplo de código siguiente muestra cómo hacerlo.

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

- Realice una asociación de `DesignerAttribute` al tipo `Parallel` y, a continuación, genere los atributos indicados.

  - En primer lugar, registre todos los diseñadores predeterminados.

    A continuación se muestra el ejemplo de código.

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

  - A continuación, invalide el paralelo en el método `RegisterCustomMetadata`.

    El siguiente código muestra esta acción en C# y Visual Basic.

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

- Por último, observe el uso de diferentes plantillas de datos y desencadenadores para seleccionar la plantilla adecuada en función de la propiedad `IsRootDesigner`.

  A continuación se muestra el ejemplo de código.

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
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`

## <a name="see-also"></a>Vea también

- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [Desarrollar aplicaciones con el Diseñador de flujo de trabajo](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
