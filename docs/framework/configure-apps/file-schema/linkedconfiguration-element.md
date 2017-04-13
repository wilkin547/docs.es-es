---
title: "&lt;linkedConfiguration&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<linkedConfiguration> (elemento)"
  - "archivos de configuración [.NET Framework], archivos de configuración vinculados"
  - "incluir archivos de configuración"
  - "archivos de configuración vinculados"
  - "linkedConfiguration (elemento)"
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;linkedConfiguration&gt; (elemento)
Especifica un archivo de configuración para incluirlo.  
  
## Sintaxis  
  
```  
<linkedConfiguration  
   href="URL of linked configuration file"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`href`|Dirección URL del archivo de configuración que se debe incluir.  El único formato que admite el atributo `href` es "file:\/\/".  Se admiten archivos UNC y locales.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<assemblyBinding\> \(elemento\)](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)|Especifica la directiva de enlace del ensamblado en el nivel de configuración.|  
  
## Comentarios  
 El elemento `<linkedConfiguration>` simplifica el servicio para los ensamblados de componentes.  Si una o más aplicaciones utilizan un ensamblado que tiene un archivo de configuración que reside en una ubicación conocida, los archivos de configuración de las aplicaciones que utilizan el ensamblado pueden usar el elemento `<linkedConfiguration>` para incluir el archivo de configuración del ensamblado, en lugar de incluir información de configuración directamente.  Cuando se da servicio al ensamblado de componentes, al actualizar el archivo de configuración común, se proporciona información de configuración actualizada a todas las aplicaciones que utilizan el ensamblado.  
  
> [!NOTE]
>  El elemento `<linkedConfiguration>` no se admite en las aplicaciones con manifiestos en paralelo de Windows.  
  
 Las reglas siguientes rigen el uso de archivos de configuración vinculados.  
  
-   Los valores de configuración de los archivos de configuración incluidos sólo afectan a la directiva de enlace del cargador y únicamente los utiliza el cargador.  Los archivos de configuración incluidos pueden tener valores de configuración además de directivas de enlace, pero dichos valores no tienen ningún efecto.  
  
-   El único formato que admite el atributo `href` es "file:\/\/".  Se admiten archivos UNC y locales.  
  
-   No hay ninguna restricción en el número de configuraciones vinculadas por archivo de configuración.  
  
-   Todos los archivos de configuración vinculados se combinan para formar un único archivo, de forma similar al comportamiento de la directiva `#include` en C\/C\+\+.  
  
-   El elemento `<linkedConfiguration>` sólo se permite en archivos de configuración de aplicación; se omite en Machine.config.  
  
-   Se detectan y finalizan las referencias circulares.  Es decir, si los elementos `<linkedConfiguration>` de una serie de archivos de configuración forman un bucle, se detecta y se detiene el bucle.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo incluir un archivo de configuración desde el disco duro local.  
  
```  
<configuration>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>  
   </assemblyBinding>  
</configuration>  
```  
  
## Vea también  
 [\<assemblyBinding\> \(elemento\)](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
 [Esquema de los archivos de configuración](../../../../docs/framework/configure-apps/file-schema/index.md)