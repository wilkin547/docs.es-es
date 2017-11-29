---
title: Enlace de datos en un cliente de Windows Presentation Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0fba3f83bbff42f570ce6da1544d2c0f1ea32393
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a>Enlace de datos en un cliente de Windows Presentation Foundation
Este ejemplo muestra el uso de enlace de datos en un cliente de la Windows Presentation Foundation (WPF). El ejemplo utiliza un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que genera de manera aleatoria genera una matriz de álbumes para devolver al cliente. Cada álbum tiene un nombre, un precio y una lista de pistas. Las pistas del álbum tienen un nombre y duración. La información que devuelve el servicio se enlaza automáticamente a la interfaz de usuario (IU) que proporciona el cliente de [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)].  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El enlace de datos permite enlazar un origen de datos automáticamente a una Interfaz de usuario. Esto simplifica el modelo de programación porque no requiere que usted actualice mediante programación cada elemento de la interfaz de usuario con los datos de un objeto de datos o una matriz de objetos de datos. Puede enlazar un objeto a un elemento de la interfaz de usuario único o una matriz a un control que toma varias entradas, como un `ListBox`. El código siguiente muestra cómo enlazar los datos a `DataContext` de un elemento de la interfaz de usuario.  
  
```  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;   
}  
```  
  
 En el ejemplo anterior, `DataContext` para el elemento de diseño `grid` denominado `myPanel` está establecido en los datos devueltos por el método `GetAlbumList`. `DataContext` permite a los elementos heredar información de sus elementos principales sobre el origen de datos que se utiliza para enlazar, así como otras características del enlace como la ruta de acceso. La línea de código se debe ejecutar cada vez que se actualizan los datos en el servidor. Por ejemplo, se ejecuta cuando se inicializa la ventana y cuando se agrega un nuevo álbum.  
  
 En el ejemplo siguiente de código XAML, `ListBox` especifica `ItemsSource="{Binding }"`.  
  
```xml  
<ListBox   
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"   
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 Esto especifica que los datos enlazados al elemento de la interfaz de usuario de nivel superior también está enlazado a este control (es decir, la matriz de Álbumes). Además, `ItemTemplate="{StaticResource AlbumStyle}"` especifica la plantilla de datos que se va a utilizar para cada elemento en `ListBox`. También puede definir las plantillas de datos para especificar cómo se debería dar formato a los datos. Estas plantillas de datos se pueden reutilizar para otros elementos de la interfaz de usuario en la aplicación, la ventaja es que la plantilla de datos se define y mantiene en un lugar.  
  
 La plantilla de datos `AlbumStyle` pone en paralelo una cuadrícula con dos `TextBlock`s. Uno especifica el nombre del Álbum y el otro el número de Pistas en el álbum.  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 El siguiente código XAML crea un segundo`ListBox`.  
  
```xaml  
<ListBox Grid.Row="2"   
            Grid.ColumnSpan="2"   
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 El código especifica una ruta de acceso para `ItemsSource`. Esto indica que el límite de los datos enlazados con este control no son los datos de nivel superior sino una propiedad de los datos de nivel superior denominada `Tracks`. Esta propiedad representa la matriz de pistas contenida dentro del álbum. Además, se especifica un `DataTemplate` diferente denominado`TrackStyle` . El diseño de la plantilla `TrackStyle` es similar al de la plantilla `AlbumStyle`, pero `TextBlock`s se enlazan a diferentes propiedades. Esto es porque las dos plantillas se utilizan con objetos de datos diferentes.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
  
## <a name="see-also"></a>Vea también
