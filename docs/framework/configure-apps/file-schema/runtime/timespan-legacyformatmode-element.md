---
title: "&lt;TimeSpan_LegacyFormatMode&gt; (Elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<TimeSpan_LegacyFormatMode> (elemento)"
  - "TimeSpan_LegacyFormatMode (elemento)"
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;TimeSpan_LegacyFormatMode&gt; (Elemento)
Determina si el runtime conserva el comportamiento heredado en operaciones de formato con valores <xref:System.TimeSpan?displayProperty=fullName>.  
  
## Sintaxis  
  
```  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime usa comportamiento de formato heredado con valores <xref:System.TimeSpan?displayProperty=fullName>.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El runtime no restaura el comportamiento de formato heredado.|  
|`true`|El runtime restaura el comportamiento de formato heredado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## Comentarios  
 Comenzando con [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], la estructura <xref:System.TimeSpan?displayProperty=fullName> implementa la interfaz <xref:System.IFormattable> y admite operaciones de formato con cadenas de formato estándar y personalizado.  Si un método de análisis encuentra un especificador de formato o cadena de formato no compatibles, produce una excepción <xref:System.FormatException>.  
  
 En versiones anteriores de .NET Framework, la estructura <xref:System.TimeSpan> no implementaba <xref:System.IFormattable> y no admitía cadenas de formato.  Sin embargo, muchos programadores supusieron equivocadamente que <xref:System.TimeSpan> era compatible con un conjunto de cadenas de formato y los usaron en [operaciones de formato compuesto](../../../../../docs/standard/base-types/composite-formatting.md) con métodos como <xref:System.String.Format%2A?displayProperty=fullName>.  Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a los métodos de formato con cadenas de formato no compatibles normalmente producen <xref:System.FormatException>.  No obstante, como <xref:System.TimeSpan> no implementó <xref:System.IFormattable>, el runtime omitió la cadena de formato y en su lugar llamó al método <xref:System.TimeSpan.ToString?displayProperty=fullName>.  Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no producía <xref:System.FormatException>.  
  
 Para los casos en los que el código heredado pasa un método de formato compuesto y una cadena de formato no válida y no se puede volver a compilar ese código, puede usar el elemento `<TimeSpan_LegacyFormatMode>` para restaurar el comportamiento heredado de <xref:System.TimeSpan>.  Al establecer el atributo `enabled` de este elemento en `true`, el método de formato compuesto produce una llamada a <xref:System.TimeSpan.ToString?displayProperty=fullName> en lugar de <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName>, y no se produce <xref:System.FormatException>.  
  
## Ejemplo  
 En el siguiente ejemplo se crean instancias de un objeto <xref:System.TimeSpan> y se le intenta dar formato con el método <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=fullName> utilizando una cadena del formato estándar no compatible.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 Al ejecutar el ejemplo en [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] o en una versión anterior, se muestra el siguiente resultado:  
  
```  
12:30:45  
```  
  
 Esto difiere marcado de salida si ejecuta el ejemplo en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o la versión posterior:  
  
```  
Invalid Format  
```  
  
 Sin embargo, si agrega el archivo de configuración siguiente al directorio de ejemplo y después ejecuta el ejemplo en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o la versión posterior, el resultado es idéntica a la que el ejemplo cuando se ejecuta en [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)