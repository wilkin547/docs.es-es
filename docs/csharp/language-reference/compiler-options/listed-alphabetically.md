---
title: "C# Compiler Options Listed Alphabetically | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "compiler options [C#], listed alpabetically"
  - "C# language, compiler options listed alphabitically"
  - "Visual C# compiler, options listed alphabetically"
  - "Visual C#, compiler options listed alphabetically"
ms.assetid: 43535ea0-ca47-4a15-b528-615087a86092
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# C# Compiler Options Listed Alphabetically
Las siguientes opciones del compilador están ordenadas alfabéticamente.  Para obtener una lista por categoría, vea [C\# Compiler Options Listed by Category](../../../csharp/language-reference/compiler-options/listed-by-category.md).  
  
|Opción|Propósito|  
|------------|---------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|Leer un archivo de respuesta para ver más opciones.|  
|[\/?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Muestra un mensaje de uso a stdout.|  
|`/additionalfile`|Asigna un nombre a los archivos adicionales que no afectan directamente a la generación de código, pero que pueden usarse desde los analizadores para generar errores o advertencias.|  
|[\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|Vincula los módulos especificados en este ensamblado.|  
|`/analyzer`|Ejecuta los analizadores de este ensamblado \(forma abreviada: \/a\).|  
|[\/appconfig](../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)|Especifica la ubicación de app.config en el momento del enlace de ensamblado.|  
|[\/baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|Especifica la dirección base de la biblioteca que se compilará.|  
|[\/bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|Crea un archivo 'Informe de errores'.  Este archivo se enviará junto con la información de bloqueo si se usa con **\/errorreport:prompt** o **\/errorreport:send**.|  
|[\/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|Hace que el compilador genere comprobaciones de desbordamiento.|  
|`/checksumalgorithm:<alg>`|Especifique el algoritmo para calcular la suma de comprobación del archivo de origen almacenado en el archivo PDB.  Los valores admitidos son: SHA1 \(predeterminado\) o SHA256.|  
|[\/codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|Especifica la página de códigos que se va a utilizar cuando se abren los archivos de código fuente.|  
|[\/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|Emite información de depuración.|  
|[\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|Define símbolos de compilación condicional.|  
|[\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|Retrasa la firma del ensamblado usando solo la parte pública de la clave de nombre seguro.|  
|[\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|Especifica un archivo de documentación XML que se generará.|  
|[\/errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|Especifica cómo tratar los errores internos del compilador: prompt, send o none.  El valor predeterminado es none.|  
|[\/filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|Especifica la alineación usada para las secciones de archivos de salida.|  
|[\/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|Hace que el compilador genere rutas de acceso completas.|  
|[\/help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Muestra un mensaje de uso a stdout.|  
|[\/highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|Especifica que se admite el ASLR de alta entropía.|  
|**\/incremental**|Habilita la compilación incremental \[obsoleto\].|  
|[\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|Especifica un contenedor de claves de nombre seguro.|  
|[\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|Especifica un archivo de clave de nombre seguro.|  
|[\/langversion:\<cadena\>](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|Especifica el modo de versión de lenguaje: ISO\-1, ISO\-2, 3, 4, 5, 6 o Default.|  
|[\/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|Especifica más directorios donde buscar referencias.|  
|[\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|Hace que la información de tipo COM de ensamblados específicos esté disponible en el proyecto.|  
|[\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|Vincula el recurso especificado a este ensamblado.|  
|[\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|Especifica el tipo que contiene el punto de entrada \(se pasan por alto los demás puntos de entrada posibles\).|  
|[\/moduleassemblyname](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)|Especifica un ensamblado a cuyos tipos no públicos puede tener acceso  un .netmodule.|  
|`/modulename:<string>`|Especifica el nombre del módulo de origen.|  
|[\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|Indica al compilador que no incluya el archivo CSC.RSP de forma automática.|  
|[\/nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|Suprime el mensaje de copyright del compilador.|  
|[\/nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|Indica al compilador que no haga referencia a la biblioteca estándar \(mscorlib.dll\).|  
|[\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|Deshabilita mensajes de advertencia específicos.|  
|[\/nowin32manifest](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)|Indica al compilador que no incruste un manifiesto de la aplicación en el archivo ejecutable.|  
|[\/optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|Habilita o deshabilita las optimizaciones.|  
|[\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|Especifica el nombre de archivo de salida \(nombre predeterminado: nombre base de archivo con la clase principal o del primer archivo\).|  
|`/parallel[+&#124;-]`|Especifica si hay que usar la compilación simultánea \(\+\).|  
|[\/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|Especifica el nombre y la ubicación de archivo del archivo .pdb.|  
|[\/platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|Limita las plataformas en las que se puede ejecutar este código: x86, Itanium, x64, anycpu o anycpu32bitpreferred.  El valor predeterminado es anycpu.|  
|[\/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Especifica el idioma que se usará para los resultados del compilador.|  
|[\/recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|Incluye todos los archivos del directorio y subdirectorios actuales de acuerdo con las especificaciones de los comodines.|  
|[\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|Hace referencia a los metadatos de los archivos de ensamblado especificados.|  
|[\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|Incrusta el recurso especificado.|  
|`/ruleset:<file>`|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|  
|[\/subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|Especifica la versión mínima del subsistema que el archivo ejecutable puede usar.|  
|[\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|Especifica el formato del archivo de salida con una de las seis opciones siguientes:[\/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [\/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), [\/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md).|  
|[\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|Permite código [no seguro](../../../csharp/language-reference/keywords/unsafe.md).|  
|[\/utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|Genera mensajes del compilador en codificación UTF\-8.|  
|[\/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|Establece el nivel de advertencia \(0\-4\).|  
|[\/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|Notifica advertencias específicas como errores.|  
|[\/win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|Usa este icono para los resultados.|  
|[\/win32manifest](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md)|Especifica un archivo de manifiesto win32 personalizado.|  
|[\/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|Especifica el archivo de recursos win32 \(.res\).|  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [C\# Compiler Options Listed by Category](../../../csharp/language-reference/compiler-options/listed-by-category.md)   
 [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)   
 [Elemento \<compiler\>](../Topic/%3Ccompiler%3E%20Element.md)