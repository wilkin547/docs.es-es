---
title: "&lt;remove&gt; (Elemento para webRequestModules, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<remove> (elemento), webRequestModules"
  - "<webRequestModules>, remove (elemento)"
  - "remove (elemento), webRequestModules"
  - "webRequestModules, remove (elemento)"
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;remove&gt; (Elemento para webRequestModules, Configuraci&#243;n de red)
Quita un módulo de solicitud Web personalizado de la aplicación.  
  
## Sintaxis  
  
```  
  
      <remove   
  name = "URI prefix"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`name`|Prefijo URI para las solicitudes controladas por este módulo de solicitud Web.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Especifica los módulos que se utilizan para solicitar información a hosts de la red.|  
  
## Comentarios  
 El elemento `remove` quita el módulo de solicitud Web registrado para el prefijo URI especificado.  
  
 El valor para el atributo `prefix` debería corresponder a los caracteres principales de un URI válido \(por ejemplo, "http" o "http:\/\/www.contoso.com".  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se quita el módulo de solicitud Web existente para HTTP y, a continuación, se registra un nuevo módulo de solicitud Web personalizado para solicitudes HTTP en www.contoso.com.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix = "http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.WebRequest>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)