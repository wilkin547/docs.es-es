---
title: '&lt;EnableAmPmParseAdjustment&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 44bd6297142b6f29d93e9a3bebdb89d32d4bf46a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltenableampmparseadjustmentgt-element"></a>&lt;EnableAmPmParseAdjustment&gt; elemento
Determina si la fecha y hora en métodos de análisis usan un conjunto de reglas ajustado para analizar cadenas de fecha que contienen un día, el mes, la hora y el designador AM/PM.  
  
 \<configuration>  
 \<en tiempo de ejecución >  
\<EnableAmPmParseAdjustment >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si la fecha y hora en métodos de análisis utilizan un conjunto de reglas ajustado para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
  
### <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|Fecha y hora en métodos de análisis no utilizan reglas ajustadas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
|1|Fecha y hora en métodos de análisis usan reglas ajustadas para analizar las cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 El `<EnableAmPmParseAdjustment>` elemento controla cómo los métodos siguientes para analizar una cadena de fecha que contiene un número de día y mes seguido de una hora y un designador AM/PM (por ejemplo, "4/10 6 A.M."):  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Otros patrones que no se ven afectados.  
  
 El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto el <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, y <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> métodos.  
  
> [!IMPORTANT]
>  En .NET Core y .NET Native, las reglas de análisis de AM/PM ajustadas están habilitadas de forma predeterminada.  
  
 Si no está habilitada la regla de ajuste de análisis, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas, y se omite el resto de la cadena excepto el designador AM/PM. La fecha y hora devuelto por el método de análisis consta de la fecha actual y la hora del día que se extrae de la cadena de fecha.  
  
 Si está habilitada la regla de ajuste de análisis, en el método de análisis interpretar el día y el mes como pertenecientes al año actual e interpretar al tiempo que la hora del reloj de 12 horas.  
  
 En la tabla siguiente se ilustra la diferencia entre el <xref:System.DateTime> valor cuando la <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> método se utiliza para analizar la cadena "" 4/10 6 AM"con el `<EnableAmPmParseAdjustment>` del elemento `enabled` propiedad establecida en"0"o"1". Se supone que la fecha actual es el 5 de enero de 2017 y muestra la fecha como si se da formato con la cadena de formato "G" de la referencia cultural especificada.  
  
|Nombre de referencia cultural|habilitada = "0"|habilitada = "1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 A.M.|4/10/2017 6:00:00 A.M.|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Vea también  
 [\<en tiempo de ejecución > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
