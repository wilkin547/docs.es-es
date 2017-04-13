---
title: "Filtros avanzados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Filtros avanzados
En este ejemplo se muestra un servicio de enrutamiento de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].El servicio de enrutamiento es un componente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permite incluir fácilmente un enrutador basado en contenido en una aplicación.En este ejemplo se adapta el ejemplo de la calculadora de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estándar para comunicarse utilizando el servicio de enrutamiento.En este ejemplo se muestra cómo definir la lógica de enrutamiento basado en contenido a través del uso de filtros de mensajes y tablas de filtro de mensajes.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## Detalles del ejemplo  
 En la siguiente tabla se muestran los filtros de mensajes que se agregan a la tabla de filtros de mensajes del servicio de enrutamiento.  
  
|Filtro|Regla|Prioridad|  
|------------|-----------|---------------|  
|Si \(tiene encabezado\)|Redondeo|2|  
|Si \(se muestra en Ep2\)|Regular|1|  
|Si \(se muestra con Address2\)|Redondeo|1|  
|Si \(RoundRobin1\)|Regular|0|  
|If \(RoundRobin2\)|Redondeo|0|  
  
 Los filtros de mensajes y las tablas de filtros de mensajes se pueden crear y configurar o bien a través del código o bien en el archivo de configuración de la aplicación.En este ejemplo, puede encontrar los filtros de mensajes y las tablas de filtros de mensajes definidos a través del código en el archivo RoutingService\\routing.cs o definidos en el archivo de configuración de la aplicación del archivo RoutingService\\App.config.Los siguientes párrafos describen el modo en que se crean los filtros de mensajes y las tablas de filtros de mensajes para obtener este ejemplo a través del código.  
  
 Primero, un objeto <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> busca el encabezado personalizado.Tenga en cuenta que el objeto <xref:System.ServiceModel.WSHttpBinding> da como resultado una versión de sobre que usa SOAP 1.2, de modo que la instrucción Xpath se defina para utilizar el espacio de nombres SOAP 1.2.El administrador del espacio de nombres predeterminado para <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> ya define un prefijo para el espacio de nombres SOAP 1.2, \/s12, que se puede utilizar.Sin embargo, el administrador del espacio de nombres predeterminado no tiene el espacio de nombres personalizado que el cliente utiliza para definir el valor de encabezado real, de modo que se debe definir el prefijo.Cualquier mensaje que se presente con este encabezado coincide con este filtro.  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
  
```  
  
 El segundo filtro es un <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>, que coincide con cualquier mensaje que se recibiera en `calculatorEndpoint`.El nombre de extremo se define cuando se crea un objeto de extremo de servicio.  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
  
```  
  
 El tercer filtro es un <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>.Esto coincide con cualquier mensaje que se presentara en un extremo con una dirección que coincida con el prefijo de dirección \(o la parte delantera\) proporcionado.En este ejemplo el prefijo de dirección se define como "http:\/\/localhost\/routingservice\/router\/rounding\/".Esto significa que este filtro coincide con cualquier mensaje entrante que se dirija a "http:\/\/localhost\/routingservice\/router\/rounding\/\*".En este caso, es un mensaje que se presenta en el extremo de la calculadora de redondeo, que tiene la dirección "http:\/\/localhost\/routingservice\/router\/rounding\/calculator".  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
  
```  
  
 Los dos filtros de mensajes últimos son <xref:System.ServiceModel.Dispatcher.MessageFilter> personalizados.En este ejemplo, se usa un filtro de mensajes “RoundRobin”.Este filtro de mensajes se crea en el archivo RoutingService\\RoundRobinMessageFilter.cs proporcionado.Estos filtros, cuando se establecen en el mismo grupo, alternan entre notificar que coinciden con el mensaje y que no lo hacen, de modo que solo uno de ellos responde `true` a la vez.  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
  
```  
  
 Luego, todos esos mensajes se agregan a un <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>.Para ello, se especifican prioridades para influir en el orden en el que la tabla de filtros de mensajes ejecuta los filtros.Cuanta más alta es la prioridad, antes se ejecuta el filtro; cuanto menor es la prioridad, más tarde se ejecuta un filtro.Por tanto, un filtro de prioridad 2 se ejecuta antes que uno de prioridad 1.El nivel de prioridad predeterminado es 0 si no se especifica ninguno.En una tabla de filtros de mensajes se ejecutan todos los filtros en un nivel de prioridad determinado antes de pasar al nivel de prioridad inferior siguiente.Si se encuentra una coincidencia en una prioridad determinada, la tabla de filtros de mensajes no sigue intentando encontrar coincidencias en la prioridad inferior siguiente.  
  
