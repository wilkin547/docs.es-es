---
title: Ejemplo de suministros de transmisión por secuencias
ms.date: 03/30/2017
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
ms.openlocfilehash: 17639273ece804dc531cbbc3ab9135c814ea632d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43800033"
---
# <a name="streaming-feeds-sample"></a><span data-ttu-id="8731d-102">Ejemplo de suministros de transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="8731d-102">Streaming Feeds Sample</span></span>
<span data-ttu-id="8731d-103">Este ejemplo muestra cómo administrar las fuentes de sindicación que contienen grandes cantidades de elementos.</span><span class="sxs-lookup"><span data-stu-id="8731d-103">This sample demonstrates how to manage syndication feeds that contain large numbers of items.</span></span> <span data-ttu-id="8731d-104">En el servidor, el ejemplo muestra cómo retrasar la creación de objetos <xref:System.ServiceModel.Syndication.SyndicationItem> individuales dentro de la fuente hasta justo antes de que el elemento se escriba en el flujo de red.</span><span class="sxs-lookup"><span data-stu-id="8731d-104">On the server, the sample demonstrates how to delay the creation of individual <xref:System.ServiceModel.Syndication.SyndicationItem> objects within the feed until immediately before the item is written to the network stream.</span></span>  
  
 <span data-ttu-id="8731d-105">En el cliente, el ejemplo muestra cómo se puede utilizar el formateador de fuente de distribución personalizado para leer los elementos individuales de la secuencia de red para que la fuente que se está leyendo nunca se almacene completamente en el búfer en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8731d-105">On the client, the sample shows how a custom syndication feed formatter can be used to read individual items from the network stream so that the feed being read is never fully buffered into memory.</span></span>  
  
 <span data-ttu-id="8731d-106">Para mostrar mejor la capacidad de transmisión por secuencias de la API de sindicación, este ejemplo utiliza un escenario algo improbable en el que el servidor expone una fuente que contiene un número infinito de elementos.</span><span class="sxs-lookup"><span data-stu-id="8731d-106">To best demonstrate the streaming capability of the syndication API, this sample uses a somewhat unlikely scenario in which the server exposes a feed that contains an infinite number of items.</span></span> <span data-ttu-id="8731d-107">En este caso, el servidor sigue generando los nuevos elementos en la fuente hasta que determine que el cliente ha leído un número especificado de elementos de la fuente (de forma predeterminada, 10).</span><span class="sxs-lookup"><span data-stu-id="8731d-107">In this case, the server continues generating new items into the feed until it determines that the client has read a specified number of items from the feed (by default, 10).</span></span> <span data-ttu-id="8731d-108">Para simplificar, el cliente y el servidor se implementan en el mismo proceso y utilizan un objeto `ItemCounter` compartido para realizar un seguimiento del número de elementos que el cliente ha generado.</span><span class="sxs-lookup"><span data-stu-id="8731d-108">For simplicity, both the client and the server are implemented in the same process and use a shared `ItemCounter` object to keep track of how many items the client has produced.</span></span> <span data-ttu-id="8731d-109">El tipo `ItemCounter` solo existe con el propósito de permitir la finalización del escenario de ejemplo y no es un elemento básico del patrón que se está mostrando.</span><span class="sxs-lookup"><span data-stu-id="8731d-109">The `ItemCounter` type exists only for the purpose of allowing the sample scenario to terminate cleanly, and is not a core element of the pattern being demonstrated.</span></span>  
  
 <span data-ttu-id="8731d-110">La demostración hace uso de Visual C# iteradores (mediante el `yield return` construcción de palabra clave).</span><span class="sxs-lookup"><span data-stu-id="8731d-110">The demonstration makes use of Visual C# iterators (using the `yield return` keyword construct).</span></span> <span data-ttu-id="8731d-111">Para obtener más información acerca de los iteradores, vea el tema "Utilizar iteradores" en MSDN.</span><span class="sxs-lookup"><span data-stu-id="8731d-111">For more information about iterators, see the "Using Iterators" topic on MSDN.</span></span>  
  
