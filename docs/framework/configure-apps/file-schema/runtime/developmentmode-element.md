---
title: "Elemento &lt;developmentMode&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<developmentMode> (elemento)"
  - "etiquetas contenedoras, <developmentMode> (elemento)"
  - "developmentMode (elemento)"
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Elemento &lt;developmentMode&gt;
Especifica si el motor de ejecución busca los ensamblados en los directorios especificados en la variable de entorno DEVPATH.  
  
## Sintaxis  
  
```  
<developmentMode developerInstallation="true | false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**developerInstallation**|Especifica si el motor de ejecución busca los ensamblados en los directorios especificados en la variable de entorno DEVPATH.|  
  
## Atributo DeveloperInstallation  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**true**|Busca los ensamblados en los directorios especificados en la variable de entorno DEVPATH.|  
|**false**|No busca los ensamblados en los directorios especificados en la variable de entorno DEVPATH.  Éste es el valor predeterminado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Utilice esta configuración sólo durante el proceso de desarrollo.  El motor en tiempo de ejecución no comprueba la versión de los ensamblados con nombre seguro que se encuentran en la variable DEVPATH.  Simplemente utiliza el primer ensamblado que encuentra.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo se consigue que el motor en tiempo de ejecución busque ensamblados en los directorios que especifica la variable de entorno DEVPATH.  
  
```  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Cómo: Buscar ensamblados mediante DEVPATH](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)