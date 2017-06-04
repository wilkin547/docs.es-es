---
title: "&lt;shadowCopyVerifyByTimestamp&gt; (Elemento) | Microsoft Docs"
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
  - "<shadowCopyTimeStampVerification> (elemento)"
  - "shadowCopyTimeStampVerification (elemento)"
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;shadowCopyVerifyByTimestamp&gt; (Elemento)
Especifica si la instantánea usa el comportamiento de inicio predeterminado introducido en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], o revierte al comportamiento de inicio de las versiones anteriores de .NET Framework.  
  
## Sintaxis  
  
```  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si los dominios de aplicación que utilizan la instantánea comparan las marcas de tiempo del ensamblado en el inicio, para determinar si un ensamblado se ha actualizado antes de la instantánea del ensamblado.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|En el inicio, solo copia ensamblados que se han actualizado desde que se copiaron la última vez en el directorio de instantánea.  Este es el valor predeterminado de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].|  
|false|Revierte al comportamiento de inicio de las versiones anteriores de .NET Framework, que era copiar todos los archivos en el inicio.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Desde [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], solo se copia una instantánea de los ensamblados si sus marcas de tiempo indican que han cambiado desde que se copiaron la última vez en el directorio de instantánea.  Esto mejora los tiempos de inicio de muchas aplicaciones que utilizan instantáneas, tal y como se describe en [Copias sombra de ensamblados](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).  Las aplicaciones que tienen un alto porcentaje y frecuencia de actualizaciones del ensamblado no podrían beneficiarse de este cambio de comportamiento.  En ese caso, puede utilizar este elemento para restaurar el comportamiento de las versiones anteriores de .NET Framework.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo deshabilitar el comportamiento de inicio predeterminado de la instantánea en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], y revertir al comportamiento de inicio de las versiones anteriores de .NET Framework.  
  
```  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Copias sombra de ensamblados](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)