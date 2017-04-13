---
title: "C&#243;mo: Especificar el tipo de credencial de cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "credenciales de seguridad, agregar a mensajes SOAP"
  - "WCF, seguridad"
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Especificar el tipo de credencial de cliente
Después de establecer un modo de seguridad \(ya sea transporte o mensaje\), tiene la opción de establecer el tipo de credencial de cliente.Esta propiedad especifica qué tipo de credencial debe proporcionar el cliente al servicio para la autenticación.[!INCLUDE[crabout](../../../includes/crabout-md.md)] establecer el modo de seguridad \(un paso necesario antes de establecer el tipo de credencial del cliente\), vea [Cómo: Establecer el modo de seguridad](../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
### Para establecer el tipo de credencial de cliente en el código  
  
1.  Cree una instancia del enlace que el servicio va a usar.En el ejemplo siguiente se utiliza el enlace <xref:System.ServiceModel.WSHttpBinding>.  
  
2.  Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> en un valor adecuado.Este ejemplo utiliza el modo de mensaje.  
  
3.  Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en un valor apropiado.Este ejemplo establece el uso de la autenticación de Windows \(<xref:System.ServiceModel.MessageCredentialType>\).  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### Para establecer el tipo de credencial en la configuración  
  
1.  Agregue un elemento [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) al archivo de configuración.  
  
2.  Como elemento secundario, añada un elemento [\<enlaces\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md).  
  
3.  Agregue un enlace adecuado.En el ejemplo siguiente se utiliza el elemento [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
4.  Agregue un elemento [\<enlace\>](../../../docs/framework/misc/binding.md)`name` y establezca el atributo en un valor adecuado.Este ejemplo utiliza el nombre "SecureBinding".  
  
5.  Agregue un enlace `<security>`.Establezca el atributo `mode` en un valor adecuado.Este ejemplo lo define en `"Message"`.  
  
6.  Agregue un elemento `<message>``<transport> o` , tal y como se haya determinado en el modo de seguridad.Establezca el atributo `clientCredentialType` en un valor adecuado.Este ejemplo utiliza `"Windows"`.  
  
    ```  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## Vea también  
 [Seguridad de servicios](../../../docs/framework/wcf/securing-services.md)   
 [Cómo: Establecer el modo de seguridad](../../../docs/framework/wcf/how-to-set-the-security-mode.md)