---
title: Filtros avanzados
ms.date: 03/30/2017
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
ms.openlocfilehash: de8577be2d56ec3c942fd8736e350234daf6a35a
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="advanced-filters"></a>Filtros avanzados
Este ejemplo muestra un servicio de enrutamiento de Windows Communication Foundation (WCF). El servicio de enrutamiento es un componente WCF que facilita el proceso incluir un enrutador basado en contenido en la aplicación. Este ejemplo adapta el ejemplo de la calculadora de WCF estándar para comunicarse con el servicio de enrutamiento. En este ejemplo se muestra cómo definir la lógica de enrutamiento basado en contenido a través del uso de filtros de mensajes y tablas de filtro de mensajes.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 En la siguiente tabla se muestran los filtros de mensajes que se agregan a la tabla de filtros de mensajes del servicio de enrutamiento.  
  
|Filtro|Regla|Prioridad|  
|------------|----------|--------------|  
|Si (tiene encabezado)|Redondeo|2|  
|Si (se muestra en Ep2)|Estándar|1|  
|Si (se muestra con Address2)|Redondeo|1|  
|Si (RoundRobin1)|Estándar|0|  
|If (RoundRobin2)|Redondeo|0|  
  
 Los filtros de mensajes y las tablas de filtros de mensajes se pueden crear y configurar o bien a través del código o bien en el archivo de configuración de la aplicación. En este ejemplo, puede encontrar los filtros de mensajes y las tablas de filtros de mensajes definidos a través del código en el archivo RoutingService\routing.cs o definidos en el archivo de configuración de la aplicación del archivo RoutingService\App.config. Los siguientes párrafos describen el modo en que se crean los filtros de mensajes y las tablas de filtros de mensajes para obtener este ejemplo a través del código.  
  
 Primero, un objeto <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> busca el encabezado personalizado. Tenga en cuenta que el objeto <xref:System.ServiceModel.WSHttpBinding> da como resultado una versión de sobre que usa SOAP 1.2, de modo que la instrucción Xpath se defina para utilizar el espacio de nombres SOAP 1.2. El administrador del espacio de nombres predeterminado para <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> ya define un prefijo para el espacio de nombres SOAP 1.2, /s12, que se puede utilizar. Sin embargo, el administrador del espacio de nombres predeterminado no tiene el espacio de nombres personalizado que el cliente utiliza para definir el valor de encabezado real, de modo que se debe definir el prefijo. Cualquier mensaje que se presente con este encabezado coincide con este filtro.  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
```  
  
 El segundo filtro es un <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, que coincide con cualquier mensaje que se recibiera en `calculatorEndpoint`. El nombre de punto de conexión se define cuando se crea un objeto de punto de conexión de servicio.  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
```  
  
 El tercer filtro es un <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>. Esto coincide con cualquier mensaje que se presentara en un punto de conexión con una dirección que coincida con el prefijo de dirección (o la parte delantera) proporcionado. En este ejemplo se define el prefijo de dirección como "http://localhost/routingservice/router/rounding/". Esto significa que los mensajes entrantes que se dirigen al "http://localhost/routingservice/router/rounding/*" coincide con este filtro. En este caso, es un mensaje que se muestran en el extremo de calculadora de redondeo, que tiene la dirección "http://localhost/routingservice/router/rounding/calculator".  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
```  
  
 Los dos filtros de mensajes últimos son <xref:System.ServiceModel.Dispatcher.MessageFilter> personalizados. En este ejemplo, se usa un filtro de mensajes “RoundRobin”. Este filtro de mensajes se crea en el archivo RoutingService\RoundRobinMessageFilter.cs proporcionado. Estos filtros, cuando se establecen en el mismo grupo, alternan entre notificar que coinciden con el mensaje y que no lo hacen, de modo que solo uno de ellos responde `true` a la vez.  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
```  
  
 Luego, todos esos mensajes se agregan a un <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>. Para ello, se especifican prioridades para influir en el orden en el que la tabla de filtros de mensajes ejecuta los filtros. Cuanta más alta es la prioridad, antes se ejecuta el filtro; cuanto menor es la prioridad, más tarde se ejecuta un filtro. Por tanto, un filtro de prioridad 2 se ejecuta antes que uno de prioridad 1. El nivel de prioridad predeterminado es 0 si no se especifica ninguno. En una tabla de filtros de mensajes se ejecutan todos los filtros en un nivel de prioridad determinado antes de pasar al nivel de prioridad inferior siguiente. Si se encuentra una coincidencia en una prioridad determinada, la tabla de filtros de mensajes no sigue intentando encontrar coincidencias en la prioridad inferior siguiente.  
  
