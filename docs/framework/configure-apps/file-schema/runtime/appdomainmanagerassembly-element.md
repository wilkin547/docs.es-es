---
title: <appDomainManagerAssembly> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff8c91680a0c3049fa9bc2f7e9c1bf3f654a19b9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487771"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerAssembly > elemento
Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.  
  
 \<configuration>  
\<runtime>  
\<appDomainManagerAssembly>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`value`|Atributo necesario. Especifica el nombre para mostrar del ensamblado que proporciona el administrador del dominio para el dominio de aplicación predeterminado en el proceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) elemento. Si no se especifica cualquiera de estos elementos, se omite el resto.  
  
 Cuando se carga el dominio de aplicación predeterminado, <xref:System.TypeLoadException> se produce si el ensamblado especificado no existe o si el ensamblado no contiene el tipo especificado por el [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) elemento; y no se puede iniciar el proceso. Si se encuentra el ensamblado, pero no coincide con la información de versión, un <xref:System.IO.FileLoadException> se produce.  
  
 Cuando se especifica el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación. Use la <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> y <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.  
  
 Especifica el tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza. (Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, un <xref:System.TypeLoadException> se produce.  
  
 Para el formato del nombre para mostrar del ensamblado, vea el <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> propiedad.  
  
 Este elemento de configuración está disponible solo en .NET Framework 4 y versiones posteriores.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo especificar que el Administrador de dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el `MyMgr` escriba en el `AdMgrExample` ensamblado.  
  
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
- [\<appDomainManagerType > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [SetAppDomainManagerType (método)](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
