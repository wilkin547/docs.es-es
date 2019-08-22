---
title: <etwEnable> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f24e9a06137744dbc97d5f34cda7ad6eab873700
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663737"
---
# <a name="etwenable-element"></a>\<etwEnable >, elemento
Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.  
  
 \<Elemento Configuration >  
\<Elemento > en tiempo de ejecución  
\<etwEnabled>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si ETW debe estar habilitado.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|DESCRIPCIÓN|  
|-----------|-----------------|  
|true|Habilitar ETW. Este es el valor predeterminado para las versiones de Windows a partir de los sistemas operativos Windows Vista y Windows Server 2008.|  
|false|Deshabilitar ETW. Este es el valor predeterminado para versiones anteriores de Windows.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de Windows Vista, ETW está habilitado de forma predeterminada. Use este elemento para deshabilitar ETW para una aplicación. En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.  
  
> [!NOTE]
>  ETW se puede habilitar o deshabilitar globalmente en un servidor mediante una configuración del registro. Consulte [control del registro de .NET Framework](../../../performance/controlling-logging.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar el seguimiento de ETW para una aplicación.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Controlar el registro de .NET Framework](../../../performance/controlling-logging.md)
