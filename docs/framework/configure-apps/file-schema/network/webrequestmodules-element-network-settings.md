---
title: "&lt;webRequestModules&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<webRequestModules> (elemento)"
  - "webRequestModules (elemento)"
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;webRequestModules&gt; (Elemento, Configuraci&#243;n de red)
Especifica los módulos que se utilizan para solicitar información a hosts de la red.  
  
## Sintaxis  
  
```  
  
      <webRequestModules>   
</webRequestModules>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[agregar](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|Agrega un módulo de solicitud Web personalizado a la aplicación.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|Quita todos los módulos de solicitud Web registrados de la aplicación.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|Quita un módulo de solicitud Web personalizado de la aplicación.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene los valores de configuración que especifican cómo se conecta a la red .NET Framework.|  
  
## Comentarios  
 El elemento de `webRequestModules` registrar los descendientes de la clase de <xref:System.Net.WebRequest> para administrar solicitudes de información a los hosts de la red.  Los módulos de solicitud web deben implementar la interfaz <xref:System.Net.IWebRequestCreate>.  
  
 .NET Framework incluye módulos de solicitud Web para las direcciones URI que comienzan con http:\/\/, https:\/\/' y file:\/\/.  Sólo se pueden reemplazar aquellos módulos que sean predeterminados si se registra un módulo personalizado en el archivo de configuración.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El ejemplo de código siguiente registra el módulo HTTP predeterminado.  Deberían reemplazarse los valores de Version y PublicKeyToken con los valores correctos para el módulo especificado.  
  
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
 <xref:System.Net.IWebRequestCreate>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)