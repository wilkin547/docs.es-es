---
title: <appDomainManagerType> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: bae4aa39f9c43480ac2ef984f78834b68646742d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118242"
---
# <a name="appdomainmanagertype-element"></a>\<elemento > appDomainManagerType
Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerType >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`value`|Atributo necesario. Especifica el nombre del tipo, incluido el espacio de nombres, que actúa como administrador del dominio de aplicación para el dominio de aplicación predeterminado en el proceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el [\<appDomainManagerAssembly >](appdomainmanagerassembly-element.md) elemento. Si no se especifica ninguno de estos elementos, se omite el otro.  
  
 Cuando se carga el dominio de aplicación predeterminado, se produce <xref:System.TypeLoadException> si el tipo especificado no existe en el ensamblado especificado por el elemento de [> de\<appDomainManagerAssembly](appdomainmanagerassembly-element.md) . y el proceso no se inicia.  
  
 Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación. Use las propiedades <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> y <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.  
  
 La especificación del tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza. (Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, se produce una <xref:System.TypeLoadException>.  
  
 El formato del tipo y el espacio de nombres es el mismo formato que se utiliza para la propiedad <xref:System.Type.FullName%2A?displayProperty=nameWithType>.  
  
 Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que el administrador del dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el tipo de `MyMgr` del ensamblado `AdMgrExample`.  
  
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
- [\<elemento > appDomainManagerAssembly](appdomainmanagerassembly-element.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [SetAppDomainManagerType (método)](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
