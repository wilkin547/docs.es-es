---
title: Opciones de F# Interactive
description: "Obtenga información acerca de las opciones de línea de comandos compatibles con F # Interactive, fsi.exe."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9f3e39b-ce6c-41ff-991f-0625f46441ae
ms.openlocfilehash: f0a8893abca0435307907aa9c169646bf3dec2d5
ms.sourcegitcommit: adcf9bdafeaa6bc243af7bf70b45f3df954f256a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2018
---
# <a name="f-interactive-options"></a>Opciones de F# Interactive

> [!NOTE]
En este artículo actualmente solo se describe la experiencia para Windows.  Se reescribirá.

En este tema se describe las opciones de línea de comandos compatibles con F # Interactive, `fsi.exe`. F # Interactive acepta muchas de las mismas opciones de línea de comandos que el compilador de F #, pero también acepta algunas opciones adicionales.

## <a name="using-f-interactive-for-scripting"></a>Uso de F # Interactive para secuencias de comandos
F # Interactive, `fsi.exe`, se puede iniciar de forma interactiva, o se puede iniciar desde la línea de comandos para ejecutar un script. La sintaxis de línea de comandos es

```
> fsi.exe [options] [ script-file [arguments] ]
```

La extensión de archivo para archivos de script de F # es `.fsx`.

## <a name="table-of-f-interactive-options"></a>Tabla de opciones de F # Interactive
En la tabla siguiente se resume las opciones admitidas por F # Interactive. Puede establecer estas opciones en la línea de comandos o mediante el IDE de Visual Studio. Para establecer estas opciones en el IDE de Visual Studio, abra el **herramientas** menú, seleccione **opciones...** , a continuación, expanda el **herramientas de F #** nodo y seleccione **F # Interactive**.

Si aparecen listas de argumentos de la opción de F # Interactive, elementos de lista están separados por punto y coma (`;`).

|Opción|Descripción|
|------|-----------|
|**--**|Se utiliza para indicar a F # Interactive que debe tratar los argumentos restantes como argumentos de línea de comandos para el programa en F # o el script que puede tener acceso en el código mediante el uso de la lista **fsi.CommandLineArgs**.|
|**--checked**[**+**&#124;**-**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--codepage:&lt;int&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--consolecolors**[**+**&#124;**-**]|Salidas de advertencia y mensajes de error de color.|
|**--crossoptimize**[**+**&#124;**-**]|Habilitar o deshabilitar las optimizaciones entre módulos.|
|**--debug**[**+**&#124;**-**]<br /><br />**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--define:&lt;string&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--deterministic**[**+**&#124;**-**]|Genera un ensamblado determinista (incluidos los GUID de la versión de módulo y marca de tiempo).|
|**--exec**|Indica a F # interactive se cierre después de cargar los archivos o ejecutar el archivo de script proporcionado en la línea de comandos.|
|**--fullpaths**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--gui**[**+**&#124;**-**]|Habilita o deshabilita el bucle de eventos de Windows Forms. El valor predeterminado está habilitado.|
|**--help**<br /><br />**-?**|Se usa para mostrar la sintaxis de línea de comandos y una breve descripción de cada opción.|
|**--lib:&lt;folder-list&gt;**<br /><br />**-I:&lt;folder-list&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--load:&lt;filename&gt;**|Compila el código de origen especificado en el inicio y carga las construcciones de F # compiladas en la sesión. Si el origen de destino contiene directivas de secuencias de comandos como **#use** o **#load**, a continuación, debe usar **--utilizar** o **#use** en lugar de **--cargar** o **#load**.|
|**--mlcompatibility**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--noframework**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, vea [opciones del compilador](compiler-options.md)|
|**--nologo**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--nowarn:&lt;warning-list&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--optimize**[**+**&#124;**-**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--preferreduilang:&lt;lang&gt;**| Especifica el nombre de referencia cultural del idioma de salida preferido (por ejemplo, es-es, ja-JP). |
|**--quiet**|Suprimir la salida de F # Interactive a la **stdout** secuencia.|
|**--quotations-debug**|Especifica que se debería emitir la información de depuración adicional para las expresiones que se derivan de literales de expresión de código delimitada de F # y reflejan las definiciones. La información de depuración se agrega a los atributos personalizados de un nodo de árbol de expresión de F #. Vea [expresiones de código delimitadas](code-quotations.md) y [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--readline**[**+**&#124;**-**]|Habilitar o deshabilitar la finalización con tabulación en modo interactivo.|
|**--reference:&lt;filename&gt;**<br /><br />**-r:&lt;filename&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--shadowcopyreferences**[**+**&#124;**-**]|Evita que se está bloqueado por el proceso de F # Interactive de referencias.|
|**--simpleresolution**|Resuelve las referencias de ensamblado con las reglas basadas en el directorio en lugar de la resolución de MSBuild.|
|**--tailcalls**[**+**&#124;**-**]|Habilitar o deshabilitar el uso de la instrucción de IL final, lo que hace que el marco de pila para reutilizarse en funciones recursivas de cola. Esta opción está habilitada de forma predeterminada.|
|**--targetprofile:&lt;cadena&gt;**|Especifica el perfil de este ensamblado de .NET framework de destino. Los valores válidos son mscorlib, netcore o netstandard.  El valor predeterminado es mscorlib.|
|**--utilizar:&lt;nombre de archivo&gt;**|Indica al intérprete que utilice el archivo especificado en el inicio como entrada inicial.|
|**--utf8output**|Igual que la opción del compilador fsc.exe. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--Advertir:&lt;nivel de advertencia&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**|Igual que el **fsc.exe** opción del compilador. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|

## <a name="related-topics"></a>Temas relacionados

|Título|Descripción|
|-----|-----------|
|[Opciones del compilador](compiler-options.md)|Describe las opciones de línea de comandos disponibles para el compilador de F #, **fsc.exe**.|
