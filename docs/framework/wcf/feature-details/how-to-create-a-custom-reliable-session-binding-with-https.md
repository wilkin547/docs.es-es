---
title: "Creaci&#243;n de un enlace personalizado de sesi&#243;n confiable con HTTPS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Creaci&#243;n de un enlace personalizado de sesi&#243;n confiable con HTTPS
En este tema se muestra el uso de la seguridad de transporte de capa de sockets seguros \(SSL\) con sesiones confiables.  Para utilizar una sesión confiable sobre HTTPS, debe crear un enlace personalizado que utilice una sesión confiable y el transporte de HTTPS.  Puede habilitar la sesión confiable de manera imperativa mediante código o de manera declarativa mediante configuración.  Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión confiable y el elemento [\<httpsTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md).  
  
 La parte clave de este procedimiento es que el elemento de configuración `endpoint` contenga un atributo `bindingConfiguration` que haga referencia a una configuración de enlace personalizado denominado "reliableSessionOverHttps".  El elemento de configuración [\<enlace\>](../../../../docs/framework/misc/binding.md)`reliableSession puede hacer referencia a continuación a este nombre para especificar que se utiliza una sesión confiable y el transporte HTTPS incluyendo elementos` `httpsTransport y` .  
  
 Para ver la copia del origen de este ejemplo, consulte [Sesión confiable de enlace personalizado mediante HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).  
  
### Configuración del servicio con un CustomBinding para utilizar una sesión confiable con HTTPS  
  
1.  Defina un contrato de servicios para el tipo de servicio.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]  
  
2.  Implemente el contrato de servicios en una clase de servicio.  Observe que la información de enlace o dirección no se especifica en ninguna parte de la implementación del servicio.  Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]  
  
3.  Cree un archivo Web.config para configurar un extremo para el `CalculatorService` con un enlace personalizado denominado "reliableSessionOverHttps" que utilice una sesión confiable y el transporte de HTTPS.  
  
     <!-- TODO: review snippet reference [!code[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]  -->  
  
4.  Cree un archivo Service.svc que contenga la línea:  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Coloque el archivo Service.svc en el directorio virtual de Internet Information Services \(IIS\).  
  
### Configuración del cliente con un CustomBinding para utilizar una sesión confiable con HTTPS  
  
1.  Utilice la [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]  
  
3.  La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.  Observe que la información de enlace y dirección no se especifica en ninguna parte de la implementación del servicio.  Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]  
  
4.  Configure un enlace personalizado denominado "reliableSessionOverHttps" para que use el transporte HTTPS y sesiones confiables.  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]  -->  
  
5.  Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]  
  
6.  Compile y ejecute el cliente.  
  
## Ejemplo  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## Seguridad de .NET Framework  
 Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert.exe, aparecerá una alerta de seguridad al intentar obtener acceso a una dirección HTTPS:, como https:\/\/localhost\/servicemodelsamples\/service.svc, desde el explorador.  
  
## Vea también  
 [Sesiones de confianza](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)