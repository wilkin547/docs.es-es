---
title: "&lt;PreferComInsteadOfManagedRemoting&gt;(Elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<PreferComInsteadOfManagedRemoting> (elemento)"
  - "PreferComInsteadOfManagedRemoting (elemento)"
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# &lt;PreferComInsteadOfManagedRemoting&gt;(Elemento)
Especifica si el runtime usará interoperabilidad COM en lugar de comunicación remota para todas las llamadas entre límites de dominio de aplicación.  
  
## Sintaxis  
  
```  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si el runtime usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El runtime usará comunicación remota entre límites de dominio de aplicación.  Éste es el valor predeterminado.|  
|`true`|El runtime usará interoperabilidad COM entre límites de dominio de aplicación.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Cuando establece el atributo `enabled` en `true`, el runtime se comporta de la manera siguiente:  
  
-   El runtime no [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) pide una interfaz de [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md) cuando [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) una interfaz entra en el dominio mediante una interfaz COM.  En su lugar, construye un contenedor RCW \([Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md)\) alrededor del objeto.  
  
-   El runtime devuelve E\_NOINTERFACE cuando recibe una llamada `QueryInterface` para una interfaz [IManagedObject](../../../../../ocs/framework/unmanaged-api/hosting/imanagedobject-interface.md) para cualquier contenedor CCW \([COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md)\) creado en este dominio.  
  
 Estos dos comportamientos garantizan que todas las llamadas a través de interfaces COM entre objetos administrados entre los límites de dominio de aplicación usan COM e interoperabilidad COM en lugar de comunicación remota.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que el runtime debe usar interoperabilidad COM entre los límites de aislamiento:  
  
```  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)