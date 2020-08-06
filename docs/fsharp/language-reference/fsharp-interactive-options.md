---
title: Opciones interactivas
description: Obtenga información sobre las opciones de línea de comandos compatibles con F# interactivo, fsi.exe.
ms.date: 07/22/2020
ms.openlocfilehash: f9932cac24fad187c332306968fb13981912e80a
ms.sourcegitcommit: 09bad6ec0cbf18be7cd7f62e77286d305a18b607
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "87795468"
---
# <a name="f-interactive-options"></a>Opciones de F# interactivo

En este artículo se describen las opciones de línea de comandos compatibles con F# interactivo, `fsi.exe` . F# interactivo acepta muchas de las mismas opciones de línea de comandos que el compilador de F #, pero también acepta algunas opciones adicionales.

## <a name="use-f-interactive-for-scripting"></a>Usar F# interactivo para el scripting

F# interactivo, `dotnet fsi` , se puede iniciar de forma interactiva o se puede iniciar desde la línea de comandos para ejecutar un script. La sintaxis de la línea de comandos es

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

La extensión de archivo de los archivos de script de F # es `.fsx` .

## <a name="table-of-f-interactive-options"></a>Tabla de opciones de F# interactivo

En la tabla siguiente se resumen las opciones admitidas por F# interactivo. Puede establecer estas opciones en la línea de comandos o a través del IDE de Visual Studio. Para establecer estas opciones en el IDE de Visual Studio, abra el menú **herramientas** , seleccione **Opciones...**, expanda el nodo herramientas de **F #** y seleccione **F# interactivo**.

Cuando aparecen listas en F# interactivo argumentos de opción, los elementos de lista se separan mediante signos de punto y coma ( `;` ).

|Opción|Descripción|
|------|-----------|
|**--**|Se usa para indicar a F# interactivo que trate los argumentos restantes como argumentos de la línea de comandos para el programa o script de F #, al que puede tener acceso en el código mediante la lista **FSI. CommandLineArgs**.|
|**--Checked**[ **+**&#124;**-** ]|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--codePage: &lt; int&gt;**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--consolecolors**[ **+**&#124;**-** ]|Genera mensajes de advertencia y error en color.|
|**--crossoptimize**[ **+**&#124;**-** ]|Habilitar o deshabilitar las optimizaciones entre módulos.|
|**--Debug**[ **+**&#124;**-** ]<br /><br />**--Debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**Embedded**]<br /><br />**-g**[ **+**&#124;**-** ]<br /><br />**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**Embedded**]|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--define: &lt; cadena&gt;**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--determinista**[ **+**&#124;**-** ]|Genera un ensamblado determinista (incluido el GUID y la marca de tiempo de la versión del módulo).|
|**--exec**|Indica a F # Interactive que se cierre después de cargar los archivos o ejecutar el archivo de script proporcionado en la línea de comandos.|
|**--fullpaths**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--GUI**[ **+**&#124;**-** ]|Habilita o deshabilita el bucle de eventos Windows Forms. El valor predeterminado es habilitado.|
|**--Help**<br /><br />**-?**|Se usa para mostrar la sintaxis de la línea de comandos y una breve descripción de cada opción.|
|**--lib: &lt; carpeta-lista&gt;**<br /><br />**-I: &lt; lista de carpetas&gt;**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--Load: &lt; nombre de archivo&gt;**|Compila el código fuente especificado en el inicio y carga las construcciones de F # compiladas en la sesión. Si el origen de destino contiene directivas de scripting como **#use** o **#load**, debe usar **--use** o **#use** en lugar de **--Load** o **#load**.|
|**--mlcompatibility**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--noframess**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, vea [Opciones del compilador](compiler-options.md) .|
|**--nologo**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--nowarn: &lt; ADVERTENCIA-lista&gt;**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--Optimize**[ **+**&#124;**-** ]|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--preferreduilang: &lt; lang&gt;**| Especifica el nombre de la referencia cultural del lenguaje de salida preferido (por ejemplo, es-ES, ja-JP). |
|**--Quiet**|Suprima la salida de F# interactivo al flujo **stdout** .|
|**--Quotations-Debug**|Especifica que debe emitirse información de depuración adicional para las expresiones que se derivan de los literales de Comillas de F # y las definiciones reflejadas. La información de depuración se agrega a los atributos personalizados de un nodo de árbol de expresión de F #. Vea [expresiones de código delimitadas](code-quotations.md) y [expr. CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--ReadLine**[ **+**&#124;**-** ]|Habilitar o deshabilitar la finalización con tabulación en el modo interactivo.|
|**--Reference: &lt; nombre de archivo&gt;**<br /><br />**-r: &lt; nombre de archivo&gt;**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--tailcalls**[ **+**&#124;**-** ]|Habilitar o deshabilitar el uso de la instrucción IL de cola, que hace que se reutilice el marco de pila para las funciones recursivas de cola. Esta opción está habilitada de manera predeterminada.|
|**--targetprofile: &lt; cadena&gt;**|Especifica el perfil de la plataforma de destino de este ensamblado. Los valores válidos son mscorlib, netcore o netstandard.  El valor predeterminado es mscorlib.|
|**--Use: &lt; nombre de archivo&gt;**|Indica al intérprete que use el archivo especificado al iniciar como entrada inicial.|
|**--utf8output**|Igual que la opción del compilador fsc.exe. Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--advertir: &lt; nivel de advertencia&gt;**|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[ **+**&#124;**-** ]|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|
|**--warnaserror**[ **+**&#124;**-** ]:** &lt; int-List &gt; **|Igual que la opción del compilador **fsc.exe** . Para obtener más información, consulte [Opciones del compilador](compiler-options.md).|

## <a name="f-interactive-structured-printing"></a>F# interactivo impresión estructurada

F# interactivo ( `dotnet fsi` ) utiliza una versión extendida de [formato de texto sin formato estructurado](plaintext-formatting.md) para informar de los valores.

1. Se admiten todas las características de `%A` formato de texto sin formato y otras también se pueden personalizar.

2. La impresión se colorea si los colores se admiten en la consola de salida.

3. Se aplica un límite a la longitud de las cadenas que se muestran, a menos que se evalúe explícitamente esa cadena.

4. Un conjunto de valores definidos por el usuario están disponibles a través del `fsi` objeto.

La configuración disponible para personalizar la impresión de texto sin formato para los valores indicados es:

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a>Personalizar con `AddPrinter` y`AddPrintTransformer`

La impresión en F# interactivo salidas se puede personalizar mediante `fsi.AddPrinter` y `fsi.AddPrintTransformer` .
La primera función proporciona texto para reemplazar la impresión de un objeto. La segunda función devuelve en su lugar un objeto suplente que se va a mostrar. Por ejemplo, considere el siguiente código de F #:

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

Si ejecuta el ejemplo en F# interactivo, se genera en función del conjunto de opciones de formato. En este caso, afecta al formato de fecha y hora:

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

`fsi.AddPrintTransformer`se puede usar para proporcionar un objeto suplente para la impresión:

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

Esto da como resultado:

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

Si la función de transformador pasada a `fsi.AddPrintTransformer` devuelve `null` , se omite el transformador de impresión.
Se puede usar para filtrar cualquier valor de entrada empezando por el tipo `obj` .  Por ejemplo:

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

Esto da como resultado:

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----|-----------|
|[Opciones del compilador](compiler-options.md)|Describe las opciones de línea de comandos disponibles para el compilador de F # **fsc.exe**.|
