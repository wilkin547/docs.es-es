---
title: "&lt;compositeDuplex&gt; | Microsoft Docs"
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
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;compositeDuplex&gt;
Define el elemento de enlace que se usa cuando el cliente debe exponer un extremo para que el servicio devuelva los mensajes al cliente.  
  
## Sintaxis  
  
```  
  
<compositeDuplex clientBaseAddress="URI" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|clientBaseAddress|Un URI que establece la dirección del canal secundario en modo de dúplex.  El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.<br /><br /> Si no se establece este atributo, se genera una dirección predeterminada "`full qualified name+default port\TemporaryIndigoAddress\guid`".  De manera predeterminada, es `null`.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP.  TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.  
  
 El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.  El atributo `clientBaseAddress` proporciona esta dirección del cliente.  Observe que Windows Communication Foundation \(WCF\) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.  
  
## Ejemplo  
  
```  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.CompositeDuplexElement>   
 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)