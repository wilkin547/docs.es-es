---
title: Uso de la configuración para agregar un extremo AJAX de ASP.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28051dbed626dc0073a38e72f2cdc21ea108a32e
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Uso de la configuración para agregar un punto de conexión AJAX de ASP.NET
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] le permite crear un servicio que expone un extremo de ASP.NET con AJAX habilitado al que se puede llamar desde JavaScript de un sitio web del cliente. Para crear este tipo de extremo, puede usar un archivo de configuración, como con el resto de extremos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], o utilizar un método que no requiera ningún elemento de configuración. En este tema se muestra el enfoque de configuración.  
  
 La parte del procedimiento que permite al extremo de servicio esté habilitado para AJAX de ASP.NET consiste en configurar el punto de conexión para usar el <xref:System.ServiceModel.WebHttpBinding> y agregar el [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento de extremo. Después de configurar el extremo, los pasos para implementar y hospedar el servicio son similares a aquellos utilizados por cualquier servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Para obtener un ejemplo, vea el [servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Para obtener más información sobre cómo configurar un punto de conexión de AJAX de ASP.NET sin usar la configuración, consulte [Cómo: agregar un punto de conexión sin configuración uso de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Para crear un servicio WCF básico  
  
1.  Defina un contrato de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básico con una interfaz marcada con el atributo <xref:System.ServiceModel.ServiceContractAttribute>. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```  
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a>Creación de un punto de conexión de AJAX de ASP.NET para el servicio.  
  
1.  Crear una configuración de comportamiento y especificar el [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento de ASP.NET con AJAX habilitado extremos del servicio.  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2.  Cree un extremo para el servicio que utilice el <xref:System.ServiceModel.WebHttpBinding> y el comportamiento de AJAX de ASP.NET definido en el paso anterior.  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"   
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>   
    ```  
  
### <a name="to-host-the-service-in-iis"></a>Hospedaje del servicio en IIS  
  
1.  Para hospedar el servicio en IIS, cree un nuevo archivo denominado service con extensión .svc en la aplicación. Editar este archivo agregando adecuado [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) información de directiva para el servicio. Por ejemplo, el contenido del archivo de servicio para el ejemplo de `CalculatorService` contiene la siguiente información:  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  Para obtener más información sobre el hospedaje en IIS, consulte [Cómo: hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1.  El extremo se configura en una dirección vacía relativa al archivo .svc, por lo que el servicio ahora está disponible y se puede invocar enviando solicitudes a Service.svc /\<operación >: por ejemplo, Service.svc/Add para la `Add` operación. Puede utilizarlo introduciendo la URL del punto de conexión en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, vea el [servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>Vea también  
 [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Migración de servicios web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
