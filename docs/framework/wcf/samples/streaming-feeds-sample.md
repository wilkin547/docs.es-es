---
title: "Ejemplo de suministros de transmisi&#243;n por secuencias | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f1228c0-daaa-45f0-b93e-c4a158113744
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Ejemplo de suministros de transmisi&#243;n por secuencias
Este ejemplo muestra cómo administrar las fuentes de sindicación que contienen grandes cantidades de elementos.En el servidor, el ejemplo muestra cómo retrasar la creación de objetos <xref:System.ServiceModel.Syndication.SyndicationItem> individuales dentro de la fuente hasta justo antes de que el elemento se escriba en el flujo de red.  
  
 En el cliente, el ejemplo muestra cómo se puede utilizar el formateador de fuente de distribución personalizado para leer los elementos individuales del flujo de red para que la fuente que se está leyendo nunca se almacene completamente en el búfer en la memoria.  
  
 Para mostrar mejor la capacidad de transmisión por secuencias de la API de sindicación, este ejemplo utiliza un escenario algo improbable en el que el servidor expone una fuente que contiene un número infinito de elementos.En este caso, el servidor sigue generando los nuevos elementos en la fuente hasta que determine que el cliente ha leído un número especificado de elementos de la fuente \(de forma predeterminada, 10\).Para simplificar, el cliente y el servidor se implementan en el mismo proceso y utilizan un objeto `ItemCounter` compartido para realizar un seguimiento del número de elementos que el cliente ha generado.El tipo `ItemCounter` solo existe con el propósito de permitir la finalización del escenario de ejemplo y no es un elemento básico del modelo que se está mostrando.  
  
 La demostración usa iteradores de [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] \(mediante la construcción de la palabra clave de `yield``return`\).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los iteradores, vea el tema "Utilizar iteradores” en MSDN.  
  
## Servicio  
 El servicio implementa un contrato <xref:System.ServiceModel.Web.WebGetAttribute> básico que está compuesto de una operación, tal y como se muestra en el código siguiente.  
  
```  
[ServiceContract]  
interface IStreamingFeedService  
{  
    [WebGet]  
    [OperationContract]  
    Atom10FeedFormatter StreamedFeed();  
}  
  
```  
  
 El servicio implementa este contrato utilizando una clase `ItemGenerator` para crear una secuencia potencialmente infinita de instancias <xref:System.ServiceModel.Syndication.SyndicationItem> mediante un iterador, tal y como se muestra en el código siguiente.  
  
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
  
 Cuando la implementación del servicio crea la fuente, se usa el resultado de `ItemGenerator.GenerateItems()` en lugar de una colección almacenada en búfer de elementos.  
  
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
  
 Como resultado, la secuencia del elemento nunca se almacena totalmente en búfer en la memoria.Puede observar este comportamiento estableciendo un punto de interrupción en la instrucción `yield``return` dentro del método `ItemGenerator.GenerateItems()` y teniendo en cuenta que este punto de interrupción se encuentra por primera vez después de que el servicio haya devuelto el resultado del método `StreamedFeed()`.  
  
## Cliente  
 El cliente en este ejemplo utiliza una implementación <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> personalizada que retrasa la materialización de elementos individuales en la fuente en lugar de almacenarlos en búfer en la memoria.La instancia `StreamedAtom10FeedFormatter` personalizada se usa de la manera siguiente.  
  
```  
XmlReader reader = XmlReader.Create("http://localhost:8000/Service/Feeds/StreamedFeed");  
StreamedAtom10FeedFormatter formatter = new StreamedAtom10FeedFormatter(counter);  
  
SyndicationFeed feed = formatter.ReadFrom(reader);  
  
```  
  
 Normalmente, una llamada a <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter.ReadFrom%28System.Xml.XmlReader%29> no se devuelve hasta que el contenido completo de la fuente se haya leído desde la red y almacenado en búfer en la memoria.Sin embargo, el objeto `StreamedAtom10FeedFormatter` invalida <xref:System.ServiceModel.Syndication.Atom10FeedFormatter.ReadItems%28System.Xml.XmlReader%2CSystem.ServiceModel.Syndication.SyndicationFeed%2CSystem.Boolean%40%29> para devolver un iterador en lugar de una colección almacenada en búfer, tal y como se muestra en el código siguiente.  
  
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
  
 Como resultado, no se lee cada elemento desde la red hasta que la aplicación cliente que atraviesa los resultados de `ReadItems()` esté lista para utilizarlo.Puede observar este comportamiento estableciendo un punto de interrupción en la instrucción `yield``return` dentro de `StreamedAtom10FeedFormatter.DelayReadItems()` y teniendo en cuenta que este punto de interrupción aparece por primera vez después de que la llamada a `ReadFrom()` se complete.  
  
 Las instrucciones siguientes muestran cómo compilar y ejecutar el ejemplo.Tenga en cuenta que aunque el servidor deja de generar los elementos después de que el cliente haya leído diez elementos, la salida muestra que el cliente lee significativamente más de diez elementos.Esto es porque el enlace de conexión en red utilizado por el ejemplo transmite los datos en segmentos de cuatro kilobytes \(KB\).Como tal, el cliente recibe 4 KB de datos de elemento antes de tener la oportunidad incluso de leer un elemento.Se trata del comportamiento normal \(el envío de datos de secuencia de HTTP en segmentos de tamaño razonable aumenta el rendimiento\).  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Extensibility\Syndication\StreamingFeeds`  
  
## Vea también  
 [Fuente de diagnósticos independientes](../../../../docs/framework/wcf/samples/stand-alone-diagnostics-feed-sample.md)