---
title: Ejemplo de proxy de detección
ms.date: 03/30/2017
ms.assetid: 1dfa02df-15b1-4e97-9c8e-f5f2772711b0
ms.openlocfilehash: 6fc0680bc6b61a6fe1b4b141c8b1e5081df5a124
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180402"
---
# <a name="discovery-proxy-sample"></a>Ejemplo de proxy de detección
En este ejemplo se muestra cómo crear una implementación de un proxy de detección para almacenar información acerca de los servicios existentes y el modo en que los clientes pueden consultar información en ese proxy. Este ejemplo consta de tres proyectos:  
  
-   **Servicio**: un simple servicio de calculadora de Windows Communication Foundation (WCF) que se registra con el proxy de detección.  
  
-   **Proxy de detección**: la implementación de un servicio de proxy de detección.  
  
-   **Cliente**: aplicación de cliente de WCF que requiere el proxy de detección para buscar servicios.  
  
## <a name="demonstrates"></a>Demostraciones  
 Implementación de un proxy de detección  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryProxy`  
  
## <a name="discoveryproxy"></a>DiscoveryProxy  
 En el método `Main` del archivo Program.cs, el ejemplo muestra cómo se hospeda un servicio de tipo <xref:System.ServiceModel.Discovery.DiscoveryProxy>. Expone dos extremos, uno de tipo <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> y otro de tipo <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>. Ambos utilizan TCP como transporte. <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> está realizando escuchas en el URI especificado por el parámetro `probeEndpointAddress`, que es donde los clientes pueden enviar mensajes de sondeo que consulten sus datos en el proxy. <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> está realizando escuchas en el URI especificado por el parámetro `announcementEndpointAddress`. Se trata del lugar donde el proxy escucha los anuncios. Cuando se recibe un anuncio en línea, el proxy agrega el servicio a su memoria caché y, cuando se recibe un anuncio sin conexión, quita el servicio de su memoria caché.  
  
 DiscoveryProxy.cs contiene la implementación de <xref:System.ServiceModel.Discovery.DiscoveryProxy>. El proxy debe heredar de la clase <xref:System.Object> y requiere una implementación de <xref:System.Runtime.Remoting.Messaging.AsyncResult>. En la creación de instancias, el proxy crea un nuevo <xref:System.Collections.Generic.Dictionary%602>, que utiliza para almacenar los elementos que conoce.  
  
 El archivo está dividido en dos regiones, Métodos de caché de proxy e Implementación de proxy de detección. La región Métodos de caché de proxy contiene los métodos utilizados para actualizar <xref:System.Collections.Generic.Dictionary%602>, realizar consultas a <xref:System.Collections.Generic.Dictionary%602> e imprimir datos de los usuarios. La región Implementación de proxy de detección contiene los métodos invalidados requeridos para la funcionalidad de Anuncio y sondeo. Definen las acciones realizadas por un proxy tras recibir un anuncio en línea, un anuncio sin conexión o un mensaje de sondeo.  
  
## <a name="service"></a>web de Office  
 En el archivo Program.cs en el proyecto de servicio, se utiliza el mismo URI para su punto de conexión de anuncio y para el proxy de detección. Esto se debe a que el servicio utiliza el extremo para enviar los anuncios, mientras que el proxy lo utiliza para recibirlos. El servicio utiliza el <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> y le agrega un extremo de anuncio.  
  
## <a name="client"></a>Cliente  
 El proyecto Cliente utiliza el mismo URI para su punto de conexión de sondeo que el proxy. Esto se debe a que los sondeos en este escenario también se difunden específicamente al extremo disponible en el proxy. El cliente se conecta a esta dirección conocida y, a continuación, consulta el servicio. Una vez ha encontrado el servicio, se conecta a él.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] y compile el proyecto.  
  
2.  Primero, ejecute la aplicación de proxy de detección, generada en [directorio base de la solución]\DiscoveryProxy\bin\debug. El proxy de detección se debe ejecutar primero porque los puntos de conexión de anuncio de TCP deben estar activos para que el servicio envíe sus anuncios.  
  
3.  En segundo lugar, ejecute la aplicación de servicio generada en [directorio base de la solución] \Service\bin\debug. Al iniciarse, el servicio envía un anuncio al extremo de anuncio del proxy de detección y se registra en la memoria caché del proxy.  
  
4.  Después, ejecute la aplicación cliente, generada en [directorio base de la solución]\Client\bin\debug. El cliente consulta el proxy, obtiene la dirección de servicio y, a continuación, se conecta al servicio.  
  
5.  Por último, termine el cliente, el servicio y, a continuación, el proxy. El proxy se debe estar ejecutando para que reciba el anuncio sin conexión del servicio.  
  
## <a name="see-also"></a>Vea también
