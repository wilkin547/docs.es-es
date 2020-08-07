---
title: Opciones interactivas
description: Obtenga información sobre las opciones de línea de comandos compatibles con F# interactivo, fsi.exe.
ms.date: 07/22/2020
ms.openlocfilehash: abddd1fd990be18ede139ab26ffe80513ba6e0dd
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855353"
---
# <a name="f-interactive-options"></a><span data-ttu-id="51eca-103">Opciones de F# interactivo</span><span class="sxs-lookup"><span data-stu-id="51eca-103">F# Interactive options</span></span>

<span data-ttu-id="51eca-104">En este artículo se describen las opciones de línea de comandos compatibles con F# interactivo, `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="51eca-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="51eca-105">F# interactivo acepta muchas de las mismas opciones de línea de comandos que el compilador de F #, pero también acepta algunas opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="51eca-105">F# Interactive accepts many of the same command-line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="51eca-106">Usar F# interactivo para el scripting</span><span class="sxs-lookup"><span data-stu-id="51eca-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="51eca-107">F# interactivo, `dotnet fsi` , se puede iniciar de forma interactiva o se puede iniciar desde la línea de comandos para ejecutar un script.</span><span class="sxs-lookup"><span data-stu-id="51eca-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="51eca-108">La sintaxis de la línea de comandos es</span><span class="sxs-lookup"><span data-stu-id="51eca-108">The command-line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="51eca-109">La extensión de archivo de los archivos de script de F # es `.fsx` .</span><span class="sxs-lookup"><span data-stu-id="51eca-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="51eca-110">Tabla de opciones de F# interactivo</span><span class="sxs-lookup"><span data-stu-id="51eca-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="51eca-111">En la tabla siguiente se resumen las opciones admitidas por F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="51eca-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="51eca-112">Puede establecer estas opciones en la línea de comandos o a través del IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="51eca-112">You can set these options on the command line or through the Visual Studio IDE.</span></span> <span data-ttu-id="51eca-113">Para establecer estas opciones en el IDE de Visual Studio, abra el menú **herramientas** , seleccione **Opciones**, expanda el nodo **herramientas de F #** y, a continuación, seleccione **F# interactivo**.</span><span class="sxs-lookup"><span data-stu-id="51eca-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options**, expand the **F# Tools** node, and then select **F# Interactive**.</span></span>

