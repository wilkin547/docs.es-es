---
title: "Opciones del compilador de Visual Basic, por orden alfabético"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: e67febba-bacf-4e1f-a143-c141e063f90e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92678a09f9b4dd9f35f4f5c0e5ecb00385b703d1
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="visual-basic-compiler-options-listed-alphabetically"></a>Opciones del compilador de Visual Basic, por orden alfabético
El compilador de línea de comandos [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] se ofrece como alternativa a la compilación de programas desde el entorno de desarrollo integrado (IDE) de [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]. La siguiente es una lista de las opciones de línea de comandos del compilador [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] ordenadas alfabéticamente.  
  
|Opción|Propósito|  
|------------|-------------|  
|[@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|Especifica un archivo de respuesta.|  
|[/?](../../../visual-basic/reference/command-line-compiler/help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `/help`. No se produce ninguna compilación.|  
|`/additionalfile`|Asigna nombre a otros archivos que no afectan directamente a la generación de código, pero que los analizadores pueden usar para generar errores o advertencias.|  
|[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)|Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.|  
|`/analyzer`|Ejecuta los analizadores de este ensamblado (forma abreviada: /a).|  
|[/baseaddress](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|Especifica la dirección base de un archivo DLL.|  
|[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)|Crea un archivo que contiene información que permite notificar un error fácilmente.|  
|`/checksumalgorithm:<alg>`|Especifique el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.  Los valores admitidos son: SHA1 (predeterminado) o SHA256.|  
|[/codepage](../../../visual-basic/reference/command-line-compiler/codepage.md)|Especifica la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.|  
|[/debug](../../../visual-basic/reference/command-line-compiler/debug.md)|Crea información de depuración.|  
|[/define](../../../visual-basic/reference/command-line-compiler/define.md)|Define símbolos de compilación condicional.|  
|[/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)|Especifica si el ensamblado estará firmado total o parcialmente.|  
|[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)|Procesa los comentarios de documentación generando un archivo XML.|  
|[/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)|Especifica cómo debe documentar el compilador [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] los errores internos del compilador.|  
|[/filealign](../../../visual-basic/reference/command-line-compiler/filealign.md)|Especifica dónde se alinean las secciones del archivo de salida.|  
|[/help](../../../visual-basic/reference/command-line-compiler/help.md)|Muestra las opciones del compilador. Este comando equivale a especificar la opción `/?`. No se produce ninguna compilación.|  
|[/highentropyva](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|Indica si un archivo ejecutable determinado admite selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.|  
|[/imports](../../../visual-basic/reference/command-line-compiler/imports.md)|Importa un espacio de nombres desde un ensamblado especificado.|  
|[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.|  
|[/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)|Especifica un archivo que contiene una clave o un par de claves para asignar un nombre seguro al ensamblado.|  
|[/langversion](../../../visual-basic/reference/command-line-compiler/langversion.md)|Especificar versión de lenguaje: 9 &#124; 9.0 &#124; 10 &#124; 10.0 &#124; 11 &#124; 11.0.|  
|[/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)|Especifica la ubicación de ensamblados al que hace referencia el [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) opción.|  
|[/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)|Crea un vínculo a un recurso administrado.|  
|[/main](../../../visual-basic/reference/command-line-compiler/main.md)|Especifica la clase que contiene el `Sub Main` procedimiento que se utilizará en el inicio.|  
|[/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|Especifica el nombre del ensamblado del que un módulo formará parte.|  
|`/modulename:<string>`|Especifica el nombre del módulo de origen.|  
|[/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)|Establece el compilador con destino en [!INCLUDE[Compact](~/includes/compact-md.md)].|  
|[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)|No compila con Vbc.rsp.|  
|[/nologo](../../../visual-basic/reference/command-line-compiler/nologo.md)|Suprime la información de titular del compilador.|  
|[/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|Hace que el compilador no haga referencia a las bibliotecas estándar.|  
|[/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)|Suprime la capacidad del compilador para generar advertencias.|  
|[/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|Indica al compilador que no inserte ningún manifiesto de la aplicación en el archivo ejecutable.|  
|[/optimize](../../../visual-basic/reference/command-line-compiler/optimize.md)|Habilita o deshabilita la optimización de código.|  
|[/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|Especifica si las comparaciones de cadenas deben ser binarias o usar la semántica de texto específica de la configuración regional.|  
|[/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|Exige la declaración explícita de variables.|  
|[/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|Permite el uso de la inferencia de tipo de variable local en declaraciones de variables.|  
|[/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|Exige una semántica de lenguaje estricta.|  
|[/out](../../../visual-basic/reference/command-line-compiler/out.md)|Especifica un directorio de salida.|  
|`/parallel[+&#124;-]`|Especifica si hay que usar la compilación simultánea (+).|  
|[/platform](../../../visual-basic/reference/command-line-compiler/platform.md)|Especifica la plataforma del procesador que el compilador destina para el archivo de salida.|  
|`/preferreduilang`|Especifique el nombre del lenguaje de salida preferido.|  
|[/quiet](../../../visual-basic/reference/command-line-compiler/quiet.md)|Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.|  
|[/recurse](../../../visual-basic/reference/command-line-compiler/recurse.md)|Busca en los subdirectorios los archivos de código fuente que se deben compilar.|  
|[/reference](../../../visual-basic/reference/command-line-compiler/reference.md)|Importa metadatos de un ensamblado.|  
|[/removeintchecks](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|Deshabilita las comprobaciones de desbordamiento con enteros.|  
|[/resource](../../../visual-basic/reference/command-line-compiler/resource.md)|Inserta un recurso administrado en un ensamblado.|  
|[/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|Especifica un espacio de nombres para todas las declaraciones de tipos.|  
|`/ruleset:<file>`|Especifica un archivo de conjunto de reglas que deshabilita diagnósticos específicos.|  
|[/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|Especifica la ubicación de Mscorlib.dll y Microsoft.VisualBasic.dll.|  
|[/subsystemversion](../../../visual-basic/reference/command-line-compiler/subsystemversion.md)|Especifica la versión mínima del subsistema que el archivo ejecutable generado puede utilizar.|  
|[/target](../../../visual-basic/reference/command-line-compiler/target.md)|Especifica el formato de la salida.|  
|[/utf8output](../../../visual-basic/reference/command-line-compiler/utf8output.md)|Muestra los resultados del compilador en codificación UTF-8.|  
|[/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.|  
|[/verbose](../../../visual-basic/reference/command-line-compiler/verbose.md)|Muestra información adicional durante la compilación.|  
|[/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|Promueve las advertencias a errores.|  
|[/win32icon](../../../visual-basic/reference/command-line-compiler/win32icon.md)|Inserta un archivo .ico en el archivo de salida.|  
|[/win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.|  
|[/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)|Inserta un recurso Win32 en el archivo de salida.|  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de Visual Basic, por categoría](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-by-category.md)  
 [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7)  
 [Opciones del compilador de C#, por orden alfabético](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [Opciones del compilador de C#, por categoría](../../../csharp/language-reference/compiler-options/listed-by-category.md)
