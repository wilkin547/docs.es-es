---
title: '&lt;TimeSpan_LegacyFormatMode&gt; elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0faf2876680ef5ec3fc7373cae9f81eb091f47a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="lttimespanlegacyformatmodegt-element"></a>&lt;TimeSpan_LegacyFormatMode&gt; elemento
Determina si el runtime conserva el comportamiento heredado para dar formato a las operaciones con <xref:System.TimeSpan?displayProperty=nameWithType> valores.  
  
 \<configuration>  
\<en tiempo de ejecución >  
< TimeSpan_LegacyFormatMode >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime usa un comportamiento de formato heredado con <xref:System.TimeSpan?displayProperty=nameWithType> valores.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El runtime no restaura el comportamiento de formato heredado.|  
|`true`|El runtime restaura el comportamiento de formato heredado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> estructura implementa la <xref:System.IFormattable> interfaz y admite operaciones con cadenas de formato estándar y personalizados de formato. Si un método de análisis encuentra un especificador de formato no admitido o una cadena de formato, produce un <xref:System.FormatException>.  
  
 En versiones anteriores de .NET Framework, el <xref:System.TimeSpan> estructura no implementó <xref:System.IFormattable> y no admitía cadenas de formato. Sin embargo, muchos desarrolladores erróneamente supusieron que <xref:System.TimeSpan> eran compatibles con un conjunto de cadenas de formato y utilizarlos en [las operaciones de formato compuesto](../../../../../docs/standard/base-types/composite-formatting.md) con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType>. Por lo general, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con un formato no admitido cadenas suelen producen un <xref:System.FormatException>. Sin embargo, dado que <xref:System.TimeSpan> no implementó <xref:System.IFormattable>, el tiempo de ejecución omite la cadena de formato y se llama en su lugar el <xref:System.TimeSpan.ToString?displayProperty=nameWithType> método. Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no se ha producido un <xref:System.FormatException>.  
  
 Para los casos en los que código heredado pasa un método y una cadena de formato no válido de formato compuesto y no se puede volver a compilar ese código, puede usar el `<TimeSpan_LegacyFormatMode>` elemento que se va a restaurar heredado <xref:System.TimeSpan> comportamiento. Al establecer el `enabled` atributo de este elemento para `true`, el método produce una llamada a de formato compuesto <xref:System.TimeSpan.ToString?displayProperty=nameWithType> en lugar de <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>y un <xref:System.FormatException> no se produce.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un <xref:System.TimeSpan> objeto e intenta dar formato con el <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> método mediante una cadena de formato estándar no compatible.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 Al ejecutar el ejemplo en la [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] o en una versión anterior, muestra el siguiente resultado:  
  
```  
12:30:45  
```  
  
 Esto difiere notablemente de la salida, si ejecuta el ejemplo en la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o una versión posterior:  
  
```  
Invalid Format  
```  
  
 Sin embargo, si agrega el siguiente archivo de configuración para el ejemplo del directorio y, a continuación, ejecutar el ejemplo en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o una versión posterior, el resultado es idéntico al producido por el ejemplo, cuando se ejecuta en [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