<span data-ttu-id="51eca-114">Cuando aparecen listas en F# interactivo argumentos de opción, los elementos de lista se separan mediante signos de punto y coma ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="51eca-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="51eca-115">Opción</span><span class="sxs-lookup"><span data-stu-id="51eca-115">Option</span></span>|<span data-ttu-id="51eca-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="51eca-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="51eca-117">Se usa para indicar a F# interactivo que trate los argumentos restantes como argumentos de línea de comandos para el programa o script de F #, al que puede tener acceso en el código mediante la lista **FSI. CommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="51eca-117">Used to instruct F# Interactive to treat remaining arguments as command-line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="51eca-118">**--Checked**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-119">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-120">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-121">**--codePage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="51eca-122">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-123">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-124">**--consolecolors**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-125">Genera mensajes de advertencia y error en color.</span><span class="sxs-lookup"><span data-stu-id="51eca-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="51eca-126">**--crossoptimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-127">Habilitar o deshabilitar las optimizaciones entre módulos.</span><span class="sxs-lookup"><span data-stu-id="51eca-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="51eca-128">**--Debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="51eca-129">**--Debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="51eca-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="51eca-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="51eca-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**Embedded**]</span><span class="sxs-lookup"><span data-stu-id="51eca-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="51eca-132">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-133">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-134">**--define: &lt; cadena&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="51eca-135">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-136">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-137">**--determinista**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-138">Genera un ensamblado determinista (incluido el GUID y la marca de tiempo de la versión del módulo).</span><span class="sxs-lookup"><span data-stu-id="51eca-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="51eca-139">**--exec**</span><span class="sxs-lookup"><span data-stu-id="51eca-139">**--exec**</span></span>|<span data-ttu-id="51eca-140">Indica a F # Interactive que se cierre después de cargar los archivos o ejecutar el archivo de script proporcionado en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="51eca-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="51eca-141">**--fullpaths**</span><span class="sxs-lookup"><span data-stu-id="51eca-141">**--fullpaths**</span></span>|<span data-ttu-id="51eca-142">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-143">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-144">**--GUI**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-145">Habilita o deshabilita el bucle de eventos Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="51eca-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="51eca-146">El valor predeterminado es habilitado.</span><span class="sxs-lookup"><span data-stu-id="51eca-146">The default is enabled.</span></span>|
|<span data-ttu-id="51eca-147">**--Help**</span><span class="sxs-lookup"><span data-stu-id="51eca-147">**--help**</span></span><br /><br /><span data-ttu-id="51eca-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="51eca-148">**-?**</span></span>|<span data-ttu-id="51eca-149">Se usa para mostrar la sintaxis de línea de comandos y una breve descripción de cada opción.</span><span class="sxs-lookup"><span data-stu-id="51eca-149">Used to display the command-line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="51eca-150">**--lib: &lt; carpeta-lista&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="51eca-151">**-I: &lt; lista de carpetas&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="51eca-152">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-153">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-154">**--Load: &lt; nombre de archivo&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="51eca-155">Compila el código fuente especificado en el inicio y carga las construcciones de F # compiladas en la sesión.</span><span class="sxs-lookup"><span data-stu-id="51eca-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span> <span data-ttu-id="51eca-156">Si el origen de destino contiene directivas de scripting como **#use** o **#load**, debe usar **--use** o **#use** en lugar de **--Load** o **#load**.</span><span class="sxs-lookup"><span data-stu-id="51eca-156">If the target source contains scripting directives such as **#use** or **#load**, then you must use **--use** or **#use** instead of **--load** or **#load**.</span></span>|
|<span data-ttu-id="51eca-157">**--mlcompatibility**</span><span class="sxs-lookup"><span data-stu-id="51eca-157">**--mlcompatibility**</span></span>|<span data-ttu-id="51eca-158">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-158">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-159">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-159">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-160">**--noframess**</span><span class="sxs-lookup"><span data-stu-id="51eca-160">**--noframework**</span></span>|<span data-ttu-id="51eca-161">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-161">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-162">Para obtener más información, vea [Opciones del compilador](compiler-options.md) .</span><span class="sxs-lookup"><span data-stu-id="51eca-162">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="51eca-163">**--nologo**</span><span class="sxs-lookup"><span data-stu-id="51eca-163">**--nologo**</span></span>|<span data-ttu-id="51eca-164">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-164">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-165">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-165">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-166">**--nowarn: &lt; ADVERTENCIA-lista&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-166">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="51eca-167">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-167">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-168">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-168">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-169">**--Optimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-169">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-170">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-170">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-171">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-171">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-172">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-172">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="51eca-173">Especifica el nombre de la referencia cultural del lenguaje de salida preferido (por ejemplo, es-ES, ja-JP).</span><span class="sxs-lookup"><span data-stu-id="51eca-173">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="51eca-174">**--Quiet**</span><span class="sxs-lookup"><span data-stu-id="51eca-174">**--quiet**</span></span>|<span data-ttu-id="51eca-175">Suprima la salida de F# interactivo al flujo **stdout** .</span><span class="sxs-lookup"><span data-stu-id="51eca-175">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="51eca-176">**--Quotations-Debug**</span><span class="sxs-lookup"><span data-stu-id="51eca-176">**--quotations-debug**</span></span>|<span data-ttu-id="51eca-177">Especifica que debe emitirse información de depuración adicional para las expresiones que se derivan de los literales de Comillas de F # y las definiciones reflejadas.</span><span class="sxs-lookup"><span data-stu-id="51eca-177">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="51eca-178">La información de depuración se agrega a los atributos personalizados de un nodo de árbol de expresión de F #.</span><span class="sxs-lookup"><span data-stu-id="51eca-178">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="51eca-179">Vea [expresiones de código delimitadas](code-quotations.md) y [expr. CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span><span class="sxs-lookup"><span data-stu-id="51eca-179">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span></span>|
|<span data-ttu-id="51eca-180">**--ReadLine**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-180">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-181">Habilitar o deshabilitar la finalización con tabulación en el modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="51eca-181">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="51eca-182">**--Reference: &lt; nombre de archivo&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-182">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="51eca-183">**-r: &lt; nombre de archivo&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-183">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="51eca-184">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-184">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-185">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-185">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-186">**--tailcalls**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-186">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-187">Habilitar o deshabilitar el uso de la instrucción IL de cola, que hace que se reutilice el marco de pila para las funciones recursivas de cola.</span><span class="sxs-lookup"><span data-stu-id="51eca-187">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="51eca-188">Esta opción está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51eca-188">This option is enabled by default.</span></span>|
|<span data-ttu-id="51eca-189">**--targetprofile: &lt; cadena&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-189">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="51eca-190">Especifica el perfil de la plataforma de destino de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="51eca-190">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="51eca-191">Los valores válidos son `mscorlib`, `netcore` o `netstandard`.</span><span class="sxs-lookup"><span data-stu-id="51eca-191">Valid values are `mscorlib`, `netcore`, or `netstandard`.</span></span> <span data-ttu-id="51eca-192">El valor predeterminado es `mscorlib`.</span><span class="sxs-lookup"><span data-stu-id="51eca-192">The default is `mscorlib`.</span></span>|
|<span data-ttu-id="51eca-193">**--Use: &lt; nombre de archivo&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-193">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="51eca-194">Indica al intérprete que use el archivo especificado al iniciar como entrada inicial.</span><span class="sxs-lookup"><span data-stu-id="51eca-194">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="51eca-195">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="51eca-195">**--utf8output**</span></span>|<span data-ttu-id="51eca-196">Igual que la opción del compilador fsc.exe.</span><span class="sxs-lookup"><span data-stu-id="51eca-196">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="51eca-197">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-197">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-198">**--advertir: &lt; nivel de advertencia&gt;**</span><span class="sxs-lookup"><span data-stu-id="51eca-198">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="51eca-199">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-199">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-200">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-200">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-201">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="51eca-201">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="51eca-202">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-202">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-203">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-203">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="51eca-204">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int-List &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="51eca-204">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="51eca-205">Igual que la opción del compilador **fsc.exe** .</span><span class="sxs-lookup"><span data-stu-id="51eca-205">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="51eca-206">Para obtener más información, consulte [Opciones del compilador](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="51eca-206">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="51eca-207">F# interactivo impresión estructurada</span><span class="sxs-lookup"><span data-stu-id="51eca-207">F# Interactive structured printing</span></span>

<span data-ttu-id="51eca-208">F# interactivo ( `dotnet fsi` ) utiliza una versión extendida de [formato de texto sin formato estructurado](plaintext-formatting.md) para informar de los valores.</span><span class="sxs-lookup"><span data-stu-id="51eca-208">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="51eca-209">Se admiten todas las características de `%A` formato de texto sin formato y otras también se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="51eca-209">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="51eca-210">La impresión se colorea si los colores se admiten en la consola de salida.</span><span class="sxs-lookup"><span data-stu-id="51eca-210">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="51eca-211">Se aplica un límite a la longitud de las cadenas que se muestran, a menos que se evalúe explícitamente esa cadena.</span><span class="sxs-lookup"><span data-stu-id="51eca-211">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="51eca-212">Un conjunto de valores definidos por el usuario está disponible a través del `fsi` objeto.</span><span class="sxs-lookup"><span data-stu-id="51eca-212">A set of user-definable settings is available via the `fsi` object.</span></span>

<span data-ttu-id="51eca-213">La configuración disponible para personalizar la impresión de texto sin formato para los valores indicados es:</span><span class="sxs-lookup"><span data-stu-id="51eca-213">The available settings to customize plain text printing for reported values are:</span></span>

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

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="51eca-214">Personalizar con `AddPrinter` y`AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="51eca-214">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="51eca-215">La impresión en F# interactivo salidas se puede personalizar mediante `fsi.AddPrinter` y `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="51eca-215">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="51eca-216">La primera función proporciona texto para reemplazar la impresión de un objeto.</span><span class="sxs-lookup"><span data-stu-id="51eca-216">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="51eca-217">La segunda función devuelve en su lugar un objeto suplente que se va a mostrar.</span><span class="sxs-lookup"><span data-stu-id="51eca-217">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="51eca-218">Por ejemplo, considere el siguiente código de F #:</span><span class="sxs-lookup"><span data-stu-id="51eca-218">For example, consider the following F# code:</span></span>

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

<span data-ttu-id="51eca-219">Si ejecuta el ejemplo en F# interactivo, se genera en función del conjunto de opciones de formato.</span><span class="sxs-lookup"><span data-stu-id="51eca-219">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="51eca-220">En este caso, afecta al formato de fecha y hora:</span><span class="sxs-lookup"><span data-stu-id="51eca-220">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="51eca-221">`fsi.AddPrintTransformer`se puede usar para proporcionar un objeto suplente para la impresión:</span><span class="sxs-lookup"><span data-stu-id="51eca-221">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="51eca-222">Esto da como resultado:</span><span class="sxs-lookup"><span data-stu-id="51eca-222">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="51eca-223">Si la función de transformador pasada a `fsi.AddPrintTransformer` devuelve `null` , se omite el transformador de impresión.</span><span class="sxs-lookup"><span data-stu-id="51eca-223">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="51eca-224">Se puede usar para filtrar cualquier valor de entrada empezando por el tipo `obj` .</span><span class="sxs-lookup"><span data-stu-id="51eca-224">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="51eca-225">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="51eca-225">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="51eca-226">Esto da como resultado:</span><span class="sxs-lookup"><span data-stu-id="51eca-226">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="51eca-227">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="51eca-227">Related topics</span></span>

|<span data-ttu-id="51eca-228">Title</span><span class="sxs-lookup"><span data-stu-id="51eca-228">Title</span></span>|<span data-ttu-id="51eca-229">Descripción</span><span class="sxs-lookup"><span data-stu-id="51eca-229">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="51eca-230">Opciones del compilador</span><span class="sxs-lookup"><span data-stu-id="51eca-230">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="51eca-231">Describe las opciones de línea de comandos disponibles para el compilador de F # **fsc.exe**.</span><span class="sxs-lookup"><span data-stu-id="51eca-231">Describes command-line options available for the F# compiler, **fsc.exe**.</span></span>|
