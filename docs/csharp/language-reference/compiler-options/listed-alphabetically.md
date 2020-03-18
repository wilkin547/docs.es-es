---
title: Opciones del compilador de C#, por orden alfabético
ms.date: 05/15/2018
helpviewer_keywords:
- compiler options [C#], listed alphabetically
- C# language, compiler options listed alphabetically
- Visual C# compiler, options listed alphabetically
- Visual C#, compiler options listed alphabetically
ms.assetid: 43535ea0-ca47-4a15-b528-615087a86092
ms.openlocfilehash: d6d471cd27f35de6325a130e6c909d13cb1dcc85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73972740"
---
# <a name="c-compiler-options-listed-alphabetically"></a>Opciones del compilador de C#, por orden alfabético

Las siguientes opciones del compilador están ordenadas alfabéticamente. Para obtener una lista por categoría, vea [Opciones del compilador de C# por categoría](listed-by-category.md).

|Opción|Propósito|
|------------|-------------|
|[@](response-file-compiler-option.md)|Leer un archivo de respuesta para ver más opciones.|
|[-?](help-compiler-option.md)|Muestra un mensaje de uso a stdout.|
|-additionalfile|Asigna nombre a otros archivos que no afectan directamente a la generación de código, pero que los analizadores pueden usar para generar errores o advertencias.|
|[-addmodule](addmodule-compiler-option.md)|Vincula los módulos especificados en este ensamblado.|
|-analyzer|Ejecuta los analizadores de este ensamblado (forma abreviada: -a).|
|[/appconfig](appconfig-compiler-option.md)|Especifica la ubicación de app.config en el momento del enlace de ensamblado.|
|[-baseaddress](baseaddress-compiler-option.md)|Especifica la dirección base de la biblioteca que se compilará.|
|[-bugreport](bugreport-compiler-option.md)|Crea un archivo 'Informe de errores'. Este archivo se enviará junto con la información de bloqueo si se usa con -errorreport:prompt o -errorreport:send.|
|[/checked](checked-compiler-option.md)|Hace que el compilador genere comprobaciones de desbordamiento.|
|-checksumalgorithm:\<alg>|Especifica el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.  Los valores admitidos son: SHA256 (valor predeterminado) o SHA1.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256. |
|[-codepage](codepage-compiler-option.md)|Especifica la página de códigos que se va a utilizar cuando se abren los archivos de código fuente.|
|[-debug](debug-compiler-option.md)|Emite información de depuración.|
|[-define](define-compiler-option.md)|Define símbolos de compilación condicional.|
|[-delaysign](delaysign-compiler-option.md)|Retrasa la firma del ensamblado usando solo la parte pública de la clave de nombre seguro.|
|[-deterministic](deterministic-compiler-option.md)|Hace que el compilador genere un ensamblado cuyo contenido binario es idéntico en todas las compilaciones si las entradas son idénticas.|
|[-doc](doc-compiler-option.md)|Especifica un archivo de documentación XML que se generará.|
|-embed|Insertar todos los archivos de origen en el archivo PDB|
|-embed:\<lista de archivos>|Insertar archivos específicos en el archivo PDB|
|-errorendlocation|Línea y columna de salida de la ubicación final de cada error.|
|-errorlog:\<archivo>|Especifique un archivo para registrar todos los diagnósticos del compilador y el analizador.|
|[-errorreport](errorreport-compiler-option.md)|Especifica cómo tratar los errores internos del compilador: prompt, send o none. El valor predeterminado es none.|
|[-filealign](filealign-compiler-option.md)|Especifica la alineación usada para las secciones de archivos de salida.|
|[/fullpaths](fullpaths-compiler-option.md)|Hace que el compilador genere rutas de acceso completas.|
|[-help](help-compiler-option.md)|Muestra un mensaje de uso a stdout.|
|[-highentropyva](highentropyva-compiler-option.md)|Especifica que se admite el ASLR de alta entropía.|
|-incremental|Habilita la compilación incremental [obsoleto].|
|[-keycontainer](keycontainer-compiler-option.md)|Especifica un contenedor de claves de nombre seguro.|
|[-keyfile](keyfile-compiler-option.md)|Especifica un archivo de clave de nombre seguro.|
|[-langversion:\<string>](langversion-compiler-option.md)|Especifique la versión de lenguaje: predeterminada, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3 o más reciente |
|[/lib](lib-compiler-option.md)|Especifica más directorios donde buscar referencias.|
|[-link](link-compiler-option.md)|Hace que la información de tipo COM de ensamblados específicos esté disponible en el proyecto.|
|[-linkresource](linkresource-compiler-option.md)|Vincula el recurso especificado a este ensamblado.|
|[-main](main-compiler-option.md)|Especifica el tipo que contiene el punto de entrada (se pasan por alto los demás puntos de entrada posibles).|
|[-moduleassemblyname](moduleassemblyname-compiler-option.md)|Especifica un ensamblado con tipos no públicos a los que puede acceder un archivo .netmodule.|
|-modulename:\<string>|Especifica el nombre del módulo de origen.|
|[-noconfig](noconfig-compiler-option.md)|Indica al compilador que no incluya el archivo CSC.RSP de forma automática.|
|[-nologo](nologo-compiler-option.md)|Suprime el mensaje de copyright del compilador.|
|[-nostdlib](nostdlib-compiler-option.md)|Indica al compilador que no haga referencia a la biblioteca estándar (mscorlib.dll).|
|[-nowarn](nowarn-compiler-option.md)|Deshabilita mensajes de advertencia específicos.|
|[-nowin32manifest](nowin32manifest-compiler-option.md)|Indica al compilador que no incruste un manifiesto de la aplicación en el archivo ejecutable.|
|[-optimize](optimize-compiler-option.md)|Habilita o deshabilita las optimizaciones.|
|[-out](out-compiler-option.md)|Especifica el nombre de archivo de salida (nombre predeterminado: nombre base de archivo con la clase principal o del primer archivo).|
|-parallel[+&#124;-]|Especifica si hay que usar la compilación simultánea (+).|
|[-pathmap](pathmap-compiler-option.md)|Especifica una asignación para los nombres de rutas de acceso de origen generados por el compilador.|
|[/pdb](pdb-compiler-option.md)|Especifica el nombre y la ubicación de archivo del archivo .pdb.|
|[-platform](platform-compiler-option.md)|Limita las plataformas en las que se puede ejecutar este código: x86, Itanium, x64, anycpu o anycpu32bitpreferred. El valor predeterminado es anycpu.|
|[/preferreduilang](preferreduilang-compiler-option.md)|Especifica el idioma que se usará para los resultados del compilador.|
|[-publicsign](publicsign-compiler-option.md)|Aplica una clave pública sin firmar el ensamblado, pero establece el bit en el ensamblado lo que indica que el ensamblado está firmado.|
|[-recurse](recurse-compiler-option.md)|Incluye todos los archivos del directorio y subdirectorios actuales de acuerdo con las especificaciones de los comodines.|
|[-reference](reference-compiler-option.md)|Hace referencia a los metadatos de los archivos de ensamblado especificados.|
|[/refout](refout-compiler-option.md)|Genere un ensamblado de referencia además del ensamblado principal.|
|[/refonly](refonly-compiler-option.md)|Genere un ensamblado de referencia en lugar del ensamblado principal.|
|-reportanalyzer|Notifica información adicional del analizador, como el tiempo de ejecución.|
|[-resource](resource-compiler-option.md)|Incrusta el recurso especificado.|
|-ruleset:\<file>|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Especifica la versión mínima del subsistema que el archivo ejecutable puede usar.|
|[-target](target-compiler-option.md)|Especifica el formato del archivo de salida con una de las seis opciones siguientes: [-target:appcontainerexe](target-appcontainerexe-compiler-option.md), [-target:exe](target-exe-compiler-option.md), [-target:library](target-library-compiler-option.md), [-target:module](target-module-compiler-option.md), [-target:winexe](target-winexe-compiler-option.md), [-target:winmdobj](target-winmdobj-compiler-option.md).|
|[/unsafe](unsafe-compiler-option.md)|Permite código [no seguro](../keywords/unsafe.md).|
|[-utf8output](utf8output-compiler-option.md)|Genera mensajes del compilador en codificación UTF-8.|
|-version|Muestra el número de versión del compilador y se cierra.|
|[/warn](warn-compiler-option.md)|Establece el nivel de advertencia (0-4).|
|[-warnaserror](warnaserror-compiler-option.md)|Notifica advertencias específicas como errores.|
|[-win32icon](win32icon-compiler-option.md)|Usa este icono para los resultados.|
|[-win32manifest](win32manifest-compiler-option.md)|Especifica un archivo de manifiesto win32 personalizado.|
|[/win32res:](win32res-compiler-option.md)|Especifica el archivo de recursos win32 (.res).|

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](index.md)
- [Opciones del compilador de C#, por categoría](listed-by-category.md)
- [Establecimiento de variables de entorno para la línea de comandos de Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
- [Elemento \<compiler>](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)
