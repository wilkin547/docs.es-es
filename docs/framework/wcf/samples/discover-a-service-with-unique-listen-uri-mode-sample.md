---
title: Ejemplo de detección de un servicio con un modo de URI de escucha único
ms.date: 03/30/2017
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
ms.openlocfilehash: 7e1c5ae0cb1a44c72a27566035b4bc20acbf1614
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703601"
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a>Ejemplo de detección de un servicio con un modo de URI de escucha único
En este ejemplo se muestra cómo detectar un servicio que tiene la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> establecida en <xref:System.ServiceModel.Description.ListenUriMode.Unique>. Cuando la propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> está establecida en <xref:System.ServiceModel.Description.ListenUriMode.Unique>, se asegura de que ListenUri es único estableciendo el puerto para que sea único o para que la ruta de acceso sea único anexando un GUID.  
  
### <a name="features-on-the-service"></a>Características en el servicio  
 La propiedad <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> se establece en <xref:System.ServiceModel.Description.ListenUriMode.Unique> para el extremo TCP. A continuación, el servicio se puede detectar a través de un extremo de <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.  
  
### <a name="features-on-the-client"></a>Características en el cliente  
 Este cliente se conecta al servicio utilizando el `Via.Uri` correcto con el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>. A continuación, el objeto <xref:System.ServiceModel.Discovery.FindResponse> que devuelve el método se consulta para comprobar si contiene una propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> válida y si es diferente de `Address.Uri`. A continuación, la información adecuada se pasa al método `InvokeCalculatorService`. En el método `InvokeCalculatorService`, el llamador pasa la propiedad <xref:System.ServiceModel.Endpoint.ListenUri%2A> y un `ClientViaBehavior` con el `Via.Uri` correcto se agrega al extremo del cliente.  
  
##### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra UniqueListenUriMode.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Ejecute la aplicación de servicio, que se genera en la carpeta [directorio base de la solución]\service\bin\debug.  
  
4.  Ejecute la aplicación cliente, que se genera en la carpeta [directorio base de la solución]\Client\bin\debug.  
  
     El cliente busca el servicio en ejecución y escribe en la consola los metadatos publicados por el extremo del servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a>Vea también
