---
title: "Elemento &lt;windows&gt; de &lt;clientCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Elemento &lt;windows&gt; de &lt;clientCredentials&gt;
Especifica los valores para una credencial de Windows que se va a utilizar para representar al cliente.  
  
## Sintaxis  
  
```  
  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`allowedImpersonationLevel`|Establece la preferencia de suplantación que el cliente comunica al servidor.  El modo de suplantación que el cliente elige no se exige en el servidor.  Los valores válidos son los siguientes:<br /><br /> -   Identification: el servidor puede obtener la identidad y privilegios del cliente, pero no puede suplantar al cliente.<br />-   Impersonation: el servidor puede suplantar el contexto de seguridad del cliente en el sistema local.<br />-   Delegation: el servidor puede suplantar el contexto de seguridad del cliente en sistemas remotos.<br />-   Anonymous: el servidor no puede suplantar o identificar al cliente.<br />-   None: no se ha asignado un nivel de suplantación.<br /><br /> El valor predeterminado es Identification.  Este atributo es del tipo <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|Establecer esta propiedad en `true` permite a la autenticación degradar a NTLM si Kerberos no está disponible.<br /><br /> Establecer esta propiedad en `false` hace que [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] realice un mayor esfuerzo por iniciar una excepción si se utiliza NTLM.  Tenga en cuenta que, aunque se establezca esta propiedad en `false`, es posible que se envíen igualmente las credenciales NTLM a través de la conexión.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Especifica las credenciales utilizadas para autenticar el cliente al servicio.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>   
 <xref:System.ServiceModel.Security.WindowsClientCredential>   
 [Protección de clientes](../../../../../docs/framework/wcf/securing-clients.md)   
 [Trabajar con certificados](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)