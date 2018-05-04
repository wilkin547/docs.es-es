---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cac4ebb46fabad49e2e4e6a7d566522ca027094
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a>&lt;PreferComInsteadOfManagedRemoting&gt; elemento
Especifica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de comunicación remota para todas las llamadas a través de los límites del dominio de aplicación.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<PreferComInsteadOfManagedRemoting >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El runtime usará comunicación remota entre límites de dominio de aplicación. Este es el valor predeterminado.|  
|`true`|El tiempo de ejecución usará interoperabilidad COM en los límites del dominio de aplicación.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Al establecer el `enabled` atribuir a `true`, el tiempo de ejecución se comporta como sigue:  
  
-   El runtime no llama a [IUnknown:: QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) para un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz cuando una [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interfaz entra en el dominio a través de una interfaz COM. En su lugar, construye un [contenedor RCW](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) alrededor del objeto.  
  
-   El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe un `QueryInterface` prevén un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz para cualquier [contenedor CCW](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) que se ha creado en este dominio.  
  
 Estos dos comportamientos garantizan que todas las llamadas a través de COM interfaces entre objetos administrados a través del uso de los límites del dominio de aplicación COM y la interoperabilidad COM en lugar de comunicación remota.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que el tiempo de ejecución debe utilizar COM interoperabilidad en los límites de aislamiento:  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
