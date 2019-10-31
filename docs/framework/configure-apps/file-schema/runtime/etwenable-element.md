---
title: <etwEnable> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 14cea171a4a25e148ea32f75a8ef09b83a4ec8ad
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117392"
---
# <a name="etwenable-element"></a>\<elemento > etwEnable
Especifica si se debe habilitar Seguimiento de eventos para Windows (ETW) para los eventos de Common Language Runtime.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<etwEnabled >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si ETW debe estar habilitado.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|true|Habilitar ETW. Este es el valor predeterminado para las versiones de Windows a partir de los sistemas operativos Windows Vista y Windows Server 2008.|  
|False|Deshabilitar ETW. Este es el valor predeterminado para versiones anteriores de Windows.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de Windows Vista, ETW está habilitado de forma predeterminada. Use este elemento para deshabilitar ETW para una aplicación. En versiones anteriores de Windows, use este elemento para habilitar ETW para una aplicación.  
  
> [!NOTE]
> ETW se puede habilitar o deshabilitar globalmente en un servidor mediante una configuración del registro. Consulte [control del registro de .NET Framework](../../../performance/controlling-logging.md).  
  
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
