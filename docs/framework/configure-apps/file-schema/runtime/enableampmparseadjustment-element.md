---
title: <EnableAmPmParseAdjustment> Elemento
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222515"
---
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment > elemento
Determina si la fecha y hora en que los métodos de análisis usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen un día, mes, hora y designador AM/PM.  
  
 \<configuration>  
 \<runtime>  
\<EnableAmPmParseAdjustment>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si la fecha y hora en que los métodos de análisis utilizan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
  
### <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|Fecha y hora en que los métodos de análisis no utilizan reglas ajustadas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
|1|Fecha y hora en que los métodos de análisis usan ajustadas reglas para analizar las cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 El `<EnableAmPmParseAdjustment>` elemento controla cómo los métodos siguientes para analizar una cadena de fecha que contiene un número de día y mes seguido de una hora y un designador AM/PM (por ejemplo, "4/10 6 a. M."):  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 No hay otros patrones se ven afectados.  
  
 El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto el <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, y <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> métodos.  
  
> [!IMPORTANT]
>  En .NET Core y .NET Native, se habilitan las reglas de análisis de A.M./P.M. ajustadas de forma predeterminada.  
  
 Si no está habilitada la regla de ajuste de análisis, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas, y se omite el resto de la cadena, excepto el designador AM/PM. La fecha y hora devuelto por el método de análisis consta de la fecha actual y la hora del día extraído de la cadena de fecha.  
  
 Si está habilitada la regla de ajuste de análisis, el método de análisis interpretar el día y mes como pertenecientes al año actual e interpretar al tiempo que la hora del reloj de 12 horas.  
  
 En la tabla siguiente se ilustra la diferencia en el <xref:System.DateTime> valor cuando la <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> método se utiliza para analizar la cadena "" 4/10 6 a. M."con el `<EnableAmPmParseAdjustment>` del elemento `enabled` propiedad establecida en"0"o"1". Se supone que la fecha de hoy es del 5 de enero de 2017 y muestra la fecha como si se da formato con la cadena de formato "G" de la referencia cultural especificada.  
  
|Nombre de referencia cultural|enabled="0"|enabled="1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 A.M.|4/10/2017 6:00:00 A.M.|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Vea también

- [\<en tiempo de ejecución > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [\<Configuración > elemento](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
