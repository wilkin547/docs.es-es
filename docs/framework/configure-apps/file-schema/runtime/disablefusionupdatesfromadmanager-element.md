---
title: <disableFusionUpdatesFromADManager> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: c3971379b358ae16fc463df2b8d6288cf8881391
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205040"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager> (Elemento)

Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si está deshabilitada la capacidad predeterminada de invalidar la configuración de fusión.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|0|No deshabilite la capacidad de invalidar la configuración de fusión. Este es el comportamiento predeterminado, comenzando por el .NET Framework 4.|  
|1|Deshabilitar la capacidad de invalidar la configuración de fusión. Esto revierte el comportamiento de las versiones anteriores del .NET Framework.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  

 A partir de la .NET Framework 4, el comportamiento predeterminado es permitir que el <xref:System.AppDomainManager> objeto invalide los valores de configuración mediante la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad o el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método del <xref:System.AppDomainSetup> objeto que se pasa a la implementación del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método, en la subclase de <xref:System.AppDomainManager> . En el caso del dominio de aplicación predeterminado, la configuración que cambie invalida la configuración especificada por el archivo de configuración de la aplicación. En otros dominios de aplicación, invalidan las opciones de configuración que se pasaron al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método o.  
  
 Puede pasar información de configuración nueva o pasar un valor null ( `Nothing` en Visual Basic) para eliminar la información de configuración que se ha pasado.  
  
 No pase información de configuración a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad y al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método. Si se pasa información de configuración a ambos, se omite la información que se pasa a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad, porque el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método reemplaza la información de configuración del archivo de configuración de la aplicación. Si usa la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad, puede pasar null ( `Nothing` en Visual Basic) al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método para eliminar los bytes de configuración especificados en la llamada al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método o.  
  
 Además de la información de configuración, puede cambiar la configuración siguiente en el <xref:System.AppDomainSetup> objeto que se pasa a la implementación del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método: <xref:System.AppDomainSetup.ApplicationBase%2A> , <xref:System.AppDomainSetup.ApplicationName%2A> , <xref:System.AppDomainSetup.CachePath%2A> , <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A> , <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> , <xref:System.AppDomainSetup.DynamicBase%2A> , <xref:System.AppDomainSetup.LoaderOptimization%2A> , <xref:System.AppDomainSetup.PrivateBinPath%2A> , <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> , <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> y <xref:System.AppDomainSetup.ShadowCopyFiles%2A> .  
  
 Como alternativa al uso del `<disableFusionUpdatesFromADManager>` elemento, puede deshabilitar el comportamiento predeterminado mediante la creación de una configuración del registro o mediante el establecimiento de una variable de entorno. En el registro, cree un valor DWORD denominado `COMPLUS_disableFusionUpdatesFromADManager` en `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework` y establezca el valor en 1. En la línea de comandos, establezca la variable de entorno `COMPLUS_disableFusionUpdatesFromADManager` en 1.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo deshabilitar la capacidad de invalidar la configuración de fusión mediante el `<disableFusionUpdatesFromADManager>` elemento.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md)
