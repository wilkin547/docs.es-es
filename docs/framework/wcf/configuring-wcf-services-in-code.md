---
title: Configurar servicios WCF en el código
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 2046ee00bef0f3e84a61151474c777d64005a30c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-wcf-services-in-code"></a>Configurar servicios WCF en el código
Windows Communication Foundation (WCF) permite a los desarrolladores configurar servicios mediante archivos de configuración o código.  Los archivos de configuración son útiles cuando un servicio se debe configurar después de implementarse. Cuando se usan archivos de configuración, un profesional de TI solo debe actualizar el archivo de configuración; no es necesario que realice ninguna recompilación. Los archivos de configuración, sin embargo, pueden ser complejos y difíciles de mantener. No se admite la depuración de archivos de configuración y se hace referencia a los elementos de configuración por nombre, con lo que la creación de archivos de configuración resulta propensa a errores y difícil. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también permite configurar servicios en el código. En versiones anteriores de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (4.0 y anteriores), la configuración de servicios en código era sencilla en escenarios autohospedados; la clase <xref:System.ServiceModel.ServiceHost> permitía configurar extremos y comportamientos antes de llamar a ServiceHost.Open. En escenarios hospedados en web, sin embargo, no tiene acceso directo a la clase <xref:System.ServiceModel.ServiceHost>. Para configurar un servicio hospedado en web era necesario crear un `System.ServiceModel.ServiceHostFactory` que creó el <xref:System.ServiceModel.Activation.ServiceHostFactory> y realizar cualquier configuración necesaria. A partir de .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona una manera más fácil de configurar los servicios autohospedados y los hospedados en web en el código.  
  
## <a name="the-configure-method"></a>El método Configure  
 Defina simplemente un método estático público denominado `Configure` con la signatura siguiente en la clase de implementación del servicio:  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 El método Configure toma una instancia de <xref:System.ServiceModel.ServiceConfiguration> que permite al desarrollador agregar extremos y comportamientos. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] llama a este método antes de abrir el host de servicio. Cuando se definen, los valores de configuración de servicio especificados en un archivo app.config o web.config se omitirán.  
  
 El fragmento de código siguiente muestra cómo definir el método `Configure` y agregar un extremo de servicio, un comportamiento de extremo y comportamientos del servicio:  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 Para habilitar un protocolo como https para un servicio, puede agregar explícitamente un punto de conexión que use el protocolo o puede agregar automáticamente puntos de conexión llamando a ServiceConfiguration.EnableProtocol (enlace) que agregue un punto de conexión para cada dirección base compatible con el protocolo y cada contrato de servicio definido. El código siguiente ilustra cómo usar el método ServiceConfiguration.EnableProtocol:  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 La configuración en el <`protocolMappings`> sección sólo se utilizarán si no hay extremos de la aplicación se agregan a la <xref:System.ServiceModel.ServiceConfiguration> mediante programación. Si lo desea, puede cargar la configuración del servicio desde el archivo de configuración de aplicación predeterminado mediante una llamada a <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> y, a continuación, cambiar la configuración. La clase <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> también permite cargar la configuración desde una configuración centralizada. El código siguiente muestra cómo implementar esto:  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  Tenga en cuenta que <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> omite <`host`> configuración de la <`service`> etiqueta de <`system.serviceModel`>. Conceptualmente, <`host`> trata sobre la configuración del host, no configuración del servicio y se cargan antes de que se ejecuta el método de configurar.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de servicios mediante archivos de configuración](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [Configuración de los comportamientos del cliente](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md)  
 [Activación basada en la configuración](../../../docs/framework/wcf/samples/configuration-based-activation.md)  
 [Configuración](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [Activación basada en la configuración en IIS y WAS](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [Compatibilidad con metadatos y configuración](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [Configuración](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [Cómo especificar un enlace de servicio en la configuración](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Creación de un punto de conexión de servicio en configuración](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Publicación de metadatos para un servicio mediante un archivo de configuración](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Cómo especificar un enlace de cliente en la configuración](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
