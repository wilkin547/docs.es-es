---
title: "&lt;supportedRuntime&gt; (Elemento) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<supportedRuntime> (elemento)"
  - "supportedRuntime (elemento)"
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
caps.latest.revision: 33
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 28
---
# &lt;supportedRuntime&gt; (Elemento)
Especifica qué versiones de Common Language Runtime admite la aplicación. Todas las aplicaciones compiladas con la versión 1.1 o posterior de .NET Framework deberían usar este elemento.  
  
 [\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
  
 **\<supportedRuntime\>**  
  
## Sintaxis  
  
```  
  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**version**|Atributo opcional.<br /><br /> Un valor de cadena que especifica la versión de Common Language Runtime \(CLR\) que es compatible con esta aplicación. Para conocer los valores válidos del atributo `version`, consulte la sección [Valores de "runtime version"](#version). **Note:**  A través de .NET Framework 3.5, el valor "*runtime version*" adopta la forma *major*.*minor*.*build*. A partir de [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], solo se requieren los números de versión principal y secundaria "\(es decir, "v4.0" en lugar de "v4.0.30319"\). Se recomienda la cadena más corta.|  
|**sku**|Atributo opcional.<br /><br /> Valor de cadena que especifica la referencia de almacén \(SKU\), que a su vez especifica qué versión de .NET Framework es compatible con esta aplicación.<br /><br /> A partir de .NET Framework 4.0, se recomienda el uso del atributo `sku`.  Cuando está presente, indica la versión de .NET Framework que la aplicación tiene como destino.<br /><br /> Para los valores válidos del atributo de SKU, consulte la sección [Valores de "sku id"](#sku).|  
  
## Comentarios  
 Si el elemento **\<supportedRuntime\>** no está presente en el archivo de configuración de la aplicación, se usará la versión del motor en tiempo de ejecución utilizado para compilar la aplicación.  
  
 Todas las aplicaciones compiladas con la versión 1.1 o posterior del motor en tiempo de ejecución deberían usar el elemento **\<supportedRuntime\>**. Las aplicaciones compiladas para ser compatibles únicamente con la versión 1.0 del motor en tiempo de ejecución deben usar el elemento [\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md).  
  
> [!NOTE]
>  Si utiliza la función [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) para especificar el archivo de configuración, debe utilizar el elemento `<requiredRuntime>` para todas las versiones del runtime. Se omite el elemento `<supportedRuntime>` al usar [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
 En el caso de aplicaciones que admiten versiones del runtime de .NET Framework 1.1 a través de la versión 3.5, cuando se admiten varias versiones del runtime, el primer elemento debería especificar la versión preferida y el último elemento la que se considera como última posibilidad. Para las aplicaciones compatibles con .NET Framework 4.0 o versiones posteriores, el atributo `version` indica la versión CLR, que es común para el .NET Framework 4 y versiones posteriores, y el atributo `sku` indica la única versión de .NET Framework que la aplicación tiene como destino.  
  
> [!NOTE]
>  Si la aplicación usa rutas de activación heredadas, como la [función CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que dichas rutas activen la versión 4 de CLR en lugar de una versión anterior, o si la aplicación está compilada con [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] pero tiene una dependencia en un ensamblado de modo mixto compilado con una versión anterior de .NET Framework, no es suficiente especificar [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] en la lista de aplicaciones compatibles. Además, en el [elemento \<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) del archivo de configuración, debe establecer el atributo `useLegacyV2RuntimeActivationPolicy` en `true`. Sin embargo, establecer este atributo en `true` significa que todos los componentes compilados con versiones anteriores de .NET Framework se ejecutan utilizando [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] en lugar de los runtimes con los que se compilaron.  
  
 Se recomienda probar las aplicaciones con todas las versiones de .NET Framework en las que puedan ejecutarse.  
  
<a name="version"></a>   
## Valores de "runtime version"  
 En la tabla siguiente se enumeran los valores válidos para el valor *runtime version* del atributo `version`.  
  
|Versión de .NET Framework|Atributo `version`|  
|-------------------------------|------------------------|  
|1.0|"v1.0.3705"|  
|1.1|"v1.1.4322"|  
|2.0|"v2.0.50727"|  
|3.0|"v2.0.50727"|  
|3.5|"v2.0.50727"|  
|4.0|"v4.0"|  
|4.5|"v4.0"|  
|4.5.1|"v4.0"|  
|4.5.2|"v4.0"|  
|4.6|"v4.0"|  
|4.6.1|"v4.0"|  
  
<a name="sku"></a>   
## Valores de "sku id"  
 En la tabla siguiente se enumeran las versiones de .NET Framework, a partir de .NET Framework 4, que son compatibles con el atributo `sku`.  Tenga en cuenta que el atributo `sku` a partir de .NET Framework 4 indica la versión de .NET Framework que la aplicación tiene como destino.  
  
|Versión de .NET Framework|Atributo `sku`|  
|-------------------------------|--------------------|  
|4.0|".NETFramework,Version\=v4.0"|  
|4.0, Client Profile|".NETFramework,Version\=v4.0,Profile\=Client"|  
|4.0, actualización 1 de la plataforma|.NETFramework,Version\=v4.0.1|  
|4.0, Client Profile, actualización 1|.NETFramework,Version\=v4.0.1,Profile\=Client|  
|4.0, actualización 2 de la plataforma|.NETFramework,Version\=v4.0.2|  
|4.0, Client Profile, actualización 2|.NETFramework,Version\=v4.0.2,Profile\=Client|  
|4.0, actualización 3 de la plataforma|.NETFramework,Version\=v4.0.3|  
|4.0, Client Profile, actualización 3|.NETFramework,Version\=v4.0.3,Profile\=Client|  
|4.5|".NETFramework,Version\=v4.5"|  
|4.5.1|".NETFramework,Version\=v4.5.1"|  
|4.5.2|".NETFramework,Version\=v4.5.2"|  
|4.6|".NETFramework,Version\=v4.6"|  
|4.6.1|".NETFramework,Version\=v4.6.1"|  
  
 En la tabla siguiente se muestran las versiones instaladas de .NET Framework 4 en las que se ejecutará una aplicación, para los distintos valores del atributo `sku`, cuando el atributo `version` y el atributo `sku` identifican a .NET Framework 4 o a una de sus actualizaciones de plataforma \(PU\).  
  
|Valor del atributo `sku`|4.0 Client|4.0 \(Versión completa\)|Cliente 4.0 \+ PU 1|4.0 Completa \+ PU 1|Cliente 4.0 \+ PU 2|4.0 completa \+ PU 2|Cliente 4.0 \+ PU 3|4.0 completa \+ PU 3|4.5 y versiones posteriores|  
|------------------------------|----------------|------------------------------|-------------------------|--------------------------|-------------------------|--------------------------|-------------------------|--------------------------|---------------------------------|  
|.NETFramework,Version\=v4.0,Profile\=Client|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|Sí|  
|.NETFramework,Version\=v4.0||Sí||Sí||Sí||Sí|Sí|  
|.NETFramework,Version\=v4.0.1,Profile\=Client|||Sí|Sí|Sí|Sí|Sí|Sí|Sí|  
|.NETFramework,Version\=v4.0.1||||Sí||Sí||Sí|Sí|  
|.NETFramework,Version\=v4.0.2,Profile\=Client|||||Sí|Sí|Sí|Sí|Sí|  
|.NETFramework,Version\=v4.0.2||||||Sí||Sí|Sí|  
|.NETFramework,Version\=v4.0.3,Profile\=Client|||||||Sí|Sí|Sí|  
|.NETFramework,Version\=v4.0.3||||||||Sí|Sí|  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar la versión del runtime compatible en un archivo de configuración. El archivo de configuración indica que la aplicación tiene como destino .NET Framework 4.6.  
  
```xml  
  
<configuration> <startup> <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" /> </startup> </configuration>  
  
```  
  
## Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración de la aplicación.  
  
## Vea también  
 [Esquema de la configuración de inicio](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Especificar la versión del runtime que se va a usar](http://msdn.microsoft.com/es-es/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [Ejecución en paralelo y en proceso](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)