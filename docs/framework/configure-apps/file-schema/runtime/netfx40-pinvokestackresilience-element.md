---
title: '&lt;NetFx40_PInvokeStackResilience&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cfd8c971edd4537de6e073c49f128f86eb8a042
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749002"
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si el tiempo de ejecución detecta incorrecta de la plataforma declaraciones de invocación y corrige automáticamente la pila en tiempo de ejecución en plataformas de 32 bits.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`0`|El runtime usa la arquitectura que se introdujo en referencias interoperativo más rápido el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], que no detecta y declaraciones de invocación de plataforma incorrectas de corrección. Este es el valor predeterminado.|  
|`1`|El runtime usa transiciones más lentas que detectan y corrigen incorrecta de la plataforma de declaraciones de invocación.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento le permite realizar transacciones comerciales más rápidos de referencias interoperativo para las declaraciones de invocación de resistencia de tiempo de ejecución con la plataforma incorrecta.  
  
 A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], una arquitectura de serialización de interoperabilidad simplificada proporciona una mejora significativa del rendimiento para las transiciones desde el código administrado a código no administrado. En versiones anteriores de .NET Framework, la plataforma incorrecta de capa detectado serialización invocar declaraciones en plataformas de 32 bits y automáticamente fija la pila. La nueva arquitectura de cálculo de referencias elimina este paso. Como resultado, las transiciones son muy rápidas, pero declaración de invocación de una plataforma incorrecta puede producir un error de programa.  
  
 Para facilitar la detectar declaraciones incorrectas durante el desarrollo, se ha mejorado la experiencia de depuración de Visual Studio. El [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) Asistente para la depuración administrada (MDA) notifica sobre incorrecta de la plataforma declaraciones de invocación cuando se ejecuta la aplicación con el depurador adjunto.  
  
 Para resolver escenarios donde la aplicación usa componentes que no se puede volver a compilar, y que haya incorrecta declaraciones invocación de plataforma, puede usar el `NetFx40_PInvokeStackResilience` elemento. Agregar este elemento a su archivo de configuración de aplicación con `enabled="1"` opta por participar en un modo de compatibilidad con el comportamiento de versiones anteriores de .NET Framework, pero a costa de transiciones más lentas. Los ensamblados que se han compilado con versiones anteriores de .NET Framework se suscriben automáticamente en este modo de compatibilidad y no es necesario este elemento.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar únicamente en el archivo de configuración de aplicación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo no formen parte de una mayor resistencia contra incorrecta de invocación de plataforma declaraciones para una aplicación, a costa de transiciones más lentas entre código administrado y.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
