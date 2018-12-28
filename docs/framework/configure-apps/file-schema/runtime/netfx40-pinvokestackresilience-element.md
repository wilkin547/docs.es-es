---
title: '&lt;NetFx40_PInvokeStackResilience&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49dc991fd1f30bce6c328725a794750c753145cd
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613289"
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a>&lt;NetFx40_PInvokeStackResilience&gt; elemento
Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.  
  
 \<configuration>  
\<en tiempo de ejecución >  
< NetFx40_PInvokeStackResilience >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el tiempo de ejecución detecta incorrecta de la plataforma las declaraciones de invocación y corrige automáticamente la pila en tiempo de ejecución en plataformas de 32 bits.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`0`|El runtime usa la arquitectura que se introdujo en interoperativo más rápido el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], que no se detecta y declaraciones de invocación de plataforma incorrectas de corrección. Este es el valor predeterminado.|  
|`1`|El runtime usa transiciones más lentas que detectan y corrigen incorrecta de la plataforma de declaraciones de invocación.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento le permite intercambiar más rápido la serialización de interoperabilidad para las declaraciones de invocación de tiempo de ejecución Resista la plataforma incorrecta.  
  
 A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], una arquitectura de serialización de interoperabilidad simplificada proporciona una mejora significativa del rendimiento de las transiciones de código administrado a código no administrado. En versiones anteriores de .NET Framework, la plataforma incorrecta cálculo de referencias de capa detectado invocar declaraciones en las plataformas de 32 bits y automáticamente se ha corregido la pila. La nueva arquitectura de cálculo de referencias elimina este paso. Como resultado, transiciones son muy rápidas, pero la declaración de invocación de una plataforma incorrecta puede producir un error de programa.  
  
 Para que sea fácil de detectar declaraciones incorrectas durante el desarrollo, se ha mejorado la experiencia de depuración de Visual Studio. El [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) Asistente para la depuración administrada (MDA) notifica a las declaraciones de plataforma incorrectas de invocación cuando se ejecuta la aplicación con el depurador adjunto.  
  
 Para abordar escenarios donde la aplicación usa componentes que no se puede volver a compilar, y que dispone de invocación de plataforma incorrectas declaraciones, puede usar el `NetFx40_PInvokeStackResilience` elemento. Al agregar este elemento al archivo de configuración de la aplicación con `enabled="1"` incluye un modo de compatibilidad con el comportamiento de las versiones anteriores de .NET Framework, a costa de transiciones más lentas. Los ensamblados que se han compilado con versiones anteriores de .NET Framework se suscriben automáticamente en este modo de compatibilidad y no es necesario este elemento.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar solo en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra cómo para participar en una mayor resistencia contra incorrecta de invocación de plataforma declaraciones para una aplicación, a costa de transiciones más lentas entre código administrado y.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
