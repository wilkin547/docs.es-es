---
title: Opciones de F# Interactive
description: Obtenga información sobre las opciones de línea de comandos admitidas por F# Interactive, fsi.exe.
ms.date: 05/16/2016
ms.openlocfilehash: a461dd0eeff2de3d15e557ba37138fbd62ca43ba
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "33565810"
---
# <a name="f-interactive-options"></a>Opciones de F# Interactive

> [!NOTE]
En este artículo actualmente solo se describe la experiencia para Windows.  Se reescribirá.

En este tema se describe las opciones de línea de comandos admitidas por F# interactivo, `fsi.exe`. F#Interactive acepta muchas de las mismas opciones de línea de comandos como la F# compilador, pero también acepta algunas opciones adicionales.

## <a name="using-f-interactive-for-scripting"></a>Uso de F# Interactive para Scripting
F#Interactivo, `fsi.exe`, se puede iniciar de forma interactiva o se puede iniciar desde la línea de comandos para ejecutar un script. La sintaxis de línea de comandos es

```
> fsi.exe [options] [ script-file [arguments] ]
```

La extensión de archivo para F# archivos de script es `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabla de F# opciones interactivas
En la tabla siguiente se resume las opciones admitidas por F# interactivo. Puede establecer estas opciones en la línea de comandos o mediante el IDE de Visual Studio. Para establecer estas opciones en el IDE de Visual Studio, abra el **herramientas** menú, seleccione **opciones...** , a continuación, expanda el  **F# herramientas** nodo y seleccione  **F# interactivo**.

Donde aparecen las listas en F# argumentos de la opción de modo interactivo, elementos de la lista están separados por punto y coma (`;`).

|Opción|Descripción|
|------|-----------|
|**--**|Se utiliza para indicar F# interactivo para tratar los argumentos restantes como argumentos de línea de comandos para el F# programa o script, que puede tener acceso en el código mediante el uso de la lista **fsi.CommandLineArgs**.|
|**--checked**[**+**&#124;**-**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--codepage:&lt;int&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--consolecolors**[**+**&#124;**-**]|Salidas de advertencia y mensajes de error de color.|
|**--crossoptimize**[**+**&#124;**-**]|Habilitar o deshabilitar las optimizaciones entre módulos.|
|**--debug**[**+**&#124;**-**]<br /><br />**--depurar:**[**completa**&#124;**pdbonly**&#124;**portable**&#124;**incrustado**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g:**[**completa**&#124;**pdbonly**&#124;**portable**&#124;**incrustado**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--define:&lt;string&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--deterministic**[**+**&#124;**-**]|Genera un ensamblado determinista (incluidos los GUID de la versión de módulo y la marca de tiempo).|
|**--exec**|Indica a F# interactivo se cierre después de cargar los archivos o ejecutar el archivo de script proporcionado en la línea de comandos.|
|**--fullpaths**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--gui**[**+**&#124;**-**]|Habilita o deshabilita el bucle de eventos de Windows Forms. El valor predeterminado está habilitado.|
|**--help**<br /><br />**-?**|Se usa para mostrar la sintaxis de línea de comandos y una breve descripción de cada opción.|
|**--lib:&lt;lista de carpetas&gt;**<br /><br />**-I:&lt;lista de carpetas&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--cargar:&lt;nombre de archivo&gt;**|Compila el código fuente especificado al inicio y carga compilado F# construye en la sesión. Si el origen de destino contiene directivas de scripting como **#use** o **#load**, a continuación, debe usar **--utilice** o **#use** en lugar de **--cargar** o **#load**.|
|**--mlcompatibility**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--noframework**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [opciones del compilador](compiler-options.md)|
|**--nologo**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--nowarn:&lt;lista de advertencias&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--optimizar**[**+**&#124;**-**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Especifica el nombre de referencia cultural del idioma de salida preferido (por ejemplo, es-es, ja-JP). |
|**--quiet**|Suprimir F# interactivo de la salida a la **stdout** secuencia.|
|**--quotations-debug**|Especifica que debe emitirse información de depuración adicional para las expresiones que se derivan de F# literales de presupuesto y definiciones reflejadas. La información de depuración se agrega a los atributos personalizados de un F# nodo de árbol de expresión. Consulte [de código delimitadas](code-quotations.md) y [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[**+**&#124;**-**]|Habilitar o deshabilitar el autocompletado en modo interactivo.|
|**--referencia:&lt;nombre de archivo&gt;**<br /><br />**-r:&lt;nombre de archivo&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--shadowcopyreferences**[**+**&#124;**-**]|Impide que las referencias desde que se está bloqueado por el F# proceso interactivo.|
|**--simpleresolution**|Resuelve las referencias de ensamblado mediante reglas basadas en el directorio en lugar de resolución de MSBuild.|
|**--tailcalls**[**+**&#124;**-**]|Habilitar o deshabilitar el uso de la instrucción IL de cola, lo que hace que el marco de pila para reutilizarse en funciones recursivas de cola. Esta opción está habilitada de forma predeterminada.|
|**--targetprofile:&lt;cadena&gt;**|Especifica el perfil de framework de destino de este ensamblado. Los valores válidos son mscorlib, netcore o netstandard.  El valor predeterminado es mscorlib.|
|**--Utilice:&lt;nombre de archivo&gt;**|Indica al intérprete que utilice el archivo indicado en el inicio como entrada inicial.|
|**--utf8output**|Igual que la opción del compilador fsc.exe. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--Advertir:&lt;nivel de advertencia&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----|-----------|
|[Opciones del compilador](compiler-options.md)|Describe las opciones de línea de comandos disponibles para el F# compilador, **fsc.exe**.|
