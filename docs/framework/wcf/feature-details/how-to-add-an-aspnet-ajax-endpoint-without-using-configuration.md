---
title: "C&#243;mo agregar un punto de conexi&#243;n AJAX de ASP.NET sin usar la configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# C&#243;mo agregar un punto de conexi&#243;n AJAX de ASP.NET sin usar la configuraci&#243;n
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] le permite crear un servicio que expone un extremo de ASP.NET con AJAX habilitado al que se puede llamar desde JavaScript de un sitio web del cliente. Para crear este tipo de extremo, puede usar un archivo de configuración, como con todos los otros extremos de WCF, o utilizar un método que no requiera ningún elemento de configuración. En este tema se muestra el segundo enfoque.  
  
 Para crear servicios con puntos de conexión de AJAX de ASP.NET sin configuración, Internet Information Services (IIS) debe hospedar los servicios. Para activar un extremo ASP.NET AJAX con este enfoque, especifique la <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> como parámetro de fábrica en el [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) la directiva en el archivo .svc. Este generador personalizado es el componente que configura automáticamente un punto de conexión de AJAX de ASP.NET para que se le pueda llamar desde JavaScript en un sitio web del cliente.  
  
 Para obtener un ejemplo, vea la [servicio AJAX sin configuración](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
 Para una descripción de cómo configurar un extremo de AJAX de ASP.NET mediante elementos de configuración, consulte [Cómo: usar la configuración para agregar un extremo de AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Para crear un servicio WCF básico  
  
1.  Definir un basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contrato de servicio con una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Asegúrese de establecer el <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> propiedad.  
  
    ```  
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
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>Hospedaje del servicio en Internet Information Services sin configuración  
  
1.  Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación. Edite este archivo agregando adecuado [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) información de directiva para el servicio. Especificar que la <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se utiliza en el [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directiva para configurar automáticamente un extremo de AJAX de ASP.NET.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2.  Compile el servicio y llámelo desde el cliente. Internet Information Services (IIS) activa el servicio cuando se llama. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]alojamiento en IIS, consulte [Cómo: hospedar un servicio WCF en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1.  El extremo se configura en una dirección vacía relativa al archivo .svc, por lo que el servicio ya está disponible y se puede invocar enviando solicitudes a Service.svc /<> \</> \> : por ejemplo, Service.svc/Add para la `Add` operación. Puede utilizarlo introduciendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, consulte el [servicio AJAX sin configuración](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Ejemplo  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 El punto de conexión configurado automáticamente se crea en una dirección vacía relativa a la URL base. También se puede agregar y utilizar un archivo de configuración con este enfoque. Si el archivo de configuración contiene las definiciones de punto de conexión, estos puntos de conexión se agregan al punto de conexión configurado automáticamente.  
  
 Por ejemplo, service.svc usa el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> y el directorio de servicio contiene un archivo Web.config que define un extremo para el mismo servicio mediante el <xref:System.ServiceModel.BasicHttpBinding> en la dirección relativa de "soap". En este caso, el servicio contiene dos puntos de conexión: uno en service.svc (que responde a las solicitudes de AJAX de ASP.NET) y otro en service.svc/soap (que responde a las solicitudes SOAP).  
  
 Si el archivo de configuración define un extremo en una dirección relativa vacía y el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es usa, se produce una excepción y no se puede iniciar el servicio.  
  
 No puede utilizar la configuración para modificar los valores en el punto de conexión configurado automáticamente. Si algún valor (como una cuota del lector) debe ser modificado, no debe utilizar el enfoque sin configuración quitando el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> desde el archivo .svc y creando una entrada de configuración para el extremo.  
  
 Si su servicio requiere el modo de compatibilidad ASP.NET; por ejemplo, si usa el <xref:System.Web.HttpContext> clase o los mecanismos de autorización de ASP.NET - un archivo de configuración está siendo necesario para activar este modo. El elemento de configuración requerido es el [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) elemento, que debe agregarse como sigue.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled=”true” /> </system.serviceModel>`  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]el [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) tema.  
  
 El <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es una clase derivada de <xref:System.ServiceModel.Activation.ServiceHostFactory>. Para obtener una explicación detallada del mecanismo de fábrica de host de servicio, consulte la [extender ServiceHostFactory utilizando hospedaje](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) tema.  
  
## <a name="see-also"></a>Vea también  
 [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)   
 [Cómo: migrar servicios Web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)