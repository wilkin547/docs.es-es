---
title: "Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Elemento &lt;windowsAuthentication&gt; de &lt;serviceCredentials&gt;
Especifica los valores de una credencial del servicio de Windows.  
  
## Sintaxis  
  
```  
  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`includeWindowsGroups`|Un atributo booleano opcional que especifica si el sistema incluye los grupos de Windows en el contexto de seguridad.  De manera predeterminada, es `true`.<br /><br /> Al establecer este atributo en `true`, se tiene un impacto de rendimiento y tiene como resultado una expansión de grupo completa.  Establezca este atributo en `false` si no necesita establecer la lista de grupos a los que un usuario pertenece.|  
|`allowAnonymousLogons`|Un atributo booleano opcional que especifica si se permiten las llamadas anónimas, no autenticadas.  De manera predeterminada, es `false`.<br /><br /> Cuando el atributo `clientCredentialType` de un enlace está establecido en `Windows`, el sistema no permite las llamadas anónimas.  Esto significa que sólo los llamadores autenticados del dominio o grupo de trabajo tienen acceso al sistema.  Se puede reemplazar este comportamiento utilizando este atributo.<br /><br /> Utilice esta configuración con extrema precaución.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
  
## Comentarios  
 Utilice este elemento para especificar si se permite a los usuarios anónimos de Windows obtener acceso estableciendo el atributo `allowAnonymousLogons`.  También puede especificar si se incluye información del grupo a la que pertenecen los usuarios en AuthorizationContext estableciendo el atributo `includeWindowsGroups`.  Si se establece como `true` \(valor predeterminado\), el servicio puede determinar los grupos de Windows a los que pertenece el cliente.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>   
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>   
 <xref:System.ServiceModel.Security.WindowsServiceCredential>