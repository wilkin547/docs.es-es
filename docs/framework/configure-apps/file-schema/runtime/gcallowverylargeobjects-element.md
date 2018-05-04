---
title: '&lt;gcAllowVeryLargeObjects&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 750b0dbc925ec484dd80e1796ba991435e354709
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltgcallowverylargeobjectsgt-element"></a>&lt;gcAllowVeryLargeObjects&gt; elemento
En plataformas de 64 bits, habilita matrices con un tamaño total superior a 2 gigabytes (GB).  
  
 \<Configuración > elemento  
\<en tiempo de ejecución > elemento  
\<gcAllowVeryLargeObjects > elemento  
  
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
  
|Valor|Descripción|  
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
  
-   El número máximo de elementos de una matriz es <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.  
  
-   El índice máximo de cualquier dimensión única es 2.147.483.591 (0x7FFFFFC7) para matrices de bytes y matrices de estructuras de un solo byte, y 2.146.435.071 (0X7FEFFFFF) para otros tipos.  
  
-   El tamaño máximo de las cadenas y otros objetos que no sean de matriz no varía.  
  
> [!CAUTION]
>  Antes de habilitar esta característica, asegúrese de que la aplicación no incluye código no seguro que supone que todas las matrices tienen un tamaño inferior a 2 GB. Por ejemplo, el código no seguro que usa matrices como búferes puede ser susceptible a saturaciones de búfer si se escribe basándose en la suposición de que las matrices no superarán los 2 GB de tamaño.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar esta característica para una aplicación.  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
