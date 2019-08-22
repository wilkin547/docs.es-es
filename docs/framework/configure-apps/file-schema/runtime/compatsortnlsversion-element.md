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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ebc4bf703bc22b642b0950fd60471342a615a5c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663849"
---
# <a name="compatsortnlsversion-element"></a>\<CompatSortNLSVersion >, elemento
Especifica que el runtime debe usar criterios de ordenación heredados al realizar comparaciones de cadenas.  
  
 \<configuration>  
\<> en tiempo de ejecución  
\<CompatSortNLSVersion >, elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica el identificador de configuración regional cuyo criterio de ordenación se va a usar.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|4096|El identificador de configuración regional que representa un criterio de ordenación alternativo. En este caso, 4096 representa el criterio de ordenación de los .NET Framework 3,5 y versiones anteriores.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Dado que las operaciones de comparación de cadenas, ordenación y uso <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> de mayúsculas y minúsculas realizadas por la clase en el .NET Framework 4 se ajustan al estándar Unicode <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> 5,1 <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> , los resultados de los métodos de comparación de cadenas como y pueden diferir de versiones anteriores de la .NET Framework. Si su aplicación depende del comportamiento heredado, puede restaurar las reglas de comparación y ordenación de cadenas usadas en el .NET Framework 3,5 y versiones anteriores incluyendo `<CompatSortNLSVersion>` el elemento en el archivo de configuración de la aplicación.  
  
> [!IMPORTANT]
>  La restauración de reglas de comparación y ordenación de cadenas heredadas también requiere que la biblioteca de vínculos dinámicos sort00001000.dll esté disponible en el sistema local.  
  
 También puede usar reglas de ordenación y comparación de cadenas heredadas en un dominio de aplicación concreto. Para ello, pase la cadena "NetFx40_Legacy20SortingBehavior" al método <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> al crear el dominio de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se crean instancias de dos objetos <xref:System.String> y se llama al método <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> para compararlas usando las convenciones de la referencia cultural actual.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 Al ejecutar el ejemplo en el .NET Framework 4, se muestra el siguiente resultado.  
  
```  
sta follows a in the sort order.  
```  
  
 Esto es completamente diferente de la salida que se muestra al ejecutar el ejemplo en el .NET Framework 3,5.  
  
```  
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
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
