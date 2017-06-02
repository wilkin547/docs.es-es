---
title: "&lt;disableFusionUpdatesFromADManager&gt;(Elemento) | Microsoft Docs"
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
  - "<disableFusionUpdatesFromADManager> (elemento)"
  - "disableFusionUpdatesFromADManager (elemento)"
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;disableFusionUpdatesFromADManager&gt;(Elemento)
Especifica si el comportamiento predeterminado, que es permitir que el host en tiempo de ejecución invalide la configuración para un dominio de aplicación, está deshabilitado.  
  
## Sintaxis  
  
```  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si la capacidad predeterminada de invalidar la configuración de Fusión está deshabilitada.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|No deshabilitar la capacidad de invalidar la configuración de Fusión.  Este es el comportamiento predeterminado a partir de [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
|1|Deshabilitar la capacidad de invalidar la configuración de Fusión.  Esto revierte al comportamiento de versiones anteriores de .NET Framework.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 A partir de [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], el comportamiento predeterminado es permitir que el objeto <xref:System.AppDomainManager> invalide la configuración usando la propiedad <xref:System.AppDomainSetup.ConfigurationFile%2A> o el método <xref:System.AppDomainSetup.SetConfigurationBytes%2A> del objeto <xref:System.AppDomainSetup> que se pasa a su implementación del método <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName>, en su subclase de <xref:System.AppDomainManager>.  Para el dominio de aplicación predeterminado, la configuración que cambia invalida la configuración especificada por el archivo de configuración de la aplicación.  Para otros dominios de aplicación, invalidan la configuración que se pasó al método <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName> o <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName>.  
  
 Puede pasar la nueva información de configuración o pasar null \(`Nothing` en Visual Basic\) para eliminar la información de configuración que se pasó.  
  
 No pase información de configuración a la propiedad <xref:System.AppDomainSetup.ConfigurationFile%2A> y al método <xref:System.AppDomainSetup.SetConfigurationBytes%2A>.  Si pasa información de configuración a ambos, se pasará por alto la información que pasa a la propiedad <xref:System.AppDomainSetup.ConfigurationFile%2A>, ya que el método <xref:System.AppDomainSetup.SetConfigurationBytes%2A> invalida la información de configuración del archivo de configuración de la aplicación.  Si usa la propiedad <xref:System.AppDomainSetup.ConfigurationFile%2A>, puede pasar null \(`Nothing` en Visual Basic\) al método <xref:System.AppDomainSetup.SetConfigurationBytes%2A> para eliminar cualquier byte de configuración que se especificara en la llamada al método <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName> o <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName>.  
  
 Además de información de configuración, puede cambiar la configuración siguiente en el objeto <xref:System.AppDomainSetup> pasado a su implementación del método <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName>: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> y <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Como alternativa al uso del elemento `<disableFusionUpdatesFromADManager>`, puede deshabilitar el comportamiento predeterminado creando un valor del Registro o estableciendo una variable de entorno.  En el Registro, cree un valor DWORD denominado `COMPLUS_disableFusionUpdatesFromADManager` bajo `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`, y establezca el valor en 1.  En la línea de comandos, establezca la variable de entorno `COMPLUS_disableFusionUpdatesFromADManager` en 1.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo deshabilitar la capacidad de invalidar la configuración de Fusión usando el elemento `<disableFusionUpdatesFromADManager>`.  
  
```  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)