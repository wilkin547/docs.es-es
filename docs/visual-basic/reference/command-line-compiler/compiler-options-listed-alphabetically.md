---
title: Opciones del compilador por orden alfabético
ms.date: 04/12/2018
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: e67febba-bacf-4e1f-a143-c141e063f90e
ms.openlocfilehash: 19e14953c08f90ea1ab245fa3124a462ccba162f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408743"
---
# <a name="visual-basic-compiler-options-listed-alphabetically"></a>Opciones del compilador de Visual Basic, por orden alfabético
El compilador de línea de comandos de Visual Basic se ofrece como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de Visual Studio. La siguiente es una lista de las opciones de línea de comandos del compilador de Visual Basic ordenadas alfabéticamente.  

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]
  
|Opción|Propósito|  
|------------|-------------|  
|[@ (especificar archivo de respuesta)](specify-response-file.md)|Especifica un archivo de respuesta.|  
|[-?](help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `-help`. No se produce ninguna compilación.|  
|`-additionalfile`|Asigna nombre a otros archivos que no afectan directamente a la generación de código, pero que los analizadores pueden usar para generar errores o advertencias.|  
|[-addmodule](addmodule.md)|Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.|  
|`-analyzer`|Ejecuta los analizadores de este ensamblado (forma abreviada: -a).|  
|[-baseaddress](baseaddress.md)|Especifica la dirección base de un archivo DLL.|  
|[-bugreport](bugreport.md)|Crea un archivo que contiene información que permite notificar un error fácilmente.|  
|`-checksumalgorithm:<alg>`|Especifique el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.  Los valores admitidos son: SHA1 (el predeterminado) o SHA256. <br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256 o superior.|  
|[-codepage](codepage.md)|Especifica la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.|  
|[-debug](debug.md)|Crea información de depuración.|  
|[-define](define.md)|Define símbolos de compilación condicional.|  
|[-delaysign](delaysign.md)|Especifica si el ensamblado estará firmado total o parcialmente.|  
|[-deterministic](deterministic.md)|Hace que el compilador genere un ensamblado cuyo contenido binario es idéntico en todas las compilaciones si las entradas son idénticas.|
|[-doc](doc.md)|Procesa los comentarios de documentación generando un archivo XML.|  
|[-errorreport](errorreport.md)|Especifica cómo debe documentar el compilador de Visual Basic los errores internos del compilador.|  
|[-filealign](filealign.md)|Especifica dónde se alinean las secciones del archivo de salida.|  
|[-help](help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `-?`. No se produce ninguna compilación.|  
|[-highentropyva](highentropyva.md)|Indica si un archivo ejecutable determinado admite selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.|  
|[-imports](imports.md)|Importa un espacio de nombres desde un ensamblado especificado.|  
|[-keycontainer](keycontainer.md)|Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.|  
|[-keyfile](keyfile.md)|Especifica un archivo que contiene una clave o un par de claves para asignar un nombre seguro al ensamblado.|  
|[-langversion](langversion.md)|Especifique la versión de lenguaje: 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.|  
|[-libpath](libpath.md)|Especifica la ubicación de los ensamblados a los que se hace referencia con la opción [-reference](reference.md).|  
|[-linkresource](linkresource.md)|Crea un vínculo a un recurso administrado.|  
|[-main](main.md)|Especifica la clase que contiene el procedimiento `Sub Main` que se usa en el inicio.|  
|[-moduleassemblyname](moduleassemblyname.md)|Especifica el nombre del ensamblado del que un módulo formará parte.|  
|`-modulename:<string>`|Especifica el nombre del módulo de origen.|  
|[-netcf](netcf.md)|Establece que el compilador tenga como destino .NET Compact Framework.|  
|[-noconfig](noconfig.md)|No compila con Vbc.rsp.|  
|[-nologo](nologo.md)|Suprime la información de titular del compilador.|  
|[-nostdlib](nostdlib.md)|Hace que el compilador no haga referencia a las bibliotecas estándar.|  
|[-nowarn](nowarn.md)|Suprime la capacidad del compilador para generar advertencias.|  
|[-nowin32manifest](nowin32manifest.md)|Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.|  
|[-optimize](optimize.md)|Habilita o deshabilita la optimización de código.|  
|[-optioncompare](optioncompare.md)|Especifica si las comparaciones de cadenas deben ser binarias o usar la semántica de texto específica de la configuración regional.|  
|[-optionexplicit](optionexplicit.md)|Exige la declaración explícita de variables.|  
|[-optioninfer](optioninfer.md)|Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.|  
|[-optionstrict](optionstrict.md)|Exige una semántica de lenguaje estricta.|  
|[-out](out.md)|Especifica un directorio de salida.|  
|<code>-parallel[+&#124;-]</code>|Especifica si hay que usar la compilación simultánea (+).|  
|[-platform](platform.md)|Especifica la plataforma del procesador que el compilador destina para el archivo de salida.|  
|`-preferreduilang`|Especifique el nombre del lenguaje de salida preferido.|  
|[-quiet](quiet.md)|Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.|  
|[-recurse](recurse.md)|Busca en los subdirectorios los archivos de código fuente que se deben compilar.|  
|[-reference](reference.md)|Importa metadatos de un ensamblado.|  
|[/refonly](refonly-compiler-option.md)|Genera solo un ensamblado de referencia.|
|[/refout](refout-compiler-option.md)|Especifica la ruta de acceso de salida de un ensamblado de referencia.|
|[-removeintchecks](removeintchecks.md)|Deshabilita las comprobaciones de desbordamiento con enteros.|  
|[-resource](resource.md)|Inserta un recurso administrado en un ensamblado.|  
|[-rootnamespace](rootnamespace.md)|Especifica un espacio de nombres para todas las declaraciones de tipos.|  
|`-ruleset:<file>`|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|  
|[-sdkpath](sdkpath.md)|Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.|  
|[-subsystemversion](subsystemversion.md)|Especifica la versión mínima del subsistema que el archivo ejecutable generado puede utilizar.|  
|[-target](target.md)|Especifica el formato de la salida.|  
|[-utf8output](utf8output.md)|Muestra los resultados del compilador en codificación UTF-8.|  
|[-vbruntime](vbruntime.md)|Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.|  
|[-verbose](verbose.md)|Muestra información adicional durante la compilación.|  
|[-warnaserror](warnaserror.md)|Promueve las advertencias a errores.|  
|[-win32icon](win32icon.md)|Inserta un archivo .ico en el archivo de salida.|  
|[-win32manifest](win32manifest.md)|Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.|  
|[-win32resource](win32resource.md)|Inserta un recurso Win32 en el archivo de salida.|  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de Visual Basic, por categoría](compiler-options-listed-by-category.md)
- [Administración de propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
