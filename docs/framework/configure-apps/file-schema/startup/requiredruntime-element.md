---
title: '&lt;requiredRuntime&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 12be2350cb123407b2f71d1f5f07e836ccddb9c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltrequiredruntimegt-element"></a>&lt;requiredRuntime&gt; elemento
Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime. Este elemento está en desuso y ya no debe usarse. El [ `supportedRuntime` ](supportedruntime-element.md) deberían usar el elemento en su lugar.
  
 \<configuration>  
\<Inicio >  
\<requiredRuntime >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`version`|Atributo opcional.<br /><br /> Un valor de cadena que especifica la versión de .NET Framework que es compatible con esta aplicación. El valor de cadena debe coincidir con el nombre de directorio se encuentra en la raíz de la instalación de .NET Framework. No se analiza el contenido del valor de cadena.|  
|`safemode`|Atributo opcional.<br /><br /> Especifica si el código de inicio en tiempo de ejecución busca en el registro para determinar la versión de tiempo de ejecución.|  
  
## <a name="safemode-attribute"></a>Atributo safemode  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El código de inicio en tiempo de ejecución busca en el registro. Este es el valor predeterminado.|  
|`true`|El código de inicio en tiempo de ejecución no busque en el registro.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`startup`|Contiene el `<requiredRuntime>` elemento.|  
  
## <a name="remarks"></a>Comentarios  
 Las aplicaciones compiladas para admitir solo la versión 1.0 del tiempo de ejecución deben usar la `<requiredRuntime>` elemento. Las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución deben usar el `<supportedRuntime>` elemento.  
  
> [!NOTE]
>  Si usas el [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) función para especificar el archivo de configuración, debe utilizar el `<requiredRuntime>` (elemento) para todas las versiones del runtime. El `<supportedRuntime>` elemento se omite cuando usa [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
 El `version` cadena de atributo debe coincidir con el nombre de la carpeta de instalación para la versión especificada de .NET Framework. Esta cadena no se interpreta. Si el código de inicio en tiempo de ejecución no encuentra una carpeta coincidente, el tiempo de ejecución no está cargado; el código de inicio muestra un mensaje de error y se cierra.  
  
> [!NOTE]
>  El código de inicio de una aplicación que se hospeda en Microsoft Internet Explorer omite el `<requiredRuntime>` elemento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de inicio](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Especificar la versión en tiempo de ejecución que se va a usar](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
