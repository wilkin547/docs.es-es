---
title: <appDomainManagerAssembly> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a293af73fde5ee72ba02c7e6613e9c57eae1b9b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658946"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerAssembly >, elemento
Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.  
  
 \<configuration>  
\<> en tiempo de ejecución  
\<appDomainManagerAssembly>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`value`|Atributo necesario. Especifica el nombre para mostrar del ensamblado que proporciona el administrador del dominio de aplicación para el dominio de aplicación predeterminado en el proceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el elemento [ \<> de appDomainManagerType](appdomainmanagertype-element.md) . Si no se especifica ninguno de estos elementos, se omite el otro.  
  
 Cuando se carga el dominio de aplicación predeterminado <xref:System.TypeLoadException> , se produce si el ensamblado especificado no existe o si el ensamblado no contiene el tipo especificado por el [ \<elemento > appDomainManagerType](appdomainmanagertype-element.md) ; y se produce un error en el proceso. iniciales. Si se encuentra el ensamblado pero la información de la versión no coincide <xref:System.IO.FileLoadException> , se produce una excepción.  
  
 Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación. Use las <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> propiedades <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> y para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.  
  
 La especificación del tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza. (Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, se produce <xref:System.TypeLoadException> una excepción.  
  
 Para obtener el formato del nombre para mostrar del ensamblado <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> , vea la propiedad.  
  
 Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que el administrador del dominio de aplicación para el dominio de aplicación predeterminado de `MyMgr` un proceso es el tipo del ensamblado.`AdMgrExample`  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<appDomainManagerType >, elemento](appdomainmanagertype-element.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [SetAppDomainManagerType (método)](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
