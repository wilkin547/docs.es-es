---
title: <gcAllowVeryLargeObjects> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154132"
---
# <a name="gcallowverylargeobjects-element"></a>\<gcAllowVeryLargeObjects> (Elemento)
En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|Las matrices con un tamaño total superior a 2 GB no están habilitadas. Este es el valor predeterminado.|  
|`true`|Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:  
  
- El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
- El índice máximo de cualquier dimensión única es 2.147.483.591 (0x7FFFFFC7) para matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para otros tipos.  
  
- El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.  
  
> [!CAUTION]
> Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB. Por ejemplo, el código no seguro que usa matrices como búferes puede ser susceptible a saturaciones de búfer si se escribe basándose en la suposición de que las matrices no superarán los 2 GB de tamaño.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a>Compatible con

.NET Framework 4,5 y versiones posteriores

## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
