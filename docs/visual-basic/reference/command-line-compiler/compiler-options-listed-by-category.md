---
title: "Opciones del compilador de Visual Basic ordenadas por categoría | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
caps.latest.revision: 24
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9c379a937f798a02badd7b7cd8470f2e1ce3b072
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-compiler-options-listed-by-category"></a>Opciones del compilador de Visual Basic, por categoría
El compilador de línea de comandos [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] se ofrece como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]. La siguiente es una lista de las opciones de línea de comandos del compilador [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] clasificadas por categoría funcional.  
  
## <a name="compiler-output"></a>Resultado de compilación  
  
|Opción|Propósito|  
|---|---|  
|[/nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Suprime la información de titular del compilador.|  
|[/utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Muestra los resultados del compilador en codificación UTF-8.|  
|[/verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Muestra información adicional durante la compilación.|  
|`/modulename:<string>`|Especifica el nombre del módulo de origen.|  
|[/preferreduilang](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|Especifica un idioma para los resultados del compilador.|  
  
## <a name="optimization"></a>Optimización  
  
|Opción|Propósito|  
|---|---|  
|[/filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Especifica dónde se alinean las secciones del archivo de salida.|  
|[/optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Habilita o deshabilita las optimizaciones.|  
  
## <a name="output-files"></a>Archivos de resultados  
  
|Opción|Propósito|  
|---|---|  
|[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Procesa los comentarios de documentación generando un archivo XML.|  
|[/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Establece el compilador con destino en [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].|  
|[/out](../../../visual-basic/reference/command-line-compiler/out.md)|Especifica un directorio de salida.|  
|[/target](../../../visual-basic/reference/command-line-compiler/target.md)|Especifica el formato de la salida.|  
  
## <a name="net-assemblies"></a>Ensamblados .NET  
  
|Opción|Propósito|  
|---|---|  
|[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.|  
|[/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Especifica si el ensamblado estará firmado total o parcialmente.|  
|[/imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Importa un espacio de nombres desde un ensamblado especificado.|  
|[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.|  
|[/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.|  
|[/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Especifica la ubicación de ensamblados al que hace referencia el [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) opción.|  
|[/reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Importa metadatos de un ensamblado.|  
|[/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Especifica el nombre del ensamblado del que un módulo formará parte.|  
|`/analyzer`|Ejecuta los analizadores de este ensamblado (forma abreviada: /a).|  
|`/additionalfile`|Asigna nombre a otros archivos que no afectan directamente a la generación de código, pero que los analizadores pueden usar para generar errores o advertencias.|  
  
## <a name="debuggingerror-checking"></a>Comprobación de errores y depuración  
  
|Opción|Propósito|  
|---|---|  
|[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Crea un archivo que contiene información que permite notificar un error fácilmente.|  
|[/debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Crea información de depuración.|  
|[/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Suprime la capacidad del compilador para generar advertencias.|  
|[/quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.|  
|[/removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Deshabilita las comprobaciones de desbordamiento con enteros.|  
|[/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Promueve las advertencias a errores.|  
|`/ruleset:<file>`|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|  
  
## <a name="help"></a>Ayuda  
  
|Opción|Propósito|  
|---|---|  
|[/?](../../../visual-basic/reference/command-line-compiler/help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `/help`. No se produce ninguna compilación.|  
|[/Help](../../../visual-basic/reference/command-line-compiler/help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `/?`. No se produce ninguna compilación.|  
  
## <a name="language"></a>Lenguaje  
  
|Opción|Propósito|  
|---|---|  
|[/langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Especificar la versión de idioma: 9 | 9.0 | 10 | 10.0 | 11 | 11.0.|  
|[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Exige la declaración explícita de variables.|  
|[/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Exige la semántica de tipos estricta.|  
|[/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Especifica si las comparaciones de cadenas deben ser binarias o usar la semántica de texto específica de la configuración regional.|  
|[/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.|  
  
## <a name="preprocessor"></a>Preprocesador  
  
|Opción|Propósito|  
|---|---|  
|[/define](../../../visual-basic/reference/command-line-compiler/define.md)|Define símbolos de compilación condicional.|  
  
## <a name="resources"></a>Recursos  
  
|Opción|Propósito|  
|---|---|  
|[/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Crea un vínculo a un recurso administrado.|  
|[/resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Inserta un recurso administrado en un ensamblado.|  
|[/win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Inserta un archivo .ico en el archivo de salida.|  
|[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Inserta un recurso Win32 en el archivo de salida.|  
  
## <a name="miscellaneous"></a>Varios  
  
|Opción|Propósito|  
|---|---|  
|[@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Especifica un archivo de respuesta.|  
|[/baseaddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Especifica la dirección base de un archivo DLL.|  
|[/codepage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Especifica la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.|  
|[/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Especifica cómo debe documentar el compilador [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] los errores internos del compilador.|  
|[/highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Indica al kernel de Windows si un archivo ejecutable determinado admite selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.|  
|[/main](../../../visual-basic/reference/command-line-compiler/main.md)|Especifica la clase que contiene el `Sub``Main` procedimiento para usar durante el inicio.|  
|[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|No compila con Vbc.rsp.|  
|[/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Hace que el compilador no haga referencia a las bibliotecas estándar.|  
|[/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.|  
|[/platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Especifica la plataforma del procesador que el compilador destina para el archivo de salida.|  
|[/recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Busca en los subdirectorios los archivos de código fuente que se deben compilar.|  
|[/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Especifica un espacio de nombres para todas las declaraciones de tipos.|  
|[/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.|  
|[/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.|  
|[/win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.|  
|`/parallel[+&#124;-]`|Especifica si hay que usar la compilación simultánea (+).|  
|`/checksumalgorithm:<alg>`|Especifique el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.  Los valores admitidos son: SHA1 (predeterminado) o SHA256.|  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de Visual Basic ordenadas alfabéticamente](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically.md)   
 [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)   
 [Opciones del compilador de C# alfabético](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)   
 [Opciones del compilador de C#, por categoría](../../../csharp/language-reference/compiler-options/listed-by-category.md)