## <a name="service"></a><span data-ttu-id="8731d-112">web de Office</span><span class="sxs-lookup"><span data-stu-id="8731d-112">Service</span></span>  
 <span data-ttu-id="8731d-113">El servicio implementa un contrato <xref:System.ServiceModel.Web.WebGetAttribute> básico que está compuesto de una operación, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8731d-113">The service implements a basic <xref:System.ServiceModel.Web.WebGetAttribute> contract that consists of one operation, as shown in the following code.</span></span>  
  
```  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
```  
  
 <span data-ttu-id="8731d-114">El servicio implementa este contrato utilizando una clase `ItemGenerator` para crear una secuencia potencialmente infinita de instancias <xref:System.ServiceModel.Syndication.SyndicationItem> mediante un iterador, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8731d-114">The service implements this contract by using an `ItemGenerator` class to create a potentially infinite stream of <xref:System.ServiceModel.Syndication.SyndicationItem> instances using an iterator, as shown in the following code.</span></span>  
  
```  
class ItemGenerator  
{  
    public IEnumerable<SyndicationItem> GenerateItems()  
    {  
        while (counter.GetCount() < maxItemsRead)  
        {  
            itemsReturned++;  
            yield return CreateNextItem();  
        }  
  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="8731d-115">Cuando la implementación del servicio crea la fuente, se usa el resultado de `ItemGenerator.GenerateItems()` en lugar de una colección almacenada en búfer de elementos.</span><span class="sxs-lookup"><span data-stu-id="8731d-115">When the service implementation creates the feed, the output of `ItemGenerator.GenerateItems()` is used instead of a buffered collection of items.</span></span>  
  
```  
public Atom10FeedFormatter StreamedFeed()  
{  
    SyndicationFeed feed = new SyndicationFeed("Streamed feed", "Feed to test streaming", null);  
    //Generate an infinite stream of items. Both the client and the service share  
    //a reference to the ItemCounter, which allows the sample to terminate  
    //execution after the client has read 10 items from the stream  
    ItemGenerator itemGenerator = new ItemGenerator(this.counter, 10);  
  
    feed.Items = itemGenerator.GenerateItems();  
    return feed.GetAtom10Formatter();  
}  
```  
  
 <span data-ttu-id="8731d-116">Como resultado, la secuencia del elemento nunca se almacena totalmente en búfer en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8731d-116">As a result, the item stream is never fully buffered into memory.</span></span> <span data-ttu-id="8731d-117">Puede observar este comportamiento estableciendo un punto de interrupción en el `yield return` instrucción dentro de la `ItemGenerator.GenerateItems()` método y teniendo en cuenta que este punto de interrupción se encuentra por primera vez después de que el servicio ha devuelto el resultado de la `StreamedFeed()` método.</span><span class="sxs-lookup"><span data-stu-id="8731d-117">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of the `ItemGenerator.GenerateItems()` method and noting that this breakpoint is encountered for the first time after the service has returned the result of the `StreamedFeed()` method.</span></span>  
  
## <a name="client"></a><span data-ttu-id="8731d-118">Cliente</span><span class="sxs-lookup"><span data-stu-id="8731d-118">Client</span></span>  
 <span data-ttu-id="8731d-119">El cliente en este ejemplo utiliza una implementación <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> personalizada que retrasa la materialización de elementos individuales en la fuente en lugar de almacenarlos en búfer en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8731d-119">The client in this sample uses a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> implementation that delays the materialization of individual items in the feed instead of buffering them into memory.</span></span> <span data-ttu-id="8731d-120">La instancia `StreamedAtom10FeedFormatter` personalizada se usa de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="8731d-120">The custom `StreamedAtom10FeedFormatter` instance is used as follows.</span></span>  
  
```  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
```  
  
 <span data-ttu-id="8731d-121">Normalmente, una llamada a <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> no se devuelve hasta que el contenido completo de la fuente se haya leído desde la red y almacenado en búfer en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8731d-121">Normally, a call to <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> does not return until the entire contents of the feed have been read from the network and buffered into memory.</span></span> <span data-ttu-id="8731d-122">Sin embargo, el objeto `StreamedAtom10FeedFormatter` invalida <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> para devolver un iterador en lugar de una colección almacenada en búfer, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8731d-122">However, the `StreamedAtom10FeedFormatter` object overrides <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> to return an iterator instead of a buffered collection, as shown in the following code.</span></span>  
  
```  
protected override IEnumerable<SyndicationItem> ReadItems(XmlReader reader, SyndicationFeed feed, out bool areAllItemsRead)  
{  
    areAllItemsRead = false;  
    return DelayReadItems(reader, feed);  
}  
  
