---
title: Procedimiento para usar la configuración para agregar un punto de conexión AJAX de ASP.NET
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 33f99161034db2aa142a422139406a1a68d42b2c
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972279"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a>Procedimiento para usar la configuración para agregar un punto de conexión AJAX de ASP.NET
Windows Communication Foundation (WCF) le permite crear un servicio que hace que un punto de conexión habilitado para ASP.NET AJAX esté disponible al que se puede llamar desde JavaScript en un sitio web del cliente. Para crear este tipo de punto de conexión, puede usar un archivo de configuración, como con todos los demás extremos de Windows Communication Foundation (WCF), o bien usar un método que no requiera ningún elemento de configuración. En este tema se muestra el enfoque de configuración.  
  
 La parte del procedimiento que permite que el punto de conexión de servicio se convierta en ASP.NET AJAX habilitado consiste en configurar <xref:System.ServiceModel.WebHttpBinding> el punto de conexión para que use y agregar el comportamiento del [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) punto de conexión de > de enableWebScript. Después de configurar el punto de conexión, los pasos para implementar y hospedar el servicio son similares a los utilizados por cualquier servicio de WCF. Para obtener un ejemplo práctico, vea el [servicio Ajax mediante http post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 Para obtener más información sobre cómo configurar un punto de conexión de ASP.NET AJAX sin usar [la configuración, vea cómo: Agregue un punto de conexión de AJAX de](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)ASP.net sin usar la configuración.  
  
## <a name="to-create-a-basic-wcf-service"></a>Para crear un servicio WCF básico  
  
1. Defina un contrato de servicio WCF básico con una interfaz marcada con <xref:System.ServiceModel.ServiceContractAttribute> el atributo. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```csharp
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.  
  
    ```csharp
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.  
  
    ```csharp
    namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a>Creación de un punto de conexión de AJAX de ASP.NET para el servicio.  
  
1. Cree una configuración de comportamiento y especifique [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) el comportamiento de > de enableWebScript para los puntos de conexión habilitados para ASP.net Ajax del servicio.  
  
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
  
2. Cree un punto de conexión para el servicio que utilice el <xref:System.ServiceModel.WebHttpBinding> y el comportamiento de AJAX de ASP.NET definido en el paso anterior.  
  
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
  
## <a name="to-host-the-service-in-iis"></a>Hospedaje del servicio en IIS  
  
1. Para hospedar el servicio en IIS, cree un nuevo archivo denominado service con extensión .svc en la aplicación. Edite este archivo agregando la información de directiva de [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio. Por ejemplo, el contenido del archivo de servicio para el ejemplo de `CalculatorService` contiene la siguiente información:  
  
    ```
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. Para obtener más información sobre el hospedaje en IIS [, vea cómo: Hospede un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
## <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1. El punto de conexión se configura en una dirección vacía relativa al archivo. SVC, por lo que el servicio ahora está disponible y se puede invocar mediante el envío de solicitudes\<al servicio. SVC/> de operación (por ejemplo, Service `Add` . SVC/Add para la operación). Puede utilizarlo introduciendo la URL del punto de conexión en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, vea el [servicio Ajax mediante http post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
## <a name="see-also"></a>Vea también

- [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [Procedimientos: Migración de servicios Web ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
