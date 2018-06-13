---
title: Cómo agregar un punto de conexión AJAX de ASP.NET sin usar la configuración
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: cc3cca2ed703c4329b3da7c6fde286c341459fa8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496131"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Cómo agregar un punto de conexión AJAX de ASP.NET sin usar la configuración
Windows Communication Foundation (WCF) le permite crear un servicio que expone un extremo habilitado para AJAX de ASP.NET que se puede llamar desde JavaScript en un sitio Web del cliente. Para crear este tipo de punto de conexión, puede usar un archivo de configuración, como con todos los otros puntos de conexión de WCF, o utilizar un método que no requiera ningún elemento de configuración. En este tema se muestra el segundo enfoque.  
  
 Para crear servicios con puntos de conexión de AJAX de ASP.NET sin configuración, Internet Information Services (IIS) debe hospedar los servicios. Para activar un punto de conexión de AJAX de ASP.NET con este enfoque, especifique la <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> como el parámetro de fábrica en el [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) la directiva en el archivo .svc. Este generador personalizado es el componente que configura automáticamente un punto de conexión de AJAX de ASP.NET para que se le pueda llamar desde JavaScript en un sitio web del cliente.  
  
 Para obtener un ejemplo, vea el [servicio de AJAX sin configuración](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Para obtener una breve descripción de cómo configurar un punto de conexión de AJAX de ASP.NET mediante elementos de configuración, consulte [Cómo: usar la configuración para agregar un extremo de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Para crear un servicio WCF básico  
  
1.  Definir un contrato de servicio WCF básico con una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>Hospedaje del servicio en Internet Information Services sin configuración  
  
1.  Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación. Editar este archivo agregando adecuado [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) información de directiva para el servicio. Especificar que la <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es que se usará en el [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva para configurar automáticamente un punto de conexión de AJAX de ASP.NET.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2.  Compile el servicio y llámelo desde el cliente. Internet Information Services (IIS) activa el servicio cuando se llama. Para obtener más información sobre el hospedaje en IIS, consulte [Cómo: hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1.  El extremo se configura en una dirección vacía relativa al archivo .svc, por lo que el servicio ahora está disponible y se puede invocar enviando solicitudes a Service.svc /\<operación >: por ejemplo, Service.svc/Add para la `Add` operación. Puede utilizarlo introduciendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, vea el [servicio de AJAX sin configuración](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Ejemplo  
  
 El punto de conexión configurado automáticamente se crea en una dirección vacía relativa a la URL base. También se puede agregar y utilizar un archivo de configuración con este enfoque. Si el archivo de configuración contiene las definiciones de punto de conexión, estos puntos de conexión se agregan al punto de conexión configurado automáticamente.  
  
 Por ejemplo, service.svc usa <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> y el directorio del servicio contiene un archivo Web.config que define un extremo para el mismo servicio mediante el elemento <xref:System.ServiceModel.BasicHttpBinding> de la dirección relativa de "soap". En este caso, el servicio contiene dos puntos de conexión: uno en service.svc (que responde a las solicitudes de AJAX de ASP.NET) y otro en service.svc/soap (que responde a las solicitudes SOAP).  
  
 Si el archivo de configuración define un extremo en una dirección relativa vacía y se utiliza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, se produce una excepción y el servicio no puede iniciarse.  
  
 No puede utilizar la configuración para modificar los valores en el extremo configurado automáticamente. Si se debe modificar algún valor (como una cuota del lector), no debe utilizar el enfoque sin configuración quitando el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> del archivo .svc y creando una entrada de configuración para el extremo.  
  
 Si su servicio requiere el modo de compatibilidad de ASP.NET; por ejemplo, si utiliza la clase <xref:System.Web.HttpContext> o los mecanismos de autorización de ASP.NET, se sigue requiriendo un archivo de configuración para activar este modo. El elemento de configuración necesario es la [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) elemento, que debe agregarse como se indica a continuación.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Para obtener más información, consulte el [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) tema.  
  
 La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es una clase derivada de <xref:System.ServiceModel.Activation.ServiceHostFactory>. Para obtener una explicación detallada del mecanismo de fábrica de host de servicio, consulte la [extender hospedaje utilizando ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) tema.  
  
## <a name="see-also"></a>Vea también  
 [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [Migración de servicios web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