> [!NOTE]
>  Aunque este ejemplo muestra cómo utilizar las prioridades del filtro de mensajes, en general es más adecuado diseñar y configurar los filtros de modo que no requieran la asignación de prioridades para funcionar correctamente.  
  
 El primer filtro que se va a agregar es el filtro de XPath y su prioridad se establece en 2. Este es el primer filtro de mensajes que se ejecuta. Si encuentra el encabezado personalizado, independientemente de cuáles serían los resultados de los demás filtros, el mensaje se enruta al punto de conexión de la calculadora de redondeo.  
  
 En la prioridad 1, se agregan dos filtros. De nuevo, solo se ejecutan si el filtro de XPath en la prioridad 2 no coincide con el mensaje. Estos dos filtros muestran dos maneras diferentes de determinar dónde se dirigió el mensaje cuando se presentó. Dado que los dos filtran comprueban eficazmente si el mensaje llegó a uno de los dos extremos, se pueden ejecutar en el mismo nivel de prioridad porque ambos no devuelven `true` al mismo tiempo.  
  
 Finalmente, en la prioridad 0 (la más baja) se ejecutan los filtros de mensajes RoundRobin. Dado que los filtros se configuran con el mismo nombre de grupo, solo uno de ellos coincide a la vez. Dado que se han enrutado todos los mensajes con el encabezado personalizado y todos los dirigidos a extremos virtualizados concretos, solo los mensajes administrados por los filtros de mensajes RoundRobin son los que se dirigieron al extremo del enrutador predeterminado sin el encabezado personalizado. Dado que estos mensajes activan un mensaje para cada llamada, la mitad de las operaciones va al punto de conexión de calculadora normal y la otra mitad va al punto de conexión de calculadora de redondeo.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra AdvancedFilters.sln.  
  
2.  Para abrir **el Explorador de soluciones**, seleccione **el Explorador de soluciones** desde el **vista** menú.  
  
3.  Presione F5 o CTRL + MAYÚS + B en Visual Studio.  
  
    1.  Si desea iniciar de forma automática los proyectos necesarios al presionar F5, haga clic en la solución y seleccione **propiedades**. Seleccione el **proyecto de inicio** nodo bajo **propiedades comunes** en el panel izquierdo. Seleccione el **proyectos de inicio múltiples** botón de radio y establecer todos los proyectos que tienen el **iniciar** acción.  
  
    2.  Si compila el proyecto con CTRL+MAYÚS+B, debe iniciar las siguientes aplicaciones:  
  
        1.  El cliente de la calculadora (./CalculatorClient/bin/client.exe)  
  
        2.  El servicio de calculadora (./CalculatorService/bin/service.exe)  
  
        3.  El servicio de enrutamiento de calculadora (./RoundingCalcService/bin/service.exe)  
  
        4.  RoutingService (./RoutingService/bin/RoutingService.exe)  
  
4.  En la ventana de la consola del cliente de la calculadora, presione ENTRAR para iniciar el cliente. El cliente devuelve una lista de los puntos de conexión de destino entre los que elegir.  
  
5.  Elija un punto de conexión de destino escribiendo su letra correspondiente y presione ENTRAR.  
  
6.  Después, el cliente le pregunta si desea agregar un encabezado personalizado. Presione S para indicar Sí o N para indicar No; a continuación, presione ENTRAR.  
  
7.  En función de las selecciones que realizó, debería ver resultados diferentes.  
  
    1.  Lo siguiente es el resultado que se devuelve si agregó un encabezado personalizado a los mensajes.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    2.  Lo siguiente es el resultado que se devuelve si eligió el punto de conexión de calculadora de redondeo sin un encabezado personalizado.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    3.  Lo siguiente es el resultado que se devuelve si eligió el punto de conexión de calculadora normal sin un encabezado personalizado.  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68. 46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
    4.  Lo siguiente es el resultado que se devuelve si eligió el punto de conexión de enrutador predeterminado sin un encabezado personalizado.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.14285714285714  
        ```  
  
8.  El servicio de calculadora y el servicio de calculadora de redondeo también imprime un registro de las operaciones invocadas en sus respectivas ventanas de consola.  
  
9. En la ventana de la consola de cliente, escriba `quit` y presione ENTRAR para salir.  
  
10. Presione ENTRAR en las ventanas de la consola de servicios para terminar los servicios.  
  
## <a name="configurable-via-code-or-appconfig"></a>Configurable a través de código o App.onfig  
 El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador. También puede cambiar el nombre del archivo RoutingService\App.config por otro que no se reconozca y quitar el comentario de la llamada al método `ConfigureRouterViaCode()` en RoutingService\routing.cs. Cualquier método provoca el mismo comportamiento del enrutador.  
  
### <a name="scenario"></a>Escenario  
 En este ejemplo se muestra el enrutador que actúa como enrutador basado en contenido que permite exponer varios tipos o la implementación de los servicios a través de un extremo.  
  
### <a name="real-world-scenario"></a>Escenario real  
 Contoso desea virtualizar todos sus servicios para exponer solo un extremo a través del que ofrecer acceso a varios tipos diferentes de servicios públicamente. En este caso, utilizan las capacidades de enrutamiento basado en contenido del servicio de enrutamiento para determinar dónde se deberían enviar las solicitudes entrantes.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