private IEnumerable<SyndicationItem> DelayReadItems(XmlReader reader, SyndicationFeed feed)  
{  
    while (reader.IsStartElement("entry", "http://www.w3.org/2005/Atom"))  
    {  
        yield return this.ReadItem(reader, feed);  
    }  
  
    reader.ReadEndElement();  
}  
```  
  
 <span data-ttu-id="8731d-123">Como resultado, no se lee cada elemento desde la red hasta que la aplicación cliente que atraviesa los resultados de `ReadItems()` esté lista para utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="8731d-123">As a result, each item is not read from the network until the client application traversing the results of `ReadItems()` is ready to use it.</span></span> <span data-ttu-id="8731d-124">Puede observar este comportamiento estableciendo un punto de interrupción en el `yield return` instrucción dentro de `StreamedAtom10FeedFormatter.DelayReadItems()` y teniendo en cuenta que este punto de interrupción se encuentra por primera vez después de llamar a `ReadFrom()` se complete.</span><span class="sxs-lookup"><span data-stu-id="8731d-124">You can observe this behavior by setting a breakpoint on the `yield return` statement inside of `StreamedAtom10FeedFormatter.DelayReadItems()` and noticing that this breakpoint is encountered for the first time after the call to `ReadFrom()` completes.</span></span>  
  
 <span data-ttu-id="8731d-125">Las instrucciones siguientes muestran cómo compilar y ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8731d-125">The following instructions show how to build and run the sample.</span></span> <span data-ttu-id="8731d-126">Tenga en cuenta que aunque el servidor deja de generar los elementos después de que el cliente haya leído diez elementos, la salida muestra que el cliente lee significativamente más de diez elementos.</span><span class="sxs-lookup"><span data-stu-id="8731d-126">Note that although the server stops generating items after the client has read 10 items, the output shows that the client reads significantly more than 10 items.</span></span> <span data-ttu-id="8731d-127">Esto es porque el enlace de conexión en red utilizado por el ejemplo transmite los datos en segmentos de cuatro kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="8731d-127">This is because the networking binding used by the sample transmits data in four-kilobyte (KB) segments.</span></span> <span data-ttu-id="8731d-128">Como tal, el cliente recibe 4 KB de datos de elemento antes de tener la oportunidad incluso de leer un elemento.</span><span class="sxs-lookup"><span data-stu-id="8731d-128">As such, the client receives 4KB of item data before it has the opportunity to read even one item.</span></span> <span data-ttu-id="8731d-129">Se trata del comportamiento normal (el envío de datos de secuencia de HTTP en segmentos de tamaño razonable aumenta el rendimiento).</span><span class="sxs-lookup"><span data-stu-id="8731d-129">This is normal behavior (sending streamed HTTP data in reasonably-sized segments increases performance).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8731d-130">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8731d-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8731d-131">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8731d-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8731d-132">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8731d-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8731d-133">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8731d-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8731d-134">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8731d-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8731d-135">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8731d-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8731d-136">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8731d-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8731d-137">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8731d-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## <a name="see-also"></a><span data-ttu-id="8731d-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8731d-138">See Also</span></span>  
 [<span data-ttu-id="8731d-139">Fuente de diagnósticos independientes</span><span class="sxs-lookup"><span data-stu-id="8731d-139">Stand-Alone Diagnostics Feed</span></span>](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)
