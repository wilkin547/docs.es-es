---
title: gcAllowVeryLargeObjects (elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 1e54b0780ffb5bbe81ab1be2b376ff7a038ee05c
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058134"
---
# <a name="gcallowverylargeobjects-element"></a>Elemento \<gcAllowVeryLargeObjects>

En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a>Atributos
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.|  
  
### <a name="enabled-attribute"></a>atributo Enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|Las matrices con un tamaño total superior a 2 GB no están habilitadas. Este es el valor predeterminado.|  
|`true`|Las matrices con un tamaño total superior a 2 GB se habilitan en plataformas de 64 bits.|  
  
## <a name="child-elements"></a>Elementos secundarios  

Ninguno.  
  
## <a name="parent-elements"></a>Elementos primarios
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  

 El uso de este elemento en el archivo de configuración de la aplicación permite utilizar matrices con un tamaño superior a 2 GB, pero no cambia otros límites de tamaño de objetos o matrices:  
  
- El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
- El tamaño máximo de una sola dimensión es 2.147.483.591 (0x7FFFFFC7) para las matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para las matrices que contienen otros tipos.  
  
- El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.  
  
> [!CAUTION]
> Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB. Por ejemplo, el código no seguro que utiliza matrices como búferes podría ser susceptible a saturaciones del búfer si se escribe en la suposición de que las matrices no superarán los 2 GB.  
  
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
