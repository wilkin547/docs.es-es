---
title: <gcServer> (Elemento)
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
ms.openlocfilehash: aa03179df1cd2595b4be428106dd3ec10b309317
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252551"
---
# <a name="gcserver-element"></a>\<gcServer >, elemento
Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<gcServer>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de servidor.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`false`|No ejecuta la recolección de elementos no utilizados de servidor. Este es el valor predeterminado.|  
|`true`|Ejecuta la recolección de elementos no utilizados de servidor.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Common Language Runtime (CLR) admite dos tipos de recolección de elementos no utilizados: de estación de trabajo, que está disponible en todos los sistemas, y de servidor, que está disponible en sistemas multiprocesador. El elemento `<gcServer>` se usa para controlar el tipo de recolección de elementos no utilizados que CLR realiza. Use la propiedad <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> para determinar si la recolección de elementos no utilizados de servidor está habilitada.  
  
 Para equipos con un solo procesador, la recolección de elementos no utilizados de estación de trabajo predeterminada será la opción más rápida. En los equipos con dos procesadores se puede usar la opción de estación de trabajo o de servidor. La recolección de elementos no utilizados de servidor será la opción más rápida si hay más de dos procesadores.  
  
 Este elemento se puede usar solo en el archivo de configuración de la aplicación; se omite si se encuentra en el archivo de configuración del equipo.  
  
> [!NOTE]
> En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados simultánea no está disponible si la recolección de elementos no utilizados de servidor está habilitada. A partir de la .NET Framework 4,5, la recolección de elementos no utilizados de servidor es simultánea. Para usar la recolección de elementos no utilizados de servidor no simultánea `<gcServer>` , establezca `true` el elemento en y el [ \<elemento > de gcConcurrent](gcconcurrent-element.md) en. `false`  
  
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

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Para deshabilitar la recolección de elementos no utilizados simultánea](gcconcurrent-element.md#to-disable-background-garbage-collection)
