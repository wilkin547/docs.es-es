---
title: "&lt;webHttpEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;webHttpEndpoint&gt;
Este elemento de configuración define un extremo estándar con un enlace [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fijo que agrega automáticamente el comportamiento [\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md).  Utilice este extremo al escribir un servicio REST.  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <webHttpEndpoint>   
          <standardEndpoint  
             automaticFormatSelectionEnabled="String"   
             defaultOutgoingResponseFormat=”Xml/Json”  
             helpEnabled=”Boolean”  
             webEndpointType=”String”/>        
       </webHttpEndpoint>   
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|automaticFormatSelectionEnabled|Valor booleano que indica si la selección de formato automática está habilitada.<br /><br /> Cuando la selección de formato automática está habilitada, la infraestructura analiza el encabezado `Accept` del mensaje de solicitud y determina el formato de la respuesta más adecuado.  Si el encabezado `Accept` no especifica un formato de respuesta adecuado, la infraestructura usa el `Content-Type` del mensaje de solicitud o el formato de respuesta predeterminado de la operación.|  
|defaultOutgoingResponseFormat|Un atributo que especifica el formato de respuesta saliente predeterminado.  Este atributo es del tipo <xref:System.Servicemodel.Web.Webmessageformat>.|  
|helpEnabled|Valor booleano que indica si la página de ayuda HTTP está habilitada para el extremo.|  
|webEndpointType|Cadena que especifica el tipo de extremo.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Colección de extremos estándar que son extremos predefinidos con una o más de sus propiedades \(dirección, enlace, contrato\) fijas.|  
  
## Vea también  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>   
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>