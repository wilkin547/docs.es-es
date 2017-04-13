---
title: "&lt;NetFx40_PInvokeStackResilience&gt; (Elemento) | Microsoft Docs"
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
  - "<NetFx40_PInvokeStackResilience> (elemento)"
  - "NetFx40_PInvokeStackResilience (elemento)"
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;NetFx40_PInvokeStackResilience&gt; (Elemento)
Especifica si el runtime corrige automáticamente en tiempo de ejecución las declaraciones de invocación de plataforma incorrectas, a costa de transiciones más lentas entre código administrado y no administrado.  
  
## Sintaxis  
  
```  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime detecta las declaraciones de la invocación de plataforma incorrectas y corrige la pila automáticamente en tiempo de ejecución en plataformas de 32 bits.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`0`|El runtime usa la arquitectura del cálculo de referencias de interoperabilidad más rápida incluida en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], que no detecta ni corrige las declaraciones de invocación de plataforma incorrectas.  Éste es el valor predeterminado.|  
|`1`|El runtime usa transiciones más lentas que detectan y corrigen declaraciones de invocación de plataforma incorrectas.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## Comentarios  
 Este elemento le permite intercambiar el cálculo de referencias de interoperabilidad más rápidamente para mayor resistencia en tiempo de ejecución contra las declaraciones de invocación de plataforma incorrectas.  
  
 A partir de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], una arquitectura del cálculo de referencias de interoperabilidad simplificada proporciona una mejora de rendimiento significativa para las transiciones del código administrado al código no administrado.  En versiones anteriores de .NET Framework, el nivel de cálculo de referencias detectó declaraciones de invocación de plataforma incorrectas en plataformas de 32 bits y automáticamente fija la pila.  La nueva arquitectura de cálculo de referencias elimina este paso.  Como resultado, las transiciones son muy rápidas, pero una declaración de la invocación de plataforma incorrecta puede producir un error del programa.  
  
 Para facilitar la tarea de detectar declaraciones incorrectas durante desarrollo, se ha mejorado la experiencia de depuración de Visual Studio.  El asistente para la depuración administrada \(MDA\) [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) notifica las declaraciones de invocación de plataforma incorrectas cuando su aplicación se está ejecutando con el depurador adjunto.  
  
 Para resolver aquellos escenarios en donde la aplicación utiliza componentes que no se pueden volver a compilar, y presentan declaraciones de invocación de plataforma incorrectas, puede utilizar el elemento `NetFx40_PInvokeStackResilience`.  Al agregar este elemento al archivo de configuración de la aplicación con `enabled="1"` se opta en un modo de compatibilidad con el comportamiento de versiones anteriores de .NET Framework, a costa de las transiciones más lentas.  Los ensamblados que se han compilado basándose en versiones anteriores del .NET Framework eligen automáticamente este modo de compatibilidad y no necesitan este elemento.  
  
## Archivo de configuración  
 Este elemento sólo puede utilizarse en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo optar a una mayor resistencia contra las declaraciones de invocación de plataforma incorrectas para una aplicación, a costa de transiciones más lentas entre código administrado y no administrado.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)