---
title: "&lt;NetFx40_LegacySecurityPolicy&gt;(Elemento) | Microsoft Docs"
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
  - "<NetFx40_LegacySecurityPolicy> (elemento)"
  - "NetFx40_LegacySecurityPolicy (elemento)"
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;NetFx40_LegacySecurityPolicy&gt;(Elemento)
Especifica si el motor en tiempo de ejecución utiliza la directiva de seguridad de acceso del código \(CAS\) heredada.  
  
## Sintaxis  
  
```  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el motor en tiempo de ejecución utiliza la directiva de CAS heredada.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El runtime no usa la directiva de CAS heredada.  Éste es el valor predeterminado.|  
|`true`|El runtime usa la directiva de CAS heredada.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## Comentarios  
 En .NET Framework versión 3.5 y versiones anteriores, la directiva de CAS siempre está en vigor.  En [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], la directiva de CAS se debe habilitar.  
  
 La directiva de CAS es específica de la versión.  Las directivas CAS personalizadas que existen en versiones anteriores de .NET Framework se deben volver a especificar en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Al aplicar el elemento `<NetFx40_LegacySecurityPolicy>` a un ensamblado [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] no afecta al [código transparente en seguridad](../../../../../docs/framework/misc/security-transparent-code.md); las reglas de la transparencia todavía se aplican.  
  
> [!IMPORTANT]
>  Al aplicar el elemento `<NetFx40_LegacySecurityPolicy>` se pueden producir reducciones de rendimiento importantes para los ensamblados de imagen nativa creados por el [Generador de imágenes nativas \(Ngen.exe\)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) que no se instala en la [caché global de ensamblados](../../../../../docs/framework/app-domains/gac.md).  La degradación del rendimiento se produce por la incapacidad del runtime para cargar los ensamblados como imágenes nativas cuando se aplica el atributo, dando como resultado que se carguen como ensamblados Just\-In\-Time.  
  
> [!NOTE]
>  Si especifica una versión de .NET Framework de destino que es anterior a [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] en la configuración del proyecto para su proyecto de Visual Studio, la directiva CAS se habilitará, incluyendo cualquier directiva CAS personalizada que especificó para esa versión.  Sin embargo, no podrá utilizar nuevos tipos y miembros de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  También puede especificar una versión anterior de .NET Framework mediante [\<supportedRuntime\> elemento](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) en el esquema de configuración de inicio en [archivo de configuración de la aplicación](../../../../../docs/framework/configure-apps/index.md).  
  
> [!NOTE]
>  La sintaxis del archivo de configuración distingue mayúsculas y minúsculas.  Debe utilizar la sintaxis conforme a lo dispuesto en las secciones Sintaxis y Ejemplo.  
  
## Archivo de configuración  
 Este elemento sólo puede utilizarse en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo habilitar la directiva de CAS heredada para una aplicación.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)