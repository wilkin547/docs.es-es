---
title: "C# Compiler Options Listed by Category | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
  - "CSharp"
helpviewer_keywords: 
  - "Visual C# compiler, options listed by category"
  - "compiler options [C#], listed by category"
  - "Visual C#, compiler options listed by category"
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C# Compiler Options Listed by Category
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las opciones del compilador siguientes están ordenadas por categoría.  Para acceder a una lista en orden alfabético, consulte [Opciones del compilador de C\#, por orden alfabético](../../../csharp/language-reference/compiler-options/listed-alphabetically.md).  
  
### Optimización  
  
|Opción|Propósito|  
|------------|---------------|  
|[\/filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|Especifica el tamaño de las secciones del archivo de salida.|  
|[\/optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|Habilita o deshabilita las optimizaciones.|  
  
### Archivos de resultados  
  
|Opción|Propósito|  
|------------|---------------|  
|[\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|Especifica un archivo XML donde se escribirán comentarios de documentación procesados.|  
|[\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|Especifica el archivo de salida.|  
|[\/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|Especifica el nombre de archivo y la ubicación del archivo .pdb.|  
|[\/platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|Especifica la plataforma de salida.|  
|[\/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Especifica un idioma para los resultados del compilador.|  
|[\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|Especifica el formato del archivo de salida con una de las seis opciones siguientes: [\/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [\/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) o [\/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md).|  
|`/modulename:<string>`|Especifica el nombre del módulo de origen.|  
  
### Ensamblados de .NET Framework  
  
|Opción|Propósito|  
|------------|---------------|  
|[\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|Especifica uno o varios módulos que formarán parte de este ensamblado.|  
|[\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|Indica al compilador que debe agregar la clave pública y mantener el ensamblado sin firma.|  
|[\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|Especifica el nombre del contenedor de claves criptográficas.|  
|[\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|Especifica el nombre de archivo que contiene la clave criptográfica.|  
|[\/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|Especifica la ubicación de los ensamblados a los que se hace referencia con [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).|  
|[\/nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|Indica al compilador que no debe importar la biblioteca estándar \(mscorlib.dll\).|  
|[\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|Importa los metadatos de un archivo que contiene un ensamblado.|  
|`/analyzer`|Ejecuta los analizadores de este ensamblado \(forma abreviada: \/a\).|  
|`/additionalfile`|Asigna un nombre a los archivos adicionales que no afectan directamente a la generación de código, pero que pueden usarse desde los analizadores para generar errores o advertencias.|  
  
### Comprobación de errores y depuración  
  
|Opción|Propósito|  
|------------|---------------|  
|[\/bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|Crea un archivo que contiene la información que permite notificar un error fácilmente.|  
|[\/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|Especifica si la aritmética de enteros que desborda los límites del tipo de datos iniciará una excepción en tiempo de ejecución.|  
|[\/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|Indica al compilador que debe emitir la información de depuración.|  
|[\/errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|Establece el comportamiento de los informes de errores.|  
|[\/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|Especifica la ruta de acceso absoluta al archivo en los resultados del compilador.|  
|[\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|Suprime la generación de advertencias especificadas en el compilador.|  
|[\/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|Establece el nivel de advertencia.|  
|[\/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|Promueve las advertencias a errores.|  
|`/ruleset:<file>`|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|  
  
### Preprocesador  
  
|Opción|Propósito|  
|------------|---------------|  
|[\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|Define los símbolos de preprocesador.|  
  
### Recursos  
  
|Opción|Propósito|  
|------------|---------------|  
|[\/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|Dispone la información de tipo COM de ensamblados específicos para que se encuentre disponible en el proyecto.|  
|[\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|Crea un vínculo a un recurso administrado.|  
|[\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|Incrusta un recurso de .NET Framework en el archivo de salida.|  
|[\/win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|Especifica un archivo .ico para insertarlo en el archivo de salida.|  
|[\/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|Especifica un recurso Win32 para insertarlo en el archivo de salida.|  
  
### Varios  
  
|Opción|Propósito|  
|------------|---------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|Especifica un archivo de respuesta.|  
|[\/?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Enumera las opciones del compilador para stdout.|  
|[\/baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|Especifica la dirección base preferida para cargar una DLL.|  
|[\/codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|Especifica la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.|  
|[\/help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Enumera las opciones del compilador para stdout.|  
|[\/highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|Especifica que el archivo ejecutable es compatible con la selección aleatoria del diseño del espacio de direcciones \(ASLR\).|  
|[\/langversion](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|Especifica el modo de versión de lenguaje: ISO\-1, ISO\-2, 3, 4, 5, 6 o Default.|  
|[\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|Especifica la ubicación del método **Main**.|  
|[\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|Indica al compilador que no debe compilar con csc.rsp.|  
|[\/nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|Suprime la información de titular del compilador.|  
|[\/recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|Busca los archivos de origen que se deben compilar en los subdirectorios.|  
|[\/subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|Especifica la versión mínima del subsistema que puede usar el archivo ejecutable.|  
|[\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|Habilita la compilación del código que usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).|  
|[\/utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|Muestra los resultados del compilador en codificación UTF\-8.|  
|`/parallel[+&#124;-]`|Especifica si se debe usar la compilación simultánea \(\+\).|  
|`/checksumalgorithm:<alg>`|Especifica el algoritmo para calcular la suma de comprobación del archivo de origen almacenado en el archivo PDB.  Los valores admitidos son: SHA1 \(predeterminado\) o SHA256.|  
  
## Opciones obsoletas  
  
|||  
|-|-|  
|**\/incremental**|Habilita la compilación incremental.|  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [C\# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)