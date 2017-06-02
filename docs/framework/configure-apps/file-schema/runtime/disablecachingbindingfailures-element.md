---
title: "&lt;disableCachingBindingFailures&gt; (Elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<disableCachingBindingFailures> (elemento)"
  - "ensamblados [.NET Framework], almacenar en caché errores de enlace"
  - "almacenar en caché errores de enlace de ensamblados"
  - "disableCachingBindingFailures (elemento)"
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# &lt;disableCachingBindingFailures&gt; (Elemento)
Especifica si se va a deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el ensamblado no se encontró mediante sondeo.  
  
## Sintaxis  
  
```  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Atributo necesario.<br /><br /> Especifica si se va a deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el ensamblado no se encontró mediante sondeo.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|0|No deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el ensamblado no se encontró mediante sondeo.  Éste es el comportamiento predeterminado de los enlaces a partir de la versión 2.0 de .NET Framework.|  
|1|Deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el ensamblado no se encontró mediante sondeo.  Este valor vuelve al comportamiento de los enlace de la versión 1.1 de .NET Framework.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 A partir de la versión 2.0 de .NET Framework, el comportamiento predeterminado para cargar ensamblados es almacenar en caché todos los errores de enlace y de carga.  Es decir, si se produce un error cuando se intenta cargar un ensamblado, se genera al momento un error en las solicitudes posteriores para dicho ensamblado, sin ningún intento de localizar el ensamblado.  Este elemento deshabilita ese comportamiento predeterminado para los errores de enlace que se producen porque el ensamblado no se pudo encontrar en la ruta de acceso de sondeo.  Estos errores producen <xref:System.IO.FileNotFoundException>.  
  
 Algunos errores de enlace y carga no se ven afectados por este elemento y siempre se almacenan en memoria caché.  Estos errores se producen porque se encontró el ensamblado pero no se pudo cargar.  Producen <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>.  La siguiente lista incluye algunos ejemplos de tales errores.  
  
-   Si intenta cargar un archivo que no es un ensamblado válido, los intentos posteriores de cargar el ensamblado generarán un error incluso si se reemplaza el archivo no válido con el ensamblado correcto.  
  
-   Si intenta cargar un ensamblado bloqueados por el sistema de archivos, los intentos posteriores de cargar el ensamblado generarán un error incluso si el sistema de archivos libera dicho ensamblado.  
  
-   Si hay una o varias versiones del ensamblado que está intentando cargar en la ruta de acceso de sondeo pero la versión que está solicitando no es una de ellas, se producirá un error al intentar cargar esa versión incluso si se mueve la versión correcta a dicha ruta de acceso.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo deshabilitar el almacenamiento en caché de errores de enlace de ensamblado que se producen porque el ensamblado no se encontró mediante sondeo.  
  
```  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)