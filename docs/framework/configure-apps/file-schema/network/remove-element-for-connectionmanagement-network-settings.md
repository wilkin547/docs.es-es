---
title: "&lt;remove&gt; (Elemento para connectionManagement, Configuraci&#243;n de red) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<connectionManagement>, remove (elemento)"
  - "<remove> (elemento), connectionManagement"
  - "connectionManagement, remove (elemento)"
  - "remove (elemento), connectionManagement"
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# &lt;remove&gt; (Elemento para connectionManagement, Configuraci&#243;n de red)
Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.  
  
## Sintaxis  
  
```  
  
      <remove   
   name = "server name or IP address"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`address`|Dirección IP o nombre DNS.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a un host de red.|  
  
## Comentarios  
 El elemento `remove` quita la entrada de la lista de administración de conexiones para el servidor especificado.  
  
 El valor del atributo `address` debería corresponder a una dirección IP válida o nombre de host.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se quita de la lista de administración de conexiones cualquier entrada correspondiente al servidor www.adventure\-works.com, a la vez que se configura una aplicación para que se utilicen cuatro conexiones con el servidor www.contoso.com y dos conexiones con todos los demás servidores.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address = "http://www.adventure-works.com"/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.ServicePoint>   
 <xref:System.Net.ServicePointManager>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)