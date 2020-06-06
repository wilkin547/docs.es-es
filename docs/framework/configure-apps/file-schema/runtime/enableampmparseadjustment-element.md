---
title: <EnableAmPmParseAdjustment> (Elemento)
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 8920e51fcaaca5cb78b80a99ea321163c9b5240f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117367"
---
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment> (Elemento)
Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen un día, un mes, una hora y un designador AM/PM.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y un designador AM/PM.|  
  
### <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|0|Los métodos de análisis de fecha y hora no usan reglas ajustadas para analizar cadenas de fecha que contengan solo un día, un mes, una hora y un designador AM/PM.|  
|1|Los métodos de análisis de fecha y hora usan reglas ajustadas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y el designador AM/PM.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
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
  
 El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto en <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> los <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> métodos,, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> y <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .  
  
> [!IMPORTANT]
> En .NET Core y .NET Native, las reglas de análisis de AM/PM ajustadas están habilitadas de forma predeterminada.  
  
 Si la regla de ajuste de análisis no está habilitada, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas y se omite el resto de la cadena excepto el designador AM/PM. La fecha y hora devueltas por el método de análisis consta de la fecha actual y la hora del día extraída de la cadena de fecha.  
  
 Si está habilitada la regla de ajuste de análisis, el método de análisis interpreta el día y el mes como pertenecientes al año actual e interpreta la hora como la hora del reloj de 12 horas.  
  
 En la tabla siguiente se muestra la diferencia en el <xref:System.DateTime> valor cuando el <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> método se utiliza para analizar la cadena "" 4/10 6 AM "con la `<EnableAmPmParseAdjustment>` propiedad del elemento `enabled` establecida en" 0 "o" 1 ". Supone que la fecha de hoy es el 5 de enero de 2017 y muestra la fecha como si estuviera formateada con la cadena de formato "G" de la referencia cultural especificada.  
  
|Nombre de referencia cultural|habilitado = "0"|habilitado = "1"|  
|------------------|------------------|------------------|  
|es-ES|1/5/2017 4:00:00 AM|4/10/2017 6:00:00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Consulte también

- [\<runtime>Element](runtime-element.md)
- [\<configuration>Element](../configuration-element.md)
