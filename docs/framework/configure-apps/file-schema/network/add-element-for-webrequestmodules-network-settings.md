---
title: "&lt;add&gt; (Elemento para webRequestModules, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add> (elemento), webRequestModules"
  - "<webRequestModules>, add (elemento)"
  - "add (elemento), webRequestModules"
  - "webRequestModules, add (elemento)"
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# &lt;add&gt; (Elemento para webRequestModules, Configuraci&#243;n de red)
Agrega un módulo de solicitud Web personalizado a la aplicación.  
  
## Sintaxis  
  
```  
  
      <add   
  prefix = "URI prefix"   
  type = "module name, Version, Culture, PublicKeyToken"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`prefix`|Prefijo URI para las solicitudes controladas por este módulo de solicitud Web.|  
|`type`|Nombre de ensamblado y de clase del módulo que implementa este módulo de solicitud Web.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Especifica los módulos que se utilizan para solicitar información a hosts de la red.|  
  
## Comentarios  
 El atributo `prefix` define el prefijo URI que utiliza el módulo de solicitud Web especificado.  Los módulos de solicitud Web normalmente se registran con el fin de controlar un protocolo específico, como HTTP o FTP, pero también se pueden registrar para controlar una solicitud en un servidor específico o en una ruta de acceso de un servidor.  
  
 El módulo de solicitud web se crea cuando se pasa al método <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName> un prefijo URI coincidente.  
  
 El valor para el atributo `prefix` debería corresponder a los caracteres principales de un URI válido \(por ejemplo, "http" o "http:\/\/www.contoso.com".  
  
 El valor para el atributo `type` debería ser un nombre de archivo DLL válido y el nombre de clase correspondiente, separados por una coma.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se registra un módulo de solicitud Web personalizado para HTTP.  Deberían reemplazarse los valores de Version y PublicKeyToken con los valores correctos para el módulo especificado.  
  
```  
<configuration>  
  <system.net>  
    <webRequestModules>  
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