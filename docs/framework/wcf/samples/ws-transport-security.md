---
title: "Seguridad de transporte WS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# Seguridad de transporte WS
Este ejemplo muestra el uso de la seguridad de transporte de SSL con el enlace <xref:System.ServiceModel.WSHttpBinding>.De forma predeterminada, el enlace `wsHttpBinding` proporciona la comunicación HTTP.Cuando se configura para la seguridad de transporte, el enlace admite la comunicación HTTPS.Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.`wsHttpBinding` se especifica y se configura en los archivos de configuración de la aplicación para el cliente y el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 El código de programa del ejemplo es idéntico al del servicio de [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).Debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web antes de compilar y ejecutar el ejemplo.La definición de extremo y de enlace en la configuración del archivo de configuración habilitan el modo de seguridad `Transport`, tal y como se muestra en la configuración de ejemplo siguiente para el cliente.  
  
```  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
  
```  
  
 La dirección especificada utiliza el esquema https:\/\/.La configuración de enlace establece el modo de seguridad en `Transport`.Debe especificarse el mismo modo de seguridad en el archivo Web.config del servicio.  
  
 Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert.exe, aparecerá una alerta de seguridad al intentar tener acceso a una dirección https:, como https:\/\/localhost\/servicemodelsamples\/service.svc, desde el explorador.Para permitir al cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] trabajar con un certificado de prueba, se ha añadido código adicional al cliente para suprimir la alerta de seguridad.Este código, y la clase que lo acompaña, no son necesarios cuando se usan certificados de producción.  
  
```  
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Asegúrese de realizar los [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Asegúrese de realizar las [Instrucciones de instalación del certificado de servidor de Internet Information Services \(IIS\)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Vea también