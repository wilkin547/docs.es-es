---
title: "Uso de la configuraci&#243;n para agregar un extremo AJAX de ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Uso de la configuraci&#243;n para agregar un extremo AJAX de ASP.NET
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] le permite crear un servicio que expone un extremo de ASP.NET con AJAX habilitado al que se puede llamar desde JavaScript de un sitio web del cliente.Para crear este tipo de extremo, puede usar un archivo de configuración, como con el resto de extremos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], o utilizar un método que no requiera ningún elemento de configuración.En este tema se muestra el enfoque de configuración.  
  
 La parte del procedimiento que permite al extremo de servicio convertirse en un extremo de ASP.NET con AJAX habilitado consiste en configurar el extremo para que utilice el <xref:System.ServiceModel.WebHttpBinding> y agregue el comportamiento de extremo [\<enableWebScript\>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md).Después de configurar el extremo, los pasos para implementar y hospedar el servicio son similares a aquellos utilizados por cualquier servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Para ver un ejemplo ilustrativo, consulte [Servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] configuración de un extremo de AJAX de ASP.NET sin utilizar la configuración, vea [Cómo agregar un extremo AJAX de ASP.NET sin usar la configuración](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).  
  
### Para crear un servicio WCF básico  
  
1.  Defina un contrato de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] básico con una interfaz marcada con el atributo <xref:System.ServiceModel.ServiceContractAttribute>.Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>.Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
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
  
3.  Defina un espacio de nombres para las implementaciones de `CalculatorService` e `ICalculator` ajustándolas en un bloque de espacios de nombres.  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### Creación de un extremo de AJAX de ASP.NET para el servicio.  
  
1.  Cree una configuración de comportamiento y especifique el comportamiento [\<enableWebScript\>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) para los extremos del servicio ASP.NET con AJAX habilitado.  
  
    ```  
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
  
    ```  
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
  
### Hospedaje del servicio en IIS  
  
1.  Para hospedar el servicio en IIS, cree un nuevo archivo denominado service con extensión .svc en la aplicación.Modifique este archivo agregando la información de directiva [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) apropiada para el servicio.Por ejemplo, el contenido del archivo de servicio para el ejemplo de `CalculatorService` contiene la siguiente información:  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] hospedaje en IIS, vea [Procedimiento para hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### Realización de llamadas al servicio  
  
1.  El extremo se configura en una dirección vacía relativa al archivo .svc, por lo que el servicio ahora está disponible y se puede invoca enviando solicitudes a service.svc\/\<operation\>; por ejemplo, service.svc\/Add para la operación `Add`.Puede utilizarlo introduciendo la URL del extremo en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET.Para obtener un ejemplo, vea [Servicio AJAX mediante HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## Vea también  
 [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)   
 [Cómo migrar servicios web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)