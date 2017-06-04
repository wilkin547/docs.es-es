---
title: "&lt;encabezados&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;encabezados&gt;
Uno o más encabezados SOAP pueden direccionar un extremo además de su URI básico.  Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.  Este elemento de configuración se puede usar para definir tales encabezados de dirección personalizados.  Las entradas en la colección de encabezado de extremo son los elementos XML definidos por el usuario.  Cada elemento tiene que ser XML correcto.  
  
## Sintaxis  
  
```  
  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|Región||  
|Miembro||  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<extremo\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Configura tipos diferentes de extremos.|  
  
## Comentarios  
 Los encabezados opcionales proporcionan información más detallada de direccionamiento para identificar o interactuar con el extremo.  Por ejemplo, los encabezados pueden indicar cómo procesar un mensaje entrante, dónde debería enviar el extremo un mensaje de respuesta o qué instancia de un servicio se va a usar para procesar un mensaje entrante de un usuario determinado cuando hay varias instancias disponibles.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>   
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>   
 [Extremos: direcciones, enlaces y contratos](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)