---
title: "&lt;clear&gt; (Elemento para connectionManagement, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear> (elemento), connectionManagement"
  - "<connectionManagement>, clear (elemento)"
  - "clear (elemento), connectionManagement"
  - "connectionManagement, clear (elemento)"
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;clear&gt; (Elemento para connectionManagement, Configuraci&#243;n de red)
Borra la lista de administración de conexiones.  
  
## Sintaxis  
  
```  
  
<clear/>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a un host de red.|  
  
## Comentarios  
 El elemento `clear` borra todas las entradas de la lista de administración de conexiones.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el siguiente ejemplo de código se borra la lista de administración de conexiones y se agregan nuevas entradas para el servidor www.contoso.com y todos los demás hosts de red.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
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