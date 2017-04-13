---
title: "Seguridad de mensaje de Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Seguridad WS"
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
caps.latest.revision: 34
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 34
---
# Seguridad de mensaje de Windows
Este ejemplo muestra cómo configurar un<xref:System.ServiceModel.WSHttpBinding> que enlaza para utilizar la seguridad del nivel de mensaje con autenticación de Windows.  Este ejemplo se basa en [Introducción:](../../../../docs/framework/wcf/samples/getting-started-sample.md).  En este ejemplo, el cliente es una aplicación de consola \(.exe\) y los Servicios de Internet Information Server \(IIS\) hospedan el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 La seguridad predeterminada para [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) es la seguridad de mensajes mediante la autenticación de Windows.  Los archivos de configuración en este ejemplo establecieron explícitamente el atributo `mode` de [\<seguridad\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) en `Message` y el atributo `clientCredentialType` a `Windows`.  Estos valores son los valores predeterminados para este enlace, pero se han configurado explícitamente, como se muestra en la configuración del ejemplo siguiente para mostrar su uso.  
  
```  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 La configuración de extremo de cliente está compuesta de una dirección absoluta para el extremo de servicio, el enlace y el contrato.  El enlace del cliente se configura con el `securityMode` adecuado y `authenticationMode`.  
  
```  
  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      <!--The default security for the WSHttpBinding is-->  
      <!--Message security using Windows authentication. -->  
      <!--This configuration explicitly defines the security mode -->  
      <!--as Message and the clientCredentialType as Windows  -->  
      <!--for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
  
```  
  
 El código fuente del servicio se ha modificado para mostrar cómo <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> se puede utilizar para tener acceso a la identidad del llamador.  
  
```  
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.  El primer método llamado \- `GetCallerIdentity`\- devuelve el nombre de la identidad del llamador al cliente.  Presione ENTRAR en la ventana de la consola para cerrar el cliente.  
  
### Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar el procedimiento de [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Vea también