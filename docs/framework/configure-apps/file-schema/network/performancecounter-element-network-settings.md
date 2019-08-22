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
ms.openlocfilehash: 05aac6c1ed3c04bce263a45cafdb9bec906bd75b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664056"
---
# <a name="performancecounter-element-network-settings"></a>\<Elemento > performanceCounter (configuración de red)
Habilita o deshabilita los contadores de rendimiento de red.  
  
 \<configuration>  
\<system.net>  
\<> de configuración  
\<performanceCounters>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Especifica si los contadores de rendimiento de red están habilitados. El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[Configuración](settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
 Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará. Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración. Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse. Para obtener más información sobre los contadores de rendimiento de red específicos, vea contadores de [rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking).  
  
 El valor predeterminado es que los contadores de rendimiento de red están deshabilitados.  
  
 La <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del atributo **Enabled** de los archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar <xref:System.Net> el y los espacios de nombres relacionados para habilitar los contadores de rendimiento de red.  
  
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
- [Contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking)
