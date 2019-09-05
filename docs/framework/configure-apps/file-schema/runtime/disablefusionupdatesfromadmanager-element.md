---
title: <disableFusionUpdatesFromADManager> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b65711ad8c404d1c4f54a6197faf598e2215226f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252648"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager >, elemento
Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si está deshabilitada la capacidad predeterminada de invalidar la configuración de fusión.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|0|No deshabilite la capacidad de invalidar la configuración de fusión. Este es el comportamiento predeterminado, comenzando por el .NET Framework 4.|  
|1|Deshabilitar la capacidad de invalidar la configuración de fusión. Esto revierte el comportamiento de las versiones anteriores del .NET Framework.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la .NET Framework 4, el comportamiento predeterminado es permitir que <xref:System.AppDomainManager> el objeto invalide los valores de <xref:System.AppDomainSetup.ConfigurationFile%2A> configuración mediante la <xref:System.AppDomainSetup.SetConfigurationBytes%2A> propiedad <xref:System.AppDomainSetup> o el método del objeto que se pasa a la implementación. del método, en la subclase de <xref:System.AppDomainManager>. <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> En el caso del dominio de aplicación predeterminado, la configuración que cambie invalida la configuración especificada por el archivo de configuración de la aplicación. En otros dominios de aplicación, invalidan las opciones de configuración que se <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> pasaron <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> al método o.  
  
 Puede pasar información de configuración nueva o pasar un valor null (`Nothing` en Visual Basic) para eliminar la información de configuración que se ha pasado.  
  
 No pase información de configuración a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad y al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método. Si se pasa información de configuración a ambos, se omite la información que <xref:System.AppDomainSetup.ConfigurationFile%2A> se pasa a la propiedad, <xref:System.AppDomainSetup.SetConfigurationBytes%2A> porque el método reemplaza la información de configuración del archivo de configuración de la aplicación. <xref:System.AppDomainSetup.ConfigurationFile%2A> Si usa la propiedad, puede pasar null ( <xref:System.AppDomainSetup.SetConfigurationBytes%2A> `Nothing` en Visual Basic) al método para eliminar los bytes de configuración especificados en la llamada al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> método o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .  
  
 Además de la información de configuración, puede cambiar la configuración siguiente en el <xref:System.AppDomainSetup> objeto que se pasa a la implementación <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> del método: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>,, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, ,,<xref:System.AppDomainSetup.LoaderOptimization%2A>,, y<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.ShadowCopyFiles%2A>  
  
 Como alternativa al uso del elemento `<disableFusionUpdatesFromADManager>` , puede deshabilitar el comportamiento predeterminado mediante la creación de una configuración del registro o mediante el establecimiento de una variable de entorno. En el registro, cree un valor DWORD denominado `COMPLUS_disableFusionUpdatesFromADManager` en `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`y establezca el valor en 1. En la línea de comandos, establezca la variable `COMPLUS_disableFusionUpdatesFromADManager` de entorno en 1.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo deshabilitar la capacidad de invalidar la configuración `<disableFusionUpdatesFromADManager>` de fusión mediante el elemento.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md)
