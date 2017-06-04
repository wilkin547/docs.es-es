---
title: "SecAnnotate.exe (.NET Security Annotator Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "SecAnnotate.exe"
  - "Security Annotator tool"
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# SecAnnotate.exe (.NET Security Annotator Tool)
La herramienta Anotador de seguridad de .NET \(SecAnnotate.exe\) es una aplicación de línea de comandos que identifica los elementos `SecurityCritical` y `SecuritySafeCritical` de uno o más ensamblados.  
  
 El [Anotador de seguridad](http://go.microsoft.com/fwlink/?LinkId=198007), que es una extensión de Visual Studio, proporciona una interfaz gráfica de usuario a SecAnnotate.exe y permite ejecutar la herramienta desde Visual Studio.  
  
 Esta herramienta se instala automáticamente con Visual Studio.  Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores \(o el Símbolo del sistema de Visual Studio en Windows 7\).  Para obtener más información, vea [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente, donde *parameters* se describe en la sección siguiente, y *assemblies* se compone de uno o varios nombres de ensamblado separados por espacios en blanco:  
  
## Sintaxis  
  
```  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
#### Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|`/a`<br /><br /> \-O bien\-<br /><br /> `/showstatistics`|Muestra estadísticas sobre el uso de transparencia en los ensamblados que se van a analizar.|  
|`/d:` *directory*<br /><br /> \-O bien\-<br /><br /> `/referencedir:` *directory*|Especifica el directorio en el que buscar los ensamblados dependientes durante la anotación.|  
|`/i`<br /><br /> \-O bien\-<br /><br /> `/includesignatures`|Incluye información de signatura ampliada en el archivo de informe de anotación.|  
|`/n`<br /><br /> \-O bien\-<br /><br /> `/nogac`|Suprime la búsqueda de los ensamblados a los que se hace referencia en la caché global de ensamblados.|  
|`/o:` *output.xml*  ``<br /><br /> \-O bien\-<br /><br /> `/out:` *output.xml*|Especifica el archivo de anotación de salida.|  
|`/p:` *maxpasses*  ``<br /><br /> \-O bien\-<br /><br /> `/maximumpasses:` *maxpasses*|Especifica el número máximo de pasos de anotación que se realizan en los ensamblados antes de detener la generación de nuevas anotaciones.|  
|`/q`<br /><br /> \-O bien\-<br /><br /> `/quiet`|Especifica el modo silencioso, en el que el anotador no genera mensajes de salida de estado; solo genera información de error.|  
|`/r:` *assembly*<br /><br /> \-O bien\-<br /><br /> `/referenceassembly:` *assembly*|Incluye el ensamblado especificado al resolver ensamblados dependientes durante la anotación.  Los ensamblados de referencia tienen prioridad sobre los ensamblados que se encuentran en la ruta de acceso de referencia.|  
|`/s:` *rulename*  ``<br /><br /> \-O bien\-<br /><br /> `/suppressrule:` *rulename*|Suprime la ejecución de la regla de transparencia especificada en los ensamblados de entrada.|  
|`/t`<br /><br /> \-O bien\-<br /><br /> `/forcetransparent`|Fuerza a la herramienta Anotador a tratar todos los ensamblados que no tienen ninguna anotación de transparencia como si fueran completamente transparentes.|  
|`/t`:*assembly*<br /><br /> \-O bien\-<br /><br /> `/forcetransparent`:*assembly*|Fuerza al ensamblado proporcionado a que sea transparente, independientemente de las anotaciones de nivel de ensamblado actuales.|  
|||  
|`/v`<br /><br /> \-O bien\-<br /><br /> `/verify`|Comprueba únicamente que las anotaciones de un ensamblado sean correctas, pero no intenta ejecutar varios pasos para buscar todas las anotaciones necesarias si el ensamblado no supera la comprobación.|  
|`/x`<br /><br /> \-O bien\-<br /><br /> `/verbose`|Especifica resultados detallados al anotar.|  
|`/y:` *directory*  ``<br /><br /> \-O bien\-<br /><br /> `/symbolpath:` *directory*|Incluye el directorio especificado al buscar archivos de símbolos durante la anotación.|  
  
## Comentarios  
 Los parámetros y ensamblados también se pueden proporcionar en un archivo de respuesta que se especifica en la línea de comandos y lleva el prefijo de una arroba \(@\).  Cada línea del archivo de respuesta debe contener un nombre de ensamblado o parámetro único.  
  
 Para obtener más información sobre el Anotador de seguridad de .NET, vea la entrada sobre [cómo utilizar SecAnnotate para analizar los ensamblados y detectar infracciones de transparencia](http://go.microsoft.com/fwlink/?LinkId=187648) en el blog de seguridad de .NET.  
  
## Ejemplos