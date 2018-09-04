---
title: CustomDiscoveryMetadata
ms.date: 03/30/2017
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
ms.openlocfilehash: 181910db3f1dd6da892f6ae2ddcbf7bd5859ff17
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525426"
---
# <a name="customdiscoverymetadata"></a>CustomDiscoveryMetadata
Este ejemplo muestra cómo insertar metadatos XML personalizados en los metadatos de detección para un punto de conexión detectable expuesto por un servicio. A continuación, el ejemplo muestra el modo en que un cliente puede buscar el servicio y extraer estos datos personalizados. Este ejemplo está compuesto de dos proyectos: servicio y cliente.  
  
## <a name="service"></a>Servicio  
 En el método `main`, el ejemplo muestra que un objeto de tipo <xref:System.Xml.Linq.XElement> se rellena con los campos deseados y se agrega a <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>. Este <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> se agrega a un extremo determinado. Cuando se detecta ese extremo en particular, los metadatos de detección contienen los datos personalizados que se agregaron aquí.  
  
## <a name="client"></a>Cliente  
 En el ejemplo se muestra el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> que se llama en un objeto <xref:System.ServiceModel.Discovery.DiscoveryClient>. A continuación, se consultan los elementos XML adecuados y los esperados en el objeto <xref:System.ServiceModel.Discovery.FindResponse> resultante. A continuación, estos elementos se imprimen en la consola.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] y compile el proyecto.  
  
2.  En primer lugar, ejecute la aplicación Servicio, generada en [directorio base de la solución]\service\bin\debug y, a continuación, ejecuta la aplicación Cliente, generada en [directorio base de la solución]\Client\bin\debug  
  
3.  Observe que el servicio está en línea, el cliente busca el servicio e imprime los metadatos publicados en el extremo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a>Vea también
