---
title: Validación de seguridad
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0aaa88268959561cabe4613d51feb0f219275634
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44178037"
---
# <a name="security-validation"></a>Validación de seguridad
Este ejemplo muestra cómo utilizar un comportamiento personalizado para validar los servicios en un equipo a fin de asegurarse de que cumplen criterios específicos. En este ejemplo, el comportamiento personalizado valida estos servicios analizando cada punto de conexión en el servicio y comprobando si contienen elementos de enlace seguros. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## <a name="endpoint-validation-custom-behavior"></a>Comportamiento personalizado de validación del extremo  
 Al agregar código de usuario al método `Validate` contenido en la interfaz <xref:System.ServiceModel.Description.IServiceBehavior>, se puede dar el comportamiento personalizado a un servicio o extremo para realizar las acciones definidas por el usuario. El código siguiente se utiliza para recorrer a través de cada punto de conexión contenido en un servicio, que busca en las colecciones de enlaces los enlaces seguros.  
  
```  
public void Validate(ServiceDescription serviceDescription,   
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually gathering their    
       binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =   
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any   
        // secure binding elements. Transport, Asymmetric, and Symmetric      
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 Al agregar el código siguiente al archivo Web.config, se agrega la extensión de comportamiento `serviceValidate` para que el servicio la reconozca.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 Una vez agregada al servicio la extensión de comportamiento, ahora es posible agregar el comportamiento `endpointValidate` a la lista de comportamientos en el archivo Web.config y así al servicio.  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 Los comportamientos y las extensiones que se agregan al archivo Web.config aplican el comportamiento a los servicios individuales, mientras que cuando se agregan al archivo Machine.config aplican el comportamiento a cada servicio activo del equipo.  
  
> [!NOTE]
>  Al agregar el comportamiento a todos los servicios, la sugerencia es realizar una copia de seguridad del archivo Machine.config antes de realizar cualquier modificación.  
  
 Ahora ejecute el cliente proporcionado en el directorio client\bin de este ejemplo. Tiene una excepción se produce el siguiente mensaje: "el servicio solicitado, 'http://localhost/servicemodelsamples/service.svc' no se pudo activar." Se espera este mensaje porque el comportamiento que valida el punto de conexión considera inseguro al punto de conexión y evita que se inicie el servicio. El comportamiento también produce una excepción interna que describe qué punto de conexión es inseguro y escribe un mensaje en el visor de eventos en el origen "System.ServiceModel 4.0.0.0" y la categoría "WebHost". También es posible activar el seguimiento en el servicio en este ejemplo. Esto le permite al usuario ver las excepciones iniciadas por el comportamiento que valida el extremo abriendo los seguimientos de servicio resultantes mediante la herramienta Service Trace Viewer.  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a>Para ver los mensajes de excepción de validación del punto de conexión en el visor de eventos  
  
1.  Haga clic en el **iniciar** menú y seleccione **ejecutar...** .  
  
2.  Tipo `eventvwr` y haga clic en **Aceptar**.  
  
3.  En la ventana Visor de eventos, haga clic en **aplicación**.  
  
4.  Haga doble clic en el evento "System.ServiceModel 4.0.0.0" recientemente agregado en la categoría "WebHost" en el **aplicación** ventana para ver los mensajes inseguros del extremo.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
