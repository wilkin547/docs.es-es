---
title: "&lt;appDomainManagerAssembly&gt; (Elemento) | Microsoft Docs"
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
  - "<appDomainManagerAssembly> (elemento)"
  - "appDomainManagerAssembly (elemento)"
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;appDomainManagerAssembly&gt; (Elemento)
Especifica el ensamblado que proporciona el administrador del dominio de aplicación predeterminado en el proceso.  
  
## Sintaxis  
  
```  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`value`|Atributo necesario.  Especifica el nombre para mostrar del ensamblado que proporciona el administrador del dominio de aplicación predeterminado en el proceso.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Para especificar el tipo de administrador de dominio de aplicación, debe especificar este elemento y el elemento de [\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) .  Si no se especifica alguno de estos elementos, el otro se pasa por alto.  
  
 Cuando el dominio de aplicación predeterminado cargado, se produce <xref:System.TypeLoadException> si no existe el ensamblado especificado o si el ensamblado no contiene el tipo especificado por el elemento de [\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) ; y el proceso no se inicia.  Si el ensamblado se encuentra pero la información de versión no coincide, se produce <xref:System.IO.FileLoadException>.  
  
 Cuando especifica el tipo de administrador del dominio de aplicación predeterminado, otros dominios de aplicación creados a partir del dominio de aplicación predeterminado heredan dicho tipo.  Use las propiedades <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=fullName> y <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=fullName> para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.  
  
 Para poder especificar el tipo de administrador de dominio de aplicación, la aplicación debe ser de plena confianza. \(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza.\) Si la aplicación no tiene plena confianza, se produce <xref:System.TypeLoadException>.  
  
 Para conocer el formato del nombre para mostrar de un ensamblado, vea <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName>.  
  
 Este elemento de configuración solo está disponible en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y en versiones posteriores.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que el administrador del dominio de aplicación predeterminado de un proceso es del tipo `MyMgr` en el ensamblado `AdMgrExample`.  
  
```  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=fullName>   
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=fullName>   
 [\<appDomainManagerType\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)   
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [SetAppDomainManagerType \(Método\)](../Topic/ICLRControl::SetAppDomainManagerType%20Method.md)