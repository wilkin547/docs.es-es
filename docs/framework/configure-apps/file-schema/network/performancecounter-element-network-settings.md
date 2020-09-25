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
ms.openlocfilehash: 4859f3a9e6de4f1bf8a56212bfe01f94d66f5650
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190246"
---
# <a name="performancecounter-element-network-settings"></a>Elemento \<performanceCounter> (configuración de red)

Habilita o deshabilita los contadores de rendimiento de red.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**

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
|[settings](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Observaciones  

 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
 Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará. Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración. Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse. Para obtener más información sobre los contadores de rendimiento de red específicos, vea [contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).  
  
 El valor predeterminado es que los contadores de rendimiento de red están deshabilitados.  
  
 La <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del atributo **Enabled** de los archivos de configuración aplicables.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
- [Contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)
