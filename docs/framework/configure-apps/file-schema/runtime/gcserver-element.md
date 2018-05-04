---
title: '&lt;gcServer&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027176bdff644a6ff3314df7484ed88ace93001b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltgcservergt-element"></a>&lt;gcServer&gt; elemento
Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<gcServer >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de servidor.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No ejecuta la recolección de elementos no utilizados de servidor. Este es el valor predeterminado.|  
|`true`|Ejecuta la recolección de elementos no utilizados de servidor.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Common Language Runtime (CLR) admite dos tipos de recolección de elementos no utilizados: de estación de trabajo, que está disponible en todos los sistemas, y de servidor, que está disponible en sistemas multiprocesador. El elemento `<gcServer>` se usa para controlar el tipo de recolección de elementos no utilizados que CLR realiza. Use la propiedad <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> para determinar si la recolección de elementos no utilizados de servidor está habilitada.  
  
 Para equipos con un solo procesador, la recolección de elementos no utilizados de estación de trabajo predeterminada será la opción más rápida. En los equipos con dos procesadores se puede usar la opción de estación de trabajo o de servidor. La recolección de elementos no utilizados de servidor será la opción más rápida si hay más de dos procesadores.  
  
 Este elemento se puede usar solo en el archivo de configuración de la aplicación; se omite si se encuentra en el archivo de configuración del equipo.  
  
> [!NOTE]
>  En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados simultánea no está disponible si la recolección de elementos no utilizados de servidor está habilitada. A partir de [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], la recolección de elementos no utilizados de servidor es simultánea. Para usar la recolección de elementos no utilizados de servidor no simultánea, establezca el `<gcServer>` elemento `true` y [ \<gcConcurrent > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) a `false`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se habilita la recolección de elementos no utilizados de servidor.  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cómo: deshabilitar la recolección de elementos no utilizados simultánea](http://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)
