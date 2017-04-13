---
title: "&lt;add&gt; de &lt;defaultPorts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; de &lt;defaultPorts&gt;
Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.  
  
## Sintaxis  
  
```  
  
<useRequestHeadersForMetadataAddress>  
   <defaultPorts>  
      <add port="Integer" scheme="String" />  
   </defaultPorts>  
</useRequestHeadersForMetadataAddress>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|puerto|Entero que especifica el número del puerto de comunicaciones predeterminado.|  
|scheme|Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<defaultPorts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|Colección de puertos predeterminados que enumeran los extremos de comunicaciones predeterminados que escucha la aplicación cliente.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>