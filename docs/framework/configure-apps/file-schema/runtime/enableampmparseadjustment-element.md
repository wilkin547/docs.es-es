---
title: <EnableAmPmParseAdjustment> (Elemento)
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a62bd3507c14e42798c903ae51edb0187e666c8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663763"
---
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment >, elemento
Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen un día, un mes, una hora y un designador AM/PM.  
  
 \<configuration>  
 \<> en tiempo de ejecución  
\<EnableAmPmParseAdjustment>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y un designador AM/PM.|  
  
### <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|0|Los métodos de análisis de fecha y hora no usan reglas ajustadas para analizar cadenas de fecha que contengan solo un día, un mes, una hora y un designador AM/PM.|  
|1|Los métodos de análisis de fecha y hora usan reglas ajustadas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y el designador AM/PM.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 El `<EnableAmPmParseAdjustment>` elemento controla el modo en que los siguientes métodos analizan una cadena de fecha que contiene un día y un mes numéricos seguidos de una hora y un designador AM/PM (por ejemplo, "4/10 6 AM"):  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 No se ven afectados otros patrones.  
  
 El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto en <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>los <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>métodos <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>,, <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> y.  
  
> [!IMPORTANT]
>  En .NET Core y .NET Native, las reglas de análisis de AM/PM ajustadas están habilitadas de forma predeterminada.  
  
 Si la regla de ajuste de análisis no está habilitada, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas y se omite el resto de la cadena excepto el designador AM/PM. La fecha y hora devueltas por el método de análisis consta de la fecha actual y la hora del día extraída de la cadena de fecha.  
  
 Si está habilitada la regla de ajuste de análisis, el método de análisis interpreta el día y el mes como pertenecientes al año actual e interpreta la hora como la hora del reloj de 12 horas.  
  
 En la tabla siguiente se muestra la diferencia en <xref:System.DateTime> el valor cuando <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> el método se utiliza para analizar la cadena "" 4/10 6 AM "con `<EnableAmPmParseAdjustment>` la propiedad `enabled` del elemento establecida en" 0 "o" 1 ". Supone que la fecha de hoy es el 5 de enero de 2017 y muestra la fecha como si estuviera formateada con la cadena de formato "G" de la referencia cultural especificada.  
  
|Nombre de referencia cultural|enabled="0"|habilitado = "1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 AM|4/10/2017 6:00:00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Vea también

- [\<Elemento > en tiempo de ejecución](runtime-element.md)
- [Elemento \<configuration>](../configuration-element.md)
