---
title: "&lt;connectionManagement&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<connectionManagement> (elemento)"
  - "connectionManagement (elemento)"
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;connectionManagement&gt; (Elemento, Configuraci&#243;n de red)
Especifica el número máximo de conexiones a un host de red.  
  
## Sintaxis  
  
```  
  
      <connectionManagement>   
</connectionManagement>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[agregar](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|Agrega una dirección IP o un nombre DNS a la lista de administración de conexiones.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|Borra la lista de administración de conexiones.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene los valores de configuración que especifican cómo se conecta a la red .NET Framework.|  
  
## Comentarios  
 El elemento `connectionManagement` define el número máximo de conexiones con un servidor o un grupo de servidores.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se configura una aplicación para que se utilicen cuatro conexiones con el servidor www.contoso.com y dos conexiones con todos los demás servidores.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
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