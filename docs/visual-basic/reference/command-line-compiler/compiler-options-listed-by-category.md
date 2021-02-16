---
description: 'Más información acerca de: Opciones del compilador de Visual Basic, por categoría'
title: Opciones del compilador por categoría
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
ms.openlocfilehash: f0535e2aa94cda96610acb0edb24f6d46cc4afa0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474179"
---
# <a name="visual-basic-compiler-options-listed-by-category"></a>Opciones del compilador de Visual Basic, por categoría

El compilador de línea de comandos de Visual Basic se ofrece como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio. La siguiente es una lista de las opciones de línea de comandos del compilador de Visual Basic clasificadas por categoría funcional.  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
## <a name="compiler-output"></a>Salida del compilador  
  
|Opción|Propósito|  
|---|---|  
|[-nologo](nologo.md)|Suprime la información de titular del compilador.|  
|[-utf8output](utf8output.md)|Muestra los resultados del compilador en codificación UTF-8.|  
|[-verbose](verbose.md)|Muestra información adicional durante la compilación.|  
|`-modulename:<string>`|Especifica el nombre del módulo de origen.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Especifica un idioma para los resultados del compilador.|
  
## <a name="optimization"></a>Optimización  
  
|Opción|Propósito|  
|---|---|  
|[-filealign](filealign.md)|Especifica dónde se alinean las secciones del archivo de salida.|  
|[-optimize](optimize.md)|Habilita o deshabilita las optimizaciones.|  
  
## <a name="output-files"></a>archivos de salida  
  
|Opción|Propósito|  
|---|---|  
|[-doc](doc.md)|Procesa los comentarios de documentación generando un archivo XML.|  
|[-deterministic](deterministic.md)|Hace que el compilador genere un ensamblado cuyo contenido binario es idéntico en todas las compilaciones si las entradas son idénticas.|
|[-netcf](netcf.md)|Establece que el compilador tenga como destino .NET Compact Framework.|  
|[-out](out.md)|Especifica un directorio de salida.|  
|[/refonly](refonly-compiler-option.md)|Genera solo un ensamblado de referencia.|
|[/refout](refout-compiler-option.md)|Especifica la ruta de acceso de salida de un ensamblado de referencia.|
|[-target](target.md)|Especifica el formato de la salida.|  
  
## <a name="net-assemblies"></a>Ensamblados .NET  
  
|Opción|Propósito|  
|---|---|  
|[-addmodule](addmodule.md)|Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.|  
|[-delaysign](delaysign.md)|Especifica si el ensamblado estará firmado total o parcialmente.|  
|[-imports](imports.md)|Importa un espacio de nombres desde un ensamblado especificado.|  
|[-keycontainer](keycontainer.md)|Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.|  
|[-keyfile](keyfile.md)|Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.|  
|[-libpath](libpath.md)|Especifica la ubicación de los ensamblados a los que se hace referencia con la opción [-reference](reference.md).|  
|[-reference](reference.md)|Importa metadatos de un ensamblado.|  
|[-moduleassemblyname](moduleassemblyname.md)|Especifica el nombre del ensamblado del que un módulo formará parte.|  
|`-analyzer`|Ejecuta los analizadores de este ensamblado (forma abreviada: -a).|  
|`-additionalfile`|Asigna nombre a otros archivos que no afectan directamente a la generación de código, pero que los analizadores pueden usar para generar errores o advertencias.|  
  
## <a name="debuggingerror-checking"></a>Comprobación de errores y depuración  
  
|Opción|Propósito|  
|---|---|  
|[-bugreport](bugreport.md)|Crea un archivo que contiene información que permite notificar un error fácilmente.|  
|[-debug](debug.md)|Crea información de depuración.|  
|[-nowarn](nowarn.md)|Suprime la capacidad del compilador para generar advertencias.|  
|[-quiet](quiet.md)|Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.|  
|[-removeintchecks](removeintchecks.md)|Deshabilita las comprobaciones de desbordamiento con enteros.|  
|[-warnaserror](warnaserror.md)|Promueve las advertencias a errores.|  
|`-ruleset:<file>`|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|  
  
## <a name="help"></a>Ayuda  
  
|Opción|Propósito|  
|---|---|  
|[-?](help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `-help`. No se produce ninguna compilación.|  
|[-help](help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `-?`. No se produce ninguna compilación.|  
  
## <a name="language"></a>Lenguaje  
  
|Opción|Propósito|  
|---|---|  
|[-langversion](langversion.md)|Especifique la versión de lenguaje: 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.|  
|[-optionexplicit](optionexplicit.md)|Exige la declaración explícita de variables.|  
|[-optionstrict](optionstrict.md)|Exige la semántica de tipos estricta.|  
|[-optioncompare](optioncompare.md)|Especifica si las comparaciones de cadenas deben ser binarias o usar la semántica de texto específica de la configuración regional.|  
|[-optioninfer](optioninfer.md)|Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.|  
  
## <a name="preprocessor"></a>Preprocesador  
  
|Opción|Propósito|  
|---|---|  
|[-define](define.md)|Define símbolos de compilación condicional.|  
  
## <a name="resources"></a>Recursos  
  
|Opción|Propósito|  
|---|---|  
|[-linkresource](linkresource.md)|Crea un vínculo a un recurso administrado.|  
|[-resource](resource.md)|Inserta un recurso administrado en un ensamblado.|  
|[-win32icon](win32icon.md)|Inserta un archivo .ico en el archivo de salida.|  
|[-win32resource](win32resource.md)|Inserta un recurso Win32 en el archivo de salida.|  
  
## <a name="miscellaneous"></a>Varios  
  
|Opción|Propósito|  
|---|---|  
|[@ (especificar archivo de respuesta)](specify-response-file.md)|Especifica un archivo de respuesta.|  
|[-baseaddress](baseaddress.md)|Especifica la dirección base de un archivo DLL.|  
|[-codepage](codepage.md)|Especifica la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.|  
|[-errorreport](errorreport.md)|Especifica cómo debe documentar el compilador de Visual Basic los errores internos del compilador.|  
|[-highentropyva](highentropyva.md)|Indica al kernel de Windows si un archivo ejecutable determinado admite selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.|  
|[-main](main.md)|Especifica la clase que contiene el procedimiento `Sub Main` que se usa en el inicio.|  
|[-noconfig](noconfig.md)|No compila con Vbc.rsp.|  
|[-nostdlib](nostdlib.md)|Hace que el compilador no haga referencia a las bibliotecas estándar.|  
|[-nowin32manifest](nowin32manifest.md)|Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.|  
|[-platform](platform.md)|Especifica la plataforma del procesador que el compilador destina para el archivo de salida.|  
|[-recurse](recurse.md)|Busca en los subdirectorios los archivos de código fuente que se deben compilar.|  
|[-rootnamespace](rootnamespace.md)|Especifica un espacio de nombres para todas las declaraciones de tipos.|  
|[-sdkpath](sdkpath.md)|Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.|  
|[-vbruntime](vbruntime.md)|Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.|  
|[-win32manifest](win32manifest.md)|Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.|  
|`-parallel[+&#124;-]`|Especifica si hay que usar la compilación simultánea (+).|  
|`-checksumalgorithm:<alg>`|Especifique el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.  Los valores admitidos son: SHA1 (el predeterminado) o SHA256. <br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256 o superior.|  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de Visual Basic, por orden alfabético](compiler-options-listed-alphabetically.md)
- [Administración de propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
