---
description: 'Más información sobre: enlace de datos en un cliente de Windows Presentation Foundation'
title: Enlace de datos en un cliente de Windows Presentation Foundation
ms.date: 03/30/2017
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
ms.openlocfilehash: 8bab24dc8f3debb75ddfd712a06f2f035707d42f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755881"
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a><span data-ttu-id="6be99-103">Enlace de datos en un cliente de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="6be99-103">Data Binding in a Windows Presentation Foundation Client</span></span>

<span data-ttu-id="6be99-104">Este ejemplo muestra el uso de enlace de datos en un cliente de la Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="6be99-104">This sample demonstrates the use of data binding in a Windows Presentation Foundation (WPF) client.</span></span> <span data-ttu-id="6be99-105">En el ejemplo se usa un servicio de Windows Communication Foundation (WCF) que genera aleatoriamente una matriz de álbumes para volver al cliente.</span><span class="sxs-lookup"><span data-stu-id="6be99-105">The sample uses a Windows Communication Foundation (WCF) service that randomly generates an array of albums to return to the client.</span></span> <span data-ttu-id="6be99-106">Cada álbum tiene un nombre, un precio y una lista de pistas.</span><span class="sxs-lookup"><span data-stu-id="6be99-106">Each album has a name, a price, and a list of album tracks.</span></span> <span data-ttu-id="6be99-107">Las pistas del álbum tienen un nombre y duración.</span><span class="sxs-lookup"><span data-stu-id="6be99-107">The album tracks have a name and duration.</span></span> <span data-ttu-id="6be99-108">La información que devuelve el servicio se enlaza automáticamente a la interfaz de usuario (UI) proporcionada por el cliente de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="6be99-108">The information that is returned by the service is automatically bound to the user interface (UI) provided by the Windows Presentation Foundation (WPF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6be99-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="6be99-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6be99-110">El enlace de datos permite enlazar un origen de datos automáticamente a una Interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6be99-110">Data binding allows a data source to be automatically bound to a UI.</span></span> <span data-ttu-id="6be99-111">Esto simplifica el modelo de programación porque no requiere que usted actualice mediante programación cada elemento de la interfaz de usuario con los datos de un objeto de datos o una matriz de objetos de datos.</span><span class="sxs-lookup"><span data-stu-id="6be99-111">This simplifies the programming model because it does not require that you programmatically update each UI element with the data from a data object or an array of data objects.</span></span> <span data-ttu-id="6be99-112">Puede enlazar un objeto a un elemento de la interfaz de usuario único o una matriz a un control que toma varias entradas, como un `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="6be99-112">You can bind an object to a single UI element or an array to a control that takes multiple inputs, such as a `ListBox`.</span></span> <span data-ttu-id="6be99-113">El código siguiente muestra cómo enlazar los datos a `DataContext` de un elemento de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6be99-113">The following code shows how to bind data to the `DataContext` of a UI element.</span></span>  
  
```csharp  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;
}  
```  
  
 <span data-ttu-id="6be99-114">En el ejemplo anterior, `DataContext` para el elemento de diseño `grid` denominado `myPanel` está establecido en los datos devueltos por el método `GetAlbumList`.</span><span class="sxs-lookup"><span data-stu-id="6be99-114">In the previous sample, the `DataContext` for the `grid` layout element named `myPanel` is set to the data returned by the `GetAlbumList` method.</span></span> <span data-ttu-id="6be99-115">`DataContext` permite a los elementos heredar información de sus elementos principales sobre el origen de datos que se utiliza para enlazar, así como otras características del enlace como la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="6be99-115">The `DataContext` allows elements to inherit information from their parent elements about the data source that is used for binding, as well as other characteristics of the binding such as the path.</span></span> <span data-ttu-id="6be99-116">La línea de código se debe ejecutar cada vez que se actualizan los datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6be99-116">The line of code must be executed every time the data on the server is updated.</span></span> <span data-ttu-id="6be99-117">Por ejemplo, se ejecuta cuando se inicializa la ventana y cuando se agrega un nuevo álbum.</span><span class="sxs-lookup"><span data-stu-id="6be99-117">For example, it is executed when the window is initialized and when a new album is added.</span></span>  
  
 <span data-ttu-id="6be99-118">En el ejemplo siguiente de código XAML, `ListBox` especifica `ItemsSource="{Binding }"`.</span><span class="sxs-lookup"><span data-stu-id="6be99-118">In the following sample XAML code, the `ListBox` specifies `ItemsSource="{Binding }"`.</span></span>  
  
```xml  
<ListBox
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 <span data-ttu-id="6be99-119">Esto especifica que los datos enlazados al elemento de la interfaz de usuario de nivel superior también está enlazado a este control (es decir, la matriz de Álbumes).</span><span class="sxs-lookup"><span data-stu-id="6be99-119">This specifies that the data bound to the top-level UI element is also bound to this control (that is, the array of Albums).</span></span> <span data-ttu-id="6be99-120">Además, `ItemTemplate="{StaticResource AlbumStyle}"` especifica la plantilla de datos que se va a utilizar para cada elemento en `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="6be99-120">In addition, `ItemTemplate="{StaticResource AlbumStyle}"` specifies the data template to be used for each item in the `ListBox`.</span></span> <span data-ttu-id="6be99-121">También puede definir las plantillas de datos para especificar cómo se debería dar formato a los datos.</span><span class="sxs-lookup"><span data-stu-id="6be99-121">You can also define data templates to specify how the data should be formatted.</span></span> <span data-ttu-id="6be99-122">Estas plantillas de datos se pueden reutilizar para otros elementos de la interfaz de usuario en la aplicación, la ventaja es que la plantilla de datos se define y mantiene en un lugar.</span><span class="sxs-lookup"><span data-stu-id="6be99-122">These data templates can be reused for other UI elements in the application, the advantage is that the data template is defined and maintained in one place.</span></span>  
  
 <span data-ttu-id="6be99-123">La plantilla de datos `AlbumStyle` pone en paralelo una cuadrícula con dos `TextBlock`s.</span><span class="sxs-lookup"><span data-stu-id="6be99-123">The `AlbumStyle` data template lays out a grid with two `TextBlock`s side by side.</span></span> <span data-ttu-id="6be99-124">Uno especifica el nombre del Álbum y el otro el número de Pistas en el álbum.</span><span class="sxs-lookup"><span data-stu-id="6be99-124">One specifies the name of the Album and the other the number of Tracks in the album.</span></span>  
  
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
  
 <span data-ttu-id="6be99-125">El siguiente código XAML crea un segundo`ListBox`.</span><span class="sxs-lookup"><span data-stu-id="6be99-125">The following XAML code creates a second `ListBox`.</span></span>  
  
```xaml  
<ListBox Grid.Row="2"
            Grid.ColumnSpan="2"
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 <span data-ttu-id="6be99-126">El código especifica una ruta de acceso para `ItemsSource`.</span><span class="sxs-lookup"><span data-stu-id="6be99-126">The code specifies a path for the `ItemsSource`.</span></span> <span data-ttu-id="6be99-127">Esto indica que el límite de los datos enlazados con este control no son los datos de nivel superior sino una propiedad de los datos de nivel superior denominada `Tracks`.</span><span class="sxs-lookup"><span data-stu-id="6be99-127">This indicates that the data bound to this control is not the top-level data but a property of the top-level data named `Tracks`.</span></span> <span data-ttu-id="6be99-128">Esta propiedad representa la matriz de pistas contenida dentro del álbum.</span><span class="sxs-lookup"><span data-stu-id="6be99-128">This property represents the array of tracks contained within the album.</span></span> <span data-ttu-id="6be99-129">Además, se especifica un `DataTemplate` diferente denominado`TrackStyle` .</span><span class="sxs-lookup"><span data-stu-id="6be99-129">In addition, a different `DataTemplate` named `TrackStyle` is specified.</span></span> <span data-ttu-id="6be99-130">El diseño de la plantilla `TrackStyle` es similar al de la plantilla `AlbumStyle`, pero `TextBlock`s se enlazan a diferentes propiedades.</span><span class="sxs-lookup"><span data-stu-id="6be99-130">The layout of the `TrackStyle` template is similar to that of the `AlbumStyle` template, but the `TextBlock`s are bound to different properties.</span></span> <span data-ttu-id="6be99-131">Esto es porque las dos plantillas se utilizan con objetos de datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="6be99-131">This is because the two templates are used with different data objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6be99-132">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6be99-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6be99-133">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6be99-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6be99-134">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6be99-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="6be99-135">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6be99-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6be99-136">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6be99-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6be99-137">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6be99-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6be99-138">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6be99-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6be99-139">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6be99-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
