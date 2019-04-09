---
title: <disableFusionUpdatesFromADManager> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c8c1cac68aca1c40826ff549d62d9636d9b0c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085888"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager > elemento
Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.  
  
 \<Configuración > elemento  
\<en tiempo de ejecución > elemento  
\<disableFusionUpdatesFromADManager>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se deshabilita la capacidad predeterminada para invalidar la configuración de fusión.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|No deshabilite la capacidad de invalidar la configuración de fusión. Este es el comportamiento predeterminado, empezando por el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
|1|Deshabilitar la capacidad de invalidar la configuración de fusión. Esto revierte el comportamiento de versiones anteriores de .NET Framework.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], el comportamiento predeterminado es permitir la <xref:System.AppDomainManager> objeto invaliden los valores de configuración mediante el <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad o el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método de la <xref:System.AppDomainSetup> objeto que se pasa a la implementación de la <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método en la subclase de <xref:System.AppDomainManager>. Para el dominio de aplicación predeterminado, la configuración que cambia invalida la configuración que se ha especificado por el archivo de configuración de la aplicación. Para otros dominios de aplicación, invalidan los valores de configuración que se pasaron a la <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método.  
  
 Puede pasar nueva información de configuración, o pasar un valor null (`Nothing` en Visual Basic) para eliminar información de configuración que se pasó.  
  
 No pase información de configuración a ambos el <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad y el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método. Si se pasa la información de configuración a ambos, la información se pasa a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad se omite porque el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método invalida la información de configuración del archivo de configuración de la aplicación. Si usas el <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad, puede pasar null (`Nothing` en Visual Basic) para el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método para eliminar los bytes de la configuración que se especificaron en la llamada a la <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método.  
  
 Además de información de configuración, puede cambiar la configuración siguiente en el <xref:System.AppDomainSetup> objeto que se pasa a la implementación de la <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, y <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Como alternativa al uso de la `<disableFusionUpdatesFromADManager>` elemento, puede deshabilitar el comportamiento predeterminado mediante la creación de una configuración del registro o estableciendo una variable de entorno. En el registro, cree un valor DWORD denominado `COMPLUS_disableFusionUpdatesFromADManager` en `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`y establezca el valor en 1. En la línea de comandos, establezca la variable de entorno `COMPLUS_disableFusionUpdatesFromADManager` en 1.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo deshabilitar la capacidad de invalidar la configuración de fusión mediante el `<disableFusionUpdatesFromADManager>` elemento.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