> [!NOTE]
>  Aunque este ejemplo muestra cómo utilizar las prioridades del filtro de mensajes, en general es más adecuado diseñar y configurar los filtros de modo que no requieran la asignación de prioridades para funcionar correctamente.  
  
 El primer filtro que se va a agregar es el filtro de XPath y su prioridad se establece en 2.Este es el primer filtro de mensajes que se ejecuta.Si encuentra el encabezado personalizado, independientemente de cuáles serían los resultados de los demás filtros, el mensaje se enruta al extremo de la calculadora de redondeo.  
  
 En la prioridad 1, se agregan dos filtros.De nuevo, solo se ejecutan si el filtro de XPath en la prioridad 2 no coincide con el mensaje.Estos dos filtros muestran dos maneras diferentes de determinar dónde se dirigió el mensaje cuando se presentó.Dado que los dos filtran comprueban eficazmente si el mensaje llegó a uno de los dos extremos, se pueden ejecutar en el mismo nivel de prioridad porque ambos no devuelven `true` al mismo tiempo.  
  
 Finalmente, en la prioridad 0 \(la más baja\) se ejecutan los filtros de mensajes RoundRobin.Dado que los filtros se configuran con el mismo nombre de grupo, solo uno de ellos coincide a la vez.Dado que se han enrutado todos los mensajes con el encabezado personalizado y todos los dirigidos a extremos virtualizados concretos, solo los mensajes administrados por los filtros de mensajes RoundRobin son los que se dirigieron al extremo del enrutador predeterminado sin el encabezado personalizado.Dado que estos mensajes activan un mensaje para cada llamada, la mitad de las operaciones va al extremo de calculadora normal y la otra mitad va al extremo de calculadora de redondeo.  
  
#### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra AdvancedFilters.sln.  
  
2.  Para abrir el **Explorador de soluciones**, seleccione **Explorador de soluciones** en el menú **Ver**.  
  
3.  Presione F5 o CTRL\+MAYÚS\+B en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
    1.  Si desea iniciar de forma automática los proyectos necesarios al presionar F5, haga clic con el botón secundario en la solución y seleccione **Propiedades**.Seleccione el nodo **Proyecto de inicio** en **Propiedades comunes**, en el panel izquierdo.Seleccione el botón de radio **Proyectos de inicio múltiples** y establezca todos los proyectos para que tengan la acción **Iniciar**.  
  
    2.  Si compila el proyecto con CTRL\+MAYÚS\+B, debe iniciar las siguientes aplicaciones:  
  
        1.  El cliente de la calculadora \(.\/CalculatorClient\/bin\/client.exe\)  
  
        2.  El servicio de calculadora \(.\/CalculatorService\/bin\/service.exe\)  
  
        3.  El servicio de enrutamiento de calculadora \(.\/RoundingCalcService\/bin\/service.exe\)  
  
        4.  RoutingService \(.\/RoutingService\/bin\/RoutingService.exe\)  
  
4.  En la ventana de la consola del cliente de la calculadora, presione ENTRAR para iniciar el cliente.El cliente devuelve una lista de los extremos de destino entre los que elegir.  
  
5.  Elija un extremo de destino escribiendo su letra correspondiente y presione ENTRAR.  
  
6.  Después, el cliente le pregunta si desea agregar un encabezado personalizado.Presione S para indicar Sí o N para indicar No; a continuación, presione ENTRAR.  
  
7.  En función de las selecciones que realizó, debería ver resultados diferentes.  
  
    1.  Lo siguiente es el resultado que se devuelve si agregó un encabezado personalizado a los mensajes.  
  
        ```Output  
        Sumar (100,15.99) = 116  
        Restar (145,76.54) = 68.5  
        Multiplicar (9,81.25) = 731.3  
        Dividir (22,7) = 3.1  
  
        ```  
  
    2.  Lo siguiente es el resultado que se devuelve si eligió el extremo de calculadora de redondeo sin un encabezado personalizado.  
  
        ```Output  
        Sumar (100,15.99) = 116  
        Restar (145,76.54) = 68.5  
        Multiplicar (9,81.25) = 731.3  
        Dividir (22,7) = 3.1  
  
        ```  
  
    3.  Lo siguiente es el resultado que se devuelve si eligió el extremo de calculadora normal sin un encabezado personalizado.  
  
        ```Output  
        Sumar(100;15,99) = 115,99  
        Restar(145;76,54) = 68.46  
        Multiplicar(9;81,25) = 731,25  
        Dividir(22;7) = 3,14285714285714  
  
        ```  
  
    4.  Lo siguiente es el resultado que se devuelve si eligió el extremo de enrutador predeterminado sin un encabezado personalizado.  
  
        ```Output  
        Sumar (100,15.99) = 116  
        Restar(145;76,54) = 68,46  
        Multiplicar (9,81.25) = 731.3  
        Dividir(22;7) = 3,14285714285714  
  
        ```  
  
8.  El servicio de calculadora y el servicio de calculadora de redondeo también imprime un registro de las operaciones invocadas en sus respectivas ventanas de consola.  
  
9. En la ventana de la consola del cliente, escriba `quit` y presione ENTRAR para salir.  
  
10. Presione ENTRAR en las ventanas de la consola de servicios para terminar los servicios.  
  
## Configurable a través de código o App.onfig  
 El ejemplo viene configurado para utilizar un archivo App.config que define el comportamiento del enrutador.También puede cambiar el nombre del archivo RoutingService\\App.config por otro que no se reconozca y quitar el comentario de la llamada al método `ConfigureRouterViaCode()` en RoutingService\\routing.cs.Cualquier método provoca el mismo comportamiento del enrutador.  
  
### Escenario  
 En este ejemplo se muestra el enrutador que actúa como enrutador basado en contenido que permite exponer varios tipos o la implementación de los servicios a través de un extremo.  
  
### Escenario real  
 Contoso desea virtualizar todos sus servicios para exponer solo un extremo a través del que ofrecer acceso a varios tipos diferentes de servicios públicamente.En este caso, utilizan las capacidades de enrutamiento basado en contenido del servicio de enrutamiento para determinar dónde se deberían enviar las solicitudes entrantes.  
  
## Vea también  
 [Ejemplos de hospedaje y persistencia de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)