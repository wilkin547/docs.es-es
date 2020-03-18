---
title: Opciones del compilador de C#, por categoría
ms.date: 05/15/2018
helpviewer_keywords:
- Visual C# compiler, options listed by category
- compiler options [C#], listed by category
- Visual C#, compiler options listed by category
ms.assetid: 96437ecc-6502-4cd3-b070-e9386a298e83
ms.openlocfilehash: 5cd5607c25dabd8f56ebb58366116666e8e649ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73972712"
---
# <a name="c-compiler-options-listed-by-category"></a>Opciones del compilador de C#, por categoría

Las opciones del compilador siguientes están ordenadas por categoría. Para acceder a una lista en orden alfabético, vea [Opciones del compilador de C#, por orden alfabético](listed-alphabetically.md).

## <a name="optimization"></a>Optimización

|Opción|Propósito|
|------------|-------------|
|[-filealign](filealign-compiler-option.md)|Especifica el tamaño de las secciones del archivo de salida.|
|[-optimize](optimize-compiler-option.md)|Habilita o deshabilita las optimizaciones.|

## <a name="output-files"></a>Archivos de resultados

|Opción|Propósito|
|------------|-------------|
|[-deterministic](deterministic-compiler-option.md)|Hace que el compilador genere un ensamblado cuyo contenido binario es idéntico en todas las compilaciones si las entradas son idénticas.|
|[-doc](doc-compiler-option.md)|Especifica un archivo XML donde se escribirán comentarios de documentación procesados.|
|[-out](out-compiler-option.md)|Especifica el archivo de salida.|
|[-pathmap](pathmap-compiler-option.md)|Especifica una asignación para los nombres de rutas de acceso de origen generados por el compilador|
|[/pdb](pdb-compiler-option.md)|Especifica el nombre y la ubicación de archivo del archivo .pdb.|
|[-platform](platform-compiler-option.md)|Especifica la plataforma de salida.|
|[/preferreduilang](preferreduilang-compiler-option.md)|Especifica un idioma para los resultados del compilador.|
|[/refout](refout-compiler-option.md)|Genere un ensamblado de referencia además del ensamblado principal.|
|[/refonly](refonly-compiler-option.md)|Genere un ensamblado de referencia en lugar del ensamblado principal.|
|[-target](target-compiler-option.md)|Especifica el formato del archivo de salida con una de estas cinco opciones: [-target:appcontainerexe](target-appcontainerexe-compiler-option.md), [-target:exe](target-exe-compiler-option.md), [-target:library](target-library-compiler-option.md), [-target:module](target-module-compiler-option.md), [-target:winexe](target-winexe-compiler-option.md) o [-target:winmdobj](target-winmdobj-compiler-option.md).|
|-modulename:\<string>|Especifica el nombre del módulo de origen.|

## <a name="net-framework-assemblies"></a>Ensamblados de .NET Framework

|Opción|Propósito|
|------------|-------------|
|[-addmodule](addmodule-compiler-option.md)|Especifica uno o varios módulos que formarán parte de este ensamblado.|
|[-delaysign](delaysign-compiler-option.md)|Indica al compilador que debe agregar la clave pública y mantener el ensamblado sin firma.|
|[-keycontainer](keycontainer-compiler-option.md)|Especifica el nombre del contenedor de claves criptográficas.|
|[-keyfile](keyfile-compiler-option.md)|Especifica el nombre de archivo que contiene la clave criptográfica.|
|[/lib](lib-compiler-option.md)|Especifica la ubicación de los ensamblados a los que se hace referencia mediante [-reference](reference-compiler-option.md).|
|[-nostdlib](nostdlib-compiler-option.md)|Indica al compilador que no debe importar la biblioteca estándar (mscorlib.dll).|
|[-publicsign](publicsign-compiler-option.md)|Aplica una clave pública sin firmar el ensamblado, pero establece el bit en el ensamblado lo que indica que el ensamblado está firmado.|
|[-reference](reference-compiler-option.md)|Importa los metadatos de un archivo que contiene un ensamblado.|
|-analyzer|Ejecuta los analizadores de este ensamblado (forma abreviada: /a).|
|-additionalfile|Asigna nombre a otros archivos que no afectan directamente a la generación de código, pero que los analizadores pueden usar para generar errores o advertencias.|
|-embed|Insertar todos los archivos de origen en el archivo PDB|
|-embed:\<lista de archivos>|Insertar archivos específicos en el archivo PDB|
## <a name="debuggingerror-checking"></a>Comprobación de errores y depuración

|Opción|Propósito|
|------------|-------------|
|[-bugreport](bugreport-compiler-option.md)|Crea un archivo que contiene información que permite notificar un error fácilmente.|
|[/checked](checked-compiler-option.md)|Especifica si la aritmética de enteros que desborda los límites del tipo de datos iniciará una excepción en tiempo de ejecución.|
|[-debug](debug-compiler-option.md)|Indica al compilador que debe emitir la información de depuración.|
|[-errorreport](errorreport-compiler-option.md)|Establece el comportamiento de los informes de errores.|
|[/fullpaths](fullpaths-compiler-option.md)|Especifica la ruta de acceso absoluta al archivo en los resultados del compilador.|
|[-nowarn](nowarn-compiler-option.md)|Suprime la generación de advertencias especificadas en el compilador.|
|[/warn](warn-compiler-option.md)|Establece el nivel de advertencia.|
|[-warnaserror](warnaserror-compiler-option.md)|Promueve las advertencias a errores.|
|-ruleset:\<file>|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|

## <a name="preprocessor"></a>Preprocesador

|Opción|Propósito|
|------------|-------------|
|[-define](define-compiler-option.md)|Define los símbolos de preprocesador.|

## <a name="resources"></a>Recursos

|Opción|Propósito|
|------------|-------------|
|[-link](link-compiler-option.md)|Hace que la información de tipo COM de ensamblados específicos esté disponible en el proyecto.|
|[-linkresource](linkresource-compiler-option.md)|Crea un vínculo a un recurso administrado.|
|[-resource](resource-compiler-option.md)|Incrusta un recurso de .NET Framework en el archivo de salida.|
|[-win32icon](win32icon-compiler-option.md)|Especifica un archivo .ico para insertarlo en el archivo de salida.|
|[/win32res:](win32res-compiler-option.md)|Especifica un recurso Win32 para insertarlo en el archivo de salida.|

## <a name="miscellaneous"></a>Varios

|Opción|Propósito|
|------------|-------------|
|[@](response-file-compiler-option.md)|Especifica un archivo de respuesta.|
|[-?](help-compiler-option.md)|Enumera las opciones del compilador para stdout.|
|[-baseaddress](baseaddress-compiler-option.md)|Especifica la dirección base preferida para cargar una DLL.|
|[-codepage](codepage-compiler-option.md)|Especifica la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.|
|[-help](help-compiler-option.md)|Enumera las opciones del compilador para stdout.|
|[-highentropyva](highentropyva-compiler-option.md)|Especifica que el archivo ejecutable es compatible con la selección aleatoria del diseño del espacio de direcciones (ASLR).|
|[-langversion](langversion-compiler-option.md)|Especifica la versión de lenguaje: valor predeterminado, ISO-1, ISO-2, 3, 4, 5, 6, 7, 7.1, 7.2, 7.3 o el más reciente |
|[-main](main-compiler-option.md)|Especifica la ubicación del método **Main**.|
|[-noconfig](noconfig-compiler-option.md)|Indica al compilador que no debe compilar con csc.rsp.|
|[-nologo](nologo-compiler-option.md)|Suprime la información de titular del compilador.|
|[-recurse](recurse-compiler-option.md)|Busca en los subdirectorios los archivos de código fuente que se deben compilar.|
|[-subsystemversion](subsystemversion-compiler-option.md)|Especifica la versión mínima del subsistema que el archivo ejecutable puede usar.|
|[/unsafe](unsafe-compiler-option.md)|Habilita la compilación del código que usa la palabra clave [unsafe](../keywords/unsafe.md).|
|[-utf8output](utf8output-compiler-option.md)|Muestra los resultados del compilador en codificación UTF-8.|
|-parallel[+&#124;-]|Especifica si hay que usar la compilación simultánea (+).|
|-checksumalgorithm:\<alg>|Especifique el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.  Los valores admitidos son: SHA1 (predeterminado) o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|

## <a name="obsolete-options"></a>Opciones obsoletas

|Opción|Propósito|
|---|---|
|-incremental|Habilita la compilación incremental.|

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](index.md)
- [Opciones del compilador de C#, por orden alfabético](listed-alphabetically.md)
- [Establecimiento de variables de entorno para la línea de comandos de Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md)
