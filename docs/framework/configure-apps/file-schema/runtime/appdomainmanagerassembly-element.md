---
title: <appDomainManagerAssembly> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154437"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerAssembly> Element
Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**  
  
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
|`value`|Atributo necesario. Especifica el nombre para mostrar del ensamblado que proporciona el administrador de dominio de aplicación para el dominio de aplicación predeterminado en el proceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  
 Para especificar el tipo del administrador de dominio de aplicación, debe especificar este elemento y el [ \<elemento de>appDomainManagerType.](appdomainmanagertype-element.md) Si no se especifica ninguno de estos elementos, se omite el otro.  
  
 Cuando se carga el <xref:System.TypeLoadException> dominio de aplicación predeterminado, se produce si el ensamblado especificado no existe o si el ensamblado no contiene el tipo especificado por el [ \<elemento de>appDomainManagerType;](appdomainmanagertype-element.md) y el proceso no se inicia. Si se encuentra el ensamblado pero la <xref:System.IO.FileLoadException> información de versión no coincide, se produce un.  
  
 Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados a partir del dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación. Use <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> las <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades y para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.  
  
 Especificar el tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza. (Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza.) Si la aplicación no tiene <xref:System.TypeLoadException> plena confianza, se produce un.  
  
 Para conocer el formato del nombre <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> para mostrar del ensamblado, consulte la propiedad.  
  
 Este elemento de configuración solo está disponible en .NET Framework 4 y versiones posteriores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que el administrador `MyMgr` de dominio `AdMgrExample` de aplicación para el dominio de aplicación predeterminado de un proceso es el tipo en el ensamblado.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<elemento de> appDomainManagerType](appdomainmanagertype-element.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
- [Método SetAppDomainManagerType](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
