---
title: "Elemento &lt;configuration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<configuration> (elemento)"
  - "configuration (elemento)"
  - "etiquetas contenedoras, <configuration> (elemento)"
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Elemento &lt;configuration&gt;
Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.  
  
 **\<configuration\>**  
  
## Sintaxis  
  
```  
  
      <configuration>   
   <!-- configuration settings -->   
</configuration>  
```  
  
## Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<assemblyBinding\> \(elemento\)](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|Especifica la directiva de enlace del ensamblado en el nivel de configuración.|  
|[Esquema de la configuración de inicio](../../../../docs/framework/configure-apps/file-schema/startup/index.md)|Todos los elementos del esquema de la configuración de inicio.|  
|[Esquema de la configuración de Common Language Runtime](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)|Todos los elementos del esquema de la configuración del motor de ejecución.|  
|[Esquema de la configuración de la comunicación remota](http://msdn.microsoft.com/es-es/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)|Todos los elementos del esquema de la comunicación remota.|  
|[Esquema de la configuración de red](../../../../docs/framework/configure-apps/file-schema/network/index.md)|Todos los elementos del esquema de la configuración de red.|  
|[Esquema de la configuración de criptografía](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)|Todos los elementos del esquema de la configuración criptográfica.|  
|[Esquema de secciones de configuración](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)|Todos los elementos del esquema de la configuración de secciones de configuración.|  
|[Esquema de la configuración de traza y depuración](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)|Todos los elementos del esquema de la configuración de seguimiento y depuración.|  
|[Esquema de configuración de ASP.NET](http://msdn.microsoft.com/es-es/116608f3-c03d-4413-9fc7-978703e18b0f)|Todos los elementos del esquema de configuración ASP.NET, que incluye elementos para configurar aplicaciones y sitios web ASP.NET.  Se usa en los archivos Web.config.|  
|[Esquema de configuración de los servicios Web XML](http://msdn.microsoft.com/es-es/f84d6d55-1add-4eb7-ae46-33df5833ea2e)|Todos los elementos del esquema de los servicios Web.|  
|[Esquema de configuración web](../../../../docs/framework/configure-apps/file-schema/web/index.md)|Describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.  Se usa en los archivos aspnet.config.|  
  
## Comentarios  
 Cada archivo de configuración debe contener exactamente un elemento de **\<configuración\>** .  
  
## Vea también  
 [Esquema de los archivos de configuración](../../../../docs/framework/configure-apps/file-schema/index.md)