---
title: <disableCachingBindingFailures> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
ms.openlocfilehash: 23633cb282b8e59b4df4bcc2cd38717d805a207e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117496"
---
# <a name="disablecachingbindingfailures-element"></a>\<disableCachingBindingFailures> (Elemento)
Especifica si se va a deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se va a deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|0|No deshabilite el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado. Este es el comportamiento de enlace predeterminado a partir de la versión .NET Framework 2,0.|  
|1|Deshabilite el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado. Esta configuración revierte al comportamiento de enlace de la .NET Framework versión 1,1.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la versión 2,0 de .NET Framework, el comportamiento predeterminado para cargar ensamblados es almacenar en caché todos los errores de enlace y carga. Es decir, si se produce un error al intentar cargar un ensamblado, las solicitudes posteriores para cargar el mismo ensamblado producen un error inmediatamente, sin ningún intento de buscar el ensamblado. Este elemento deshabilita el comportamiento predeterminado para los errores de enlace que se producen porque no se pudo encontrar el ensamblado en la ruta de acceso de sondeo. Se producen estos errores <xref:System.IO.FileNotFoundException> .  
  
 Algunos errores de enlace y carga no se ven afectados por este elemento y siempre se almacenan en caché. Estos errores se producen porque se encontró el ensamblado, pero no se pudo cargar. Inician <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException> . La lista siguiente incluye algunos ejemplos de estos errores.  
  
- Si intenta cargar un archivo no es un ensamblado válido, se producirá un error en los intentos posteriores de cargar el ensamblado aunque el archivo incorrecto se reemplace con el ensamblado correcto.  
  
- Si intenta cargar un ensamblado bloqueado por el sistema de archivos, se producirá un error en los intentos posteriores de cargar el ensamblado incluso después de que el sistema de archivos libere el ensamblado.  
  
- Si una o varias de las versiones del ensamblado que está intentando cargar se encuentran en la ruta de acceso de sondeo, pero la versión específica que está solicitando no está entre ellas, los intentos posteriores de cargar esa versión producirán un error aunque la versión correcta se mueva a la ruta de acceso de sondeo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo deshabilitar el almacenamiento en caché de errores de enlace de ensamblados que se producen porque el sondeo no encontró el ensamblado.  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md)
