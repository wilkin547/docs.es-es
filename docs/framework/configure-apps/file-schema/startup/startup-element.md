---
title: "Elemento &lt;startup&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#startup"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<startup> (elemento)"
  - "etiquetas contenedoras, <startup> (elemento)"
  - "startup (elemento)"
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# Elemento &lt;startup&gt;
Especifica información de inicio de Common Language Runtime.  
  
## Sintaxis  
  
```  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|Atributo opcional.<br /><br /> Especifica si se debe habilitar la directiva de activación del runtime [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] o se debe usar la directiva de activación [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
## useLegacyV2RuntimeActivationPolicy \(Atributo\)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Habilite la directiva de activación del runtime de [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] para el runtime elegido, que es enlazar las técnicas de activación del runtime heredado \(como la función [CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)\) al runtime elegido desde el archivo de configuración en lugar de completarlas en la versión 2.0 de CLR.  Por lo tanto, si se elije CLR versión 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores de la.NET Framework se cargarán con la versión de CLR elegida.  Este valor impide que la versión 1.1 o 2.0 de CLR se cargue en el mismo proceso, deshabilitando la característica en paralelo en curso.|  
|`false`|Use la directiva de activación predeterminada de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y posterior, que consiste en permitir que las técnicas de activación del runtime heredado carguen la versión 1.1 o 2.0 de CLR en el proceso.  Establecer este valor evita los ensamblados de modo mixto de carga en .NET Framework 4 o posterior a menos que los compilaran con .NET Framework 4 o posterior.  Este valor es el predeterminado.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Especifica que la aplicación sólo es compatible con la versión 1.0 de Common Language Runtime.  Las aplicaciones compiladas con la versión 1.1 o posterior deben utilizar el elemento de **\<supportedRuntime\>** .|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Especifica qué versiones de Common Language Runtime admite la aplicación.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## Comentarios  
 Todas las aplicaciones compiladas con la versión 1.1 o posterior del motor en tiempo de ejecución deberían usar el elemento **\<supportedRuntime\>**.  Las aplicaciones compiladas para ser compatibles únicamente con la versión 1.0 del motor en tiempo de ejecución deben usar el elemento **\<requiredRuntime\>**.  
  
 El código de inicio para una aplicación hospedada en Microsoft Internet Explorer omite el elemento de **\<startup\>** y sus elementos secundarios.  
  
## El atributo UseLegacyV2RuntimeActivationPolicy  
 Este atributo resulta útil si su aplicación utiliza rutas de activación heredadas, como la [función CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que las rutas activen la versión 4 de CLR en lugar de una versión anterior, o si su aplicación está compilada con [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] pero tiene una dependencia en un ensamblado de modo mixto creado con una versión anterior de .NET Framework.  En esos escenarios, establezca el atributo en `true`.  
  
> [!NOTE]
>  Establecer el atributo en `true` impide que la versión 1.1 o 2.0 de CLR se cargue en el mismo proceso, deshabilitando la característica en paralelo en curso \(vea [Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/es-es/4302318c-3586-49bf-8620-b9a39cdf4a32)\).  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo especificar la versión del motor de ejecución en un archivo de configuración.  
  
```  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de inicio](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/es-es/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/es-es/4302318c-3586-49bf-8620-b9a39cdf4a32)   
 [Ejecución en paralelo y en proceso](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)