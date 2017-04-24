---
title: "Intercambio de mensajes dentro de una sesi&#243;n confiable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Intercambio de mensajes dentro de una sesi&#243;n confiable
En este tema se describen los pasos necesarios para habilitar una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.Puede habilitar la sesión confiable de manera imperativa mediante código o de manera declarativa mediante configuración.Este procedimiento utiliza los archivos de configuración de cliente y servicio para habilitar la sesión confiable y para estipular que los mensajes lleguen en el mismo orden en el que se enviaron.  
  
 La parte clave de este procedimiento es que el elemento de configuración del extremo contenga un atributo `bindingConfiguration` que haga referencia a una configuración de enlace denominada "Binding1". El elemento de configuración [\<enlace\>](../../../../docs/framework/misc/binding.md)`enabled puede hacer referencia a continuación a este nombre para habilitar las sesiones confiables estableciendo el atributo` [reliableSession del elemento](http://msdn.microsoft.com/es-es/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)`true en` .Especifica las garantías de entrega ordenada de la sesión confiable estableciendo el atributo `ordered` en `true`.  
  
 Para la copia de origen de este ejemplo, vea [Sesión de confianza de WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).  
  
### Configuración del servicio con WSHttpBinding para utilizar una sesión confiable  
  
1.  Defina un contrato de servicios para el tipo de servicio.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]  
  
2.  Implemente el contrato de servicios en una clase de servicio.Observe que la información de enlace o dirección no se especifica en ninguna parte de la implementación del servicio.Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]  
  
3.  Cree un archivo Web.config para configurar un extremo del `CalculatorService` que utiliza el <xref:System.ServiceModel.WSHttpBinding> con sesión confiable habilitada y entrega ordenada de mensajes requerida..  
  
     <!-- TODO: review snippet reference [!code[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]  -->  
  
4.  Cree un archivo Service.svc que contenga la línea:  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Coloque el archivo Service.svc en el directorio virtual de Internet Information Services \(IIS\).  
  
### Configuración del cliente con un WSHttpBinding para utilizar una sesión confiable  
  
1.  Utilice la [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio:  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]  
  
3.  La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.Observe que la información de enlace y dirección no se especifica en ninguna parte de la implementación del servicio.Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]  
  
4.  Svcutil.exe también genera la configuración para el cliente que utiliza la clase <xref:System.ServiceModel.WSHttpBinding>.Este archivo se debería denominar App.config al utilizar [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]  -->  
  
5.  Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]  
  
6.  Compile y ejecute el cliente.  
  
## Ejemplo  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 Algunos de los enlaces proporcionados por el sistema admiten de forma predeterminada las sesiones confiables.Éstos incluyen:  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>  
  
 Para obtener un ejemplo sobre cómo crear un enlace personalizado que admita sesiones confiables, vea [Creación de un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).  
  
## Vea también  
 [Sesiones de confianza](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)