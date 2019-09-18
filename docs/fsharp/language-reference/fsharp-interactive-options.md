---
title: Opciones de F# Interactive
description: Obtenga información sobre las opciones de línea de comandos F# admitidas por el comando interactivo, FSI. exe.
ms.date: 05/16/2016
ms.openlocfilehash: c9cd5c2e73a6e2f6ce0a9b2f2a631b6a2658423c
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083118"
---
# <a name="f-interactive-options"></a>Opciones de F# Interactive

> [!NOTE]
> En este artículo actualmente solo se describe la experiencia para Windows.  Se reescribirá.

En este tema se describen las opciones de línea de F# comandos compatibles `fsi.exe`con Interactive,. F#Interactive acepta muchas de las mismas opciones de línea de F# comandos que el compilador, pero también acepta algunas opciones adicionales.

## <a name="using-f-interactive-for-scripting"></a>Uso F# de Interactive para scripting
F#Interactivo, `fsi.exe`, se puede iniciar de forma interactiva o se puede iniciar desde la línea de comandos para ejecutar un script. La sintaxis de la línea de comandos es

```console
> fsi.exe [options] [ script-file [arguments] ]
```

La extensión de archivo F# de los archivos `.fsx`de script es.

## <a name="table-of-f-interactive-options"></a>Tabla de F# opciones interactivas
En la tabla siguiente se resumen las opciones admitidas por F# el Interactive. Puede establecer estas opciones en la línea de comandos o a través del IDE de Visual Studio. Para establecer estas opciones en el IDE de Visual Studio, abra el menú **herramientas** , seleccione **Opciones...** , expanda el  **F# nodo herramientas** y seleccione  **F# interactivo**.

Cuando las listas aparecen F# en argumentos de opción interactiva, los elementos de lista se separan mediante signos de punto y coma (`;`).

|Opción|DESCRIPCIÓN|
|------|-----------|
|**--**|Se usa para F# indicar a Interactive que trate los argumentos restantes como argumentos F# de la línea de comandos para el programa o script, al que puede tener acceso en el código mediante la lista **FSI. CommandLineArgs**.|
|**--checked**[ **+** &#124; **-** ]|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--codepage:&lt;int&gt;**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--consolecolors** [ **+** &#124; **-** ]|Genera mensajes de advertencia y error en color.|
|**--crossoptimize**[ **+** &#124; **-** ]|Habilitar o deshabilitar las optimizaciones entre módulos.|
|**--debug**[ **+** &#124; **-** ]<br /><br />**--debug:** [**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]<br /><br />**-g**[ **+** &#124; **-** ]<br /><br />**-g:** [**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--define:&lt;string&gt;**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--deterministic**[ **+** &#124; **-** ]|Genera un ensamblado determinista (incluido el GUID y la marca de tiempo de la versión del módulo).|
|**--exec**|Indica a F# interactivo que salga después de cargar los archivos o de ejecutar el archivo de script proporcionado en la línea de comandos.|
|**--fullpaths**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--gui**[ **+** &#124; **-** ]|Habilita o deshabilita el bucle de eventos Windows Forms. El valor predeterminado está habilitado.|
|**--help**<br /><br />**-?**|Se usa para mostrar la sintaxis de la línea de comandos y una breve descripción de cada opción.|
|**--lib:&lt;folder-list&gt;**<br /><br />**-I:&lt;folder-list&gt;**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--load:&lt;filename&gt;**|Compila el código fuente especificado en el inicio y carga las construcciones compiladas F# en la sesión. Si el origen de destino contiene directivas de scripting como **#use** o **#load**, debe usar **--use** o **#use** en lugar de **--Load** o **#load**.|
|**--mlcompatibility**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--noframework**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, vea [Opciones del compilador](compiler-options.md) .|
|**--nologo**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--nowarn:&lt;warning-list&gt;**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--optimizar** [ **+** &#124; **-** ]|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Especifica el nombre de la referencia cultural del lenguaje de salida preferido (por ejemplo, es-ES, ja-JP). |
|**--quiet**|Suprime F# la salida de Interactive en el flujo **stdout** .|
|**--quotations-debug**|Especifica que debe emitirse información de depuración adicional para las expresiones que F# se derivan de los literales de Comillas y de las definiciones reflejadas. La información de depuración se agrega a los atributos F# personalizados de un nodo de árbol de expresión. Vea [expresiones de código delimitadas](code-quotations.md) y [expr. CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[ **+** &#124; **-** ]|Habilitar o deshabilitar la finalización con tabulación en el modo interactivo.|
|**--Reference:&lt;nombre de archivo&gt;**<br /><br />**-r:&lt;filename&gt;**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--shadowcopyreferences**[ **+** &#124; **-** ]|Impide que el F# proceso interactivo bloquee las referencias.|
|**--simpleresolution**|Resuelve las referencias de ensamblado mediante reglas basadas en directorios en lugar de la resolución de MSBuild.|
|**--tailcalls**[ **+** &#124; **-** ]|Habilitar o deshabilitar el uso de la instrucción IL de cola, que hace que se reutilice el marco de pila para las funciones recursivas de cola. Esta opción está habilitada de forma predeterminada.|
|**--targetprofile:&lt;cadena&gt;**|Especifica el perfil de la plataforma de destino de este ensamblado. Los valores válidos son mscorlib, netcore o netstandard.  El valor predeterminado es mscorlib.|
|**--Use:&lt;nombre de archivo&gt;**|Indica al intérprete que use el archivo especificado al iniciar como entrada inicial.|
|**--utf8output**|Igual que la opción del compilador FSC. exe. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warn:&lt;warning-level&gt;**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[ **+** &#124; **-** ]|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[ **+** &#124; **-** ]: **&lt;int-list&gt;**|Igual que la opción del compilador **FSC. exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|

## <a name="related-topics"></a>Temas relacionados

|Título|DESCRIPCIÓN|
|-----|-----------|
|[Opciones del compilador](compiler-options.md)|Describe las opciones de línea de comandos F# disponibles para el compilador, **FSC. exe**.|
