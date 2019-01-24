---
title: '&lt;gcConcurrent&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c83576c5c46d9a32f990d23fa20b116be36e4c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612003"
---
# <a name="ltgcconcurrentgt-element"></a>&lt;gcConcurrent&gt; elemento
Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados en un subproceso independiente.  
  
 \<configuration>  
\<runtime>  
\<gcConcurrent>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No ejecuta la recolección de elementos no utilizados simultáneamente.|  
|`true`|Ejecuta la recolección de elementos no utilizados simultáneamente. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Antes de .NET Framework 4, la recolección de elementos no utilizados de estación de trabajo permitía la recolección de elementos no utilizados  simultánea, que se realizaba en segundo plano en un subproceso independiente. En .NET Framework 4, la recolección de elementos no utilizados simultánea se reemplazó por GC, que también realiza la recolección de elementos no utilizados en segundo plano en un subproceso independiente. A partir de .NET Framework 4.5, la recolección de elementos no utilizados de servidor se puede realizar en segundo plano. El elemento `<gcConcurrent>` controla si CLR realiza la recolección de elementos no utilizados simultáneamente o en segundo plano, si está disponible o si realiza la recolección de elementos no utilizados en primer plano.  
  
> [!WARNING]
>  A partir de .NET Framework 4, la recolección de elementos no utilizados en segundo plano reemplaza a la recolección de elementos no utilizados simultánea. Los términos *simultáneas* y *en segundo plano* se usan indistintamente en la documentación de .NET Framework. Para deshabilitar la recolección de elementos no utilizados en segundo plano, use el elemento `<gcConcurrent>` tal y como se describe en este artículo.  
  
 De forma predeterminada, CLR usa la recolección de elementos no utilizados simultánea, que está optimizada para la latencia. Si la aplicación requiere mucha interacción por parte del usuario, deje habilitada la recolección de elementos no utilizados simultánea para minimizar el tiempo que la aplicación debe parar para realizar la recolección de elementos no utilizados. Si establece el atributo `enabled` del elemento `<gcConcurrent>` en `false`, CLR usa la recolección de elementos no utilizados no simultánea, que está optimizada para el rendimiento. El archivo de configuración siguiente deshabilita la recolección de elementos no utilizados en segundo plano.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Si hay una opción de configuración `<gcConcurrentSetting>` en el archivo de configuración del equipo, define el valor predeterminado para todas las aplicaciones de .NET Framework. El archivo de configuración del equipo reemplaza el archivo de configuración de la aplicación.  
  
 Para obtener más información sobre simultáneas y recolección de elementos no utilizados en segundo plano, consulte la sección "recopilación de elementos no utilizados simultánea" en el [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) tema.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se habilita la recolección de elementos no utilizados simultánea.  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Fundamentos de la recolección de elementos no utilizados](../../../../../docs/standard/garbage-collection/fundamentals.md)
