---
title: "Opciones del compilador de C#, por categoría"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 8e8d01587ccde967b8484b3b61916f8cf437f6c0
ms.openlocfilehash: 584d0cb249644e6b4ffe15e115c49256f5fa2716
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="c-compiler-options-listed-by-category"></a>Opciones del compilador de C#, por categoría
Las opciones del compilador siguientes están ordenadas por categoría. Para acceder a una lista en orden alfabético, vea [Opciones del compilador de C#, por orden alfabético](../../../csharp/language-reference/compiler-options/listed-alphabetically.md).  
  
### <a name="optimization"></a>Optimización  
  
|Opción|Propósito|  
|------------|-------------|  
|[/filealign](../../../csharp/language-reference/compiler-options/filealign-compiler-option.md)|Especifica el tamaño de las secciones del archivo de salida.|  
|[/optimize](../../../csharp/language-reference/compiler-options/optimize-compiler-option.md)|Habilita o deshabilita las optimizaciones.|  
  
### <a name="output-files"></a>Archivos de resultados  
  
|Opción|Finalidad|  
|------------|-------------|  
|[/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)|Especifica un archivo XML donde se escribirán comentarios de documentación procesados.|  
|[/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md)|Especifica el archivo de salida.|  
|[/pdb](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md)|Especifica el nombre y la ubicación de archivo del archivo .pdb.|  
|[/platform](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)|Especifica la plataforma de salida.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Especifica un idioma para los resultados del compilador.|  
|[/refout](refout-compiler-option.md)|Genere un ensamblado de referencia además del ensamblado principal.|  
|[/refonly](refonly-compiler-option.md)|Genere un ensamblado de referencia en lugar del ensamblado principal.|  
|[/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)|Especifica el formato del archivo de salida con una de las seis opciones siguientes: [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md), [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md), [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md) o [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md).|  
|/modulename:\<string>|Especifica el nombre del módulo de origen.|  
  
### <a name="net-framework-assemblies"></a>Ensamblados de .NET Framework  
  
|Opción|Propósito|  
|------------|-------------|  
|[/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)|Especifica uno o varios módulos que formarán parte de este ensamblado.|  
|[/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)|Indica al compilador que debe agregar la clave pública y mantener el ensamblado sin firma.|  
|[/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md)|Especifica el nombre del contenedor de claves criptográficas.|  
|[/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)|Especifica el nombre de archivo que contiene la clave criptográfica.|  
|[/lib](../../../csharp/language-reference/compiler-options/lib-compiler-option.md)|Especifica la ubicación de los ensamblados a los que se hace referencia con [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).|  
|[/nostdlib](../../../csharp/language-reference/compiler-options/nostdlib-compiler-option.md)|Indica al compilador que no debe importar la biblioteca estándar (mscorlib.dll).|  
|[/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)|Importa los metadatos de un archivo que contiene un ensamblado.|  
|/analyzer|Ejecuta los analizadores de este ensamblado (forma abreviada: /a).|  
|/additionalfile|Asigna nombre a otros archivos que no afectan directamente a la generación de código, pero que los analizadores pueden usar para generar errores o advertencias.|  
  
### <a name="debuggingerror-checking"></a>Comprobación de errores y depuración  
  
|Opción|Propósito|  
|------------|-------------|  
|[/bugreport](../../../csharp/language-reference/compiler-options/bugreport-compiler-option.md)|Crea un archivo que contiene información que permite notificar un error fácilmente.|  
|[/checked](../../../csharp/language-reference/compiler-options/checked-compiler-option.md)|Especifica si la aritmética de enteros que desborda los límites del tipo de datos iniciará una excepción en tiempo de ejecución.|  
|[/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)|Indica al compilador que debe emitir la información de depuración.|  
|[/errorreport](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)|Establece el comportamiento de los informes de errores.|  
|[/fullpaths](../../../csharp/language-reference/compiler-options/fullpaths-compiler-option.md)|Especifica la ruta de acceso absoluta al archivo en los resultados del compilador.|  
|[/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md)|Suprime la generación de advertencias especificadas en el compilador.|  
|[/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md)|Establece el nivel de advertencia.|  
|[/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md)|Promueve las advertencias a errores.|  
|/ruleset:\<file>|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|  
  
### <a name="preprocessor"></a>Preprocesador  
  
|Opción|Propósito|  
|------------|-------------|  
|[/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md)|Define los símbolos de preprocesador.|  
  
### <a name="resources"></a>Recursos  
  
|Opción|Propósito|  
|------------|-------------|  
|[/link](../../../csharp/language-reference/compiler-options/link-compiler-option.md)|Hace que la información de tipo COM de ensamblados específicos esté disponible en el proyecto.|  
|[/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md)|Crea un vínculo a un recurso administrado.|  
|[/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md)|Incrusta un recurso de .NET Framework en el archivo de salida.|  
|[/win32icon](../../../csharp/language-reference/compiler-options/win32icon-compiler-option.md)|Especifica un archivo .ico para insertarlo en el archivo de salida.|  
|[/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md)|Especifica un recurso Win32 para insertarlo en el archivo de salida.|  
  
### <a name="miscellaneous"></a>Varios  
  
|Opción|Propósito|  
|------------|-------------|  
|[@](../../../csharp/language-reference/compiler-options/response-file-compiler-option.md)|Especifica un archivo de respuesta.|  
|[/?](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Enumera las opciones del compilador para stdout.|  
|[/baseaddress](../../../csharp/language-reference/compiler-options/baseaddress-compiler-option.md)|Especifica la dirección base preferida para cargar una DLL.|  
|[/codepage](../../../csharp/language-reference/compiler-options/codepage-compiler-option.md)|Especifica la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.|  
|[/help](../../../csharp/language-reference/compiler-options/help-compiler-option.md)|Enumera las opciones del compilador para stdout.|  
|[/highentropyva](../../../csharp/language-reference/compiler-options/highentropyva-compiler-option.md)|Especifica que el archivo ejecutable es compatible con la selección aleatoria del diseño del espacio de direcciones (ASLR).|  
|[/langversion](../../../csharp/language-reference/compiler-options/langversion-compiler-option.md)|Especifica el modo de versión de lenguaje: valor predeterminado, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1 o el más reciente |  
|[/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md)|Especifica la ubicación del método **Main**.|  
|[/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)|Indica al compilador que no debe compilar con csc.rsp.|  
|[/nologo](../../../csharp/language-reference/compiler-options/nologo-compiler-option.md)|Suprime la información de titular del compilador.|  
|[/recurse](../../../csharp/language-reference/compiler-options/recurse-compiler-option.md)|Busca en los subdirectorios los archivos de código fuente que se deben compilar.|  
|[/subsystemversion](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)|Especifica la versión mínima del subsistema que el archivo ejecutable puede usar.|  
|[/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)|Habilita la compilación del código que usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).|  
|[/utf8output](../../../csharp/language-reference/compiler-options/utf8output-compiler-option.md)|Muestra los resultados del compilador en codificación UTF-8.|  
|/parallel[+&#124;-]|Especifica si hay que usar la compilación simultánea (+).|  
|/checksumalgorithm:\<alg>|Especifique el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.  Los valores admitidos son: SHA1 (predeterminado) o SHA256.|  
  
## <a name="obsolete-options"></a>Opciones obsoletas  
  
|Opción|Propósito|  
|---|---|  
|/incremental|Habilita la compilación incremental.|  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [C# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  (Opciones del compilador de C#, por orden alfabético)  
 [Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)

