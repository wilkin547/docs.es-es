---
title: '&lt;disableCachingBindingFailures&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25d504afd7945718f08dd5f2bf92d7ea33037a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a>&lt;disableCachingBindingFailures&gt; elemento
Especifica si se deshabilita el almacenamiento en caché de errores que se producen porque el ensamblado no se encontró mediante sondeo de enlace.  
  
 \<Configuración > elemento  
\<en tiempo de ejecución > elemento  
\<disableCachingBindingFailures >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se deshabilita el almacenamiento en caché de errores que se producen porque el ensamblado no se encontró mediante sondeo de enlace.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|Deshabilitar el almacenamiento en caché de errores que se producen porque el ensamblado no se encontró mediante sondeo de enlace. Éste es el comportamiento de enlace de forma predeterminada a partir de la versión 2.0 de .NET Framework.|  
|1|Deshabilitar el almacenamiento en caché de errores que se producen porque el ensamblado no se encontró mediante sondeo de enlace. Esta configuración revierte el comportamiento de enlace de la versión 1.1 de .NET Framework.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la versión 2.0 de .NET Framework, el comportamiento predeterminado para cargar ensamblados es almacenar en caché todos los enlaces y los errores de carga. Es decir, si falla un intento para cargar un ensamblado, las posteriores solicitudes para cargar el mismo ensamblado producirá un error inmediatamente, sin ningún intento de localizar el ensamblado. Este elemento deshabilita ese comportamiento predeterminado para los errores que se producen porque no se encontró el ensamblado en la ruta de acceso de búsqueda de enlace. Estos errores se producen <xref:System.IO.FileNotFoundException>.  
  
 Algunos de los enlaces y los errores de carga, no se ven afectados por este elemento y siempre se almacenan en caché. Estos errores se producen porque se encontró el ensamblado, pero no se puede cargar. Producen <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>. En la lista siguiente incluye algunos ejemplos de tales errores.  
  
-   Si intenta cargar un archivo no es un ensamblado válido, se producirá un error en los intentos subsiguientes para cargar el ensamblado incluso si se reemplaza el archivo incorrecto con el ensamblado correcto.  
  
-   Si intenta cargar un ensamblado que está bloqueado por el sistema de archivos, se producirá un error en los intentos subsiguientes para cargar el ensamblado incluso después de que el ensamblado se libera por el sistema de archivos.  
  
-   Si una o varias versiones del ensamblado que está intentando cargar está en la ruta de acceso de búsqueda, pero la versión específica que solicita no está entre ellos, se producirá un error en los intentos subsiguientes para cargar esa versión incluso si se mueve la versión correcta en la ruta de acceso de búsqueda.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo deshabilitar el almacenamiento en caché de errores de enlace de ensamblado que se producen porque el ensamblado no se encontró mediante sondeo.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
