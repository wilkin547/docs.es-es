---
title: "&lt;legacyCorruptedStateExceptionsPolicy&gt; (Elemento) | Microsoft Docs"
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
  - "<legacyCorruptedStateExceptionsPolicy> (elemento)"
  - "legacyCorruptedStateExceptionsPolicy (elemento)"
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;legacyCorruptedStateExceptionsPolicy&gt; (Elemento)
Especifica si Common Language Runtime permite al código administrado detectar infracciones de acceso y otras excepciones que indican un estado dañado.  
  
## Sintaxis  
  
```  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica que la aplicación detectará errores de excepción de estado dañado como infracciones de acceso.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|La aplicación no detectará errores de excepción de estado dañado como infracciones de acceso.  Éste es el valor predeterminado.|  
|`true`|La aplicación detectará errores de excepción de estado dañado como infracciones de acceso.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 En .NET Framework versión 3.5 y versiones anteriores, Common Language Runtime permitía que el código administrado detectara excepciones producidas por estados de procesos dañados.  Una infracción de acceso es un ejemplo de este tipo de excepción.  
  
 A partir de [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], el código administrado ya no detecta estos tipos de excepciones en bloques `catch`.  Sin embargo, hay dos formas de invalidar este cambio y mantener el control de las excepciones de estado dañado:  
  
-   Establecer el atributo `enabled` del elemento `<legacyCorruptedStateExceptionsPolicy>` en `true`.  Este valor de configuración se aplica a todo el proceso y afecta a todos los métodos.  
  
 O bien  
  
-   Aplicar el atributo <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName> al método que contiene el bloque `catch` de las excepciones.  
  
 Este elemento de configuración solo está disponible en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y en versiones posteriores.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que la aplicación debe revertir al comportamiento anterior a [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y detectar todos los errores de excepción de estados dañados.  
  
```  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>   
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)