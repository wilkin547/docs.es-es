---
title: Elemento <TimeSpan_LegacyFormatMode>
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
ms.openlocfilehash: 38adde3cd51a96f0e15ed5a0c539e088f2d3b480
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701637"
---
# <a name="timespanlegacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode > elemento
Determina si el runtime conserva el comportamiento heredado para dar formato a las operaciones con <xref:System.TimeSpan?displayProperty=nameWithType> valores.  
  
 \<configuration>  
\<runtime>  
<TimeSpan_LegacyFormatMode>  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime usa el comportamiento de formato heredado con <xref:System.TimeSpan?displayProperty=nameWithType> valores.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El tiempo de ejecución no restaura el comportamiento de formato heredado.|  
|`true`|El runtime restaura el comportamiento de formato heredado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> estructura implementa el <xref:System.IFormattable> interfaz y admite operaciones con cadenas de formato estándar y personalizadas de formato. Si un método de análisis encuentra un especificador de formato no compatible o una cadena de formato, produce un <xref:System.FormatException>.  
  
 En versiones anteriores de .NET Framework, el <xref:System.TimeSpan> estructura no implementó <xref:System.IFormattable> y no eran compatibles con las cadenas de formato. Sin embargo, muchos desarrolladores erróneamente supusieron que <xref:System.TimeSpan> eran compatibles con un conjunto de cadenas de formato y se usaron en [las operaciones de formato compuesto](../../../../../docs/standard/base-types/composite-formatting.md) con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType>. Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con un formato no admitido cadenas suele producen un <xref:System.FormatException>. Sin embargo, dado que <xref:System.TimeSpan> no implementó <xref:System.IFormattable>, el tiempo de ejecución omite la cadena de formato y se llama en su lugar el <xref:System.TimeSpan.ToString?displayProperty=nameWithType> método. Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no se ha producido un <xref:System.FormatException>.  
  
 Para los casos en que código heredado pasa un método y una cadena de formato no válido de formato compuesto y no se puede volver a compilar ese código, puede usar el `<TimeSpan_LegacyFormatMode>` elemento para restaurar heredado <xref:System.TimeSpan> comportamiento. Al establecer el `enabled` atributo de este elemento para `true`, el método da como resultado una llamada a de formato compuesto <xref:System.TimeSpan.ToString?displayProperty=nameWithType> lugar <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>y un <xref:System.FormatException> no se produce.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un <xref:System.TimeSpan> objeto e intenta dar formato con el <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> método mediante una cadena de formato estándar no admitido.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 Al ejecutar el ejemplo en el [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] o una versión anterior, muestra el siguiente resultado:  
  
```  
12:30:45  
```  
  
 Esto difiere notablemente de la salida, si ejecuta el ejemplo en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o una versión posterior:  
  
```  
Invalid Format  
```  
  
 Sin embargo, si agrega el siguiente archivo de configuración para el ejemplo del directorio y, a continuación, ejecutar el ejemplo en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o una versión posterior, el resultado es idéntico al producido por el ejemplo, cuando se ejecuta [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
