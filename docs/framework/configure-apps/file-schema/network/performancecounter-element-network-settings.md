---
title: Elemento <performanceCounter> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 58a2bf5118a3a2cd9c33301eca5dcc751c2351bf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283091"
---
# <a name="performancecounter-element-network-settings"></a>\<elemento > performanceCounter (configuración de red)
Habilita o deshabilita los contadores de rendimiento de red.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;[ **&nbsp;&nbsp;\<>\** ](settings-element-network-settings.md)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<performanceCounters >**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Especifica si los contadores de rendimiento de red están habilitados. El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Configuración](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
 Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará. Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración. Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse. Para obtener más información sobre los contadores de rendimiento de red específicos, vea [contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).  
  
 El valor predeterminado es que los contadores de rendimiento de red están deshabilitados.  
  
 La propiedad <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo **Enabled** de los archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar el <xref:System.Net> y los espacios de nombres relacionados para habilitar los contadores de rendimiento de red.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
- [Contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)
