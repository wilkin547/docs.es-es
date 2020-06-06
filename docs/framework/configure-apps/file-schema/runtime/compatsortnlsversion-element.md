---
title: <CompatSortNLSVersion> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
ms.openlocfilehash: 30afeb2ab9380db75cbeb723ea15a23e4313c9e8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154275"
---
# <a name="compatsortnlsversion-element"></a>\<CompatSortNLSVersion> (Elemento)
Especifica que el runtime debe usar criterios de ordenación heredados al realizar comparaciones de cadenas.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<CompatSortNLSVersion>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<CompatSortNLSVersion
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica el identificador de configuración regional cuyo criterio de ordenación se va a usar.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|4096|El identificador de configuración regional que representa un criterio de ordenación alternativo. En este caso, 4096 representa el criterio de ordenación de los .NET Framework 3,5 y versiones anteriores.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Dado que las operaciones de comparación de cadenas, ordenación y uso de mayúsculas y minúsculas realizadas por la <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> clase en el .NET Framework 4 se ajustan al estándar Unicode 5,1, los resultados de los métodos de comparación de cadenas como <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> y <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> pueden diferir de las versiones anteriores de la .NET Framework. Si su aplicación depende del comportamiento heredado, puede restaurar las reglas de comparación y ordenación de cadenas usadas en el .NET Framework 3,5 y versiones anteriores incluyendo el `<CompatSortNLSVersion>` elemento en el archivo de configuración de la aplicación.  
  
> [!IMPORTANT]
> La restauración de reglas de comparación y ordenación de cadenas heredadas también requiere que la biblioteca de vínculos dinámicos sort00001000.dll esté disponible en el sistema local.  
  
 También puede usar reglas de ordenación y comparación de cadenas heredadas en un dominio de aplicación concreto. Para ello, pase la cadena "NetFx40_Legacy20SortingBehavior" al método <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> al crear el dominio de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se crean instancias de dos objetos <xref:System.String> y se llama al método <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> para compararlas usando las convenciones de la referencia cultural actual.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 Al ejecutar el ejemplo en el .NET Framework 4, se muestra el siguiente resultado:
  
```console
sta follows a in the sort order.  
```  
  
 Esto es completamente diferente de la salida que se muestra al ejecutar el ejemplo en el .NET Framework 3,5:
  
```console
sta equals a in the sort order.  
```  
  
 Sin embargo, si agrega el archivo de configuración siguiente al directorio del ejemplo y, a continuación, ejecuta el ejemplo en el .NET Framework 4, la salida es idéntica a la generada por el ejemplo cuando se ejecuta en el .NET Framework 3,5.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
