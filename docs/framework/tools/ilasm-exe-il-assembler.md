---
title: Ilasm.exe (Ensamblador de IL)
description: Empiece a usar Ilasm.exe, el ensamblador de IL. Esta herramienta genera un archivo ejecutable portable (PE) a partir de lenguaje intermedio (IL).
ms.date: 03/30/2017
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
ms.openlocfilehash: 1a85b3bf9509ffba6c2331d14196a6bef2bfa080
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166979"
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="616fe-104">Ilasm.exe (Ensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="616fe-104">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="616fe-105">El Ensamblador de IL genera un archivo portable ejecutable (PE) a partir del lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="616fe-105">The IL Assembler generates a portable executable (PE) file from intermediate language (IL).</span></span> <span data-ttu-id="616fe-106">Para obtener información sobre IL, consulte [Proceso de ejecución administrada](../../standard/managed-execution-process.md). Se puede ejecutar el archivo ejecutable resultante, que contiene IL y los metadatos requeridos, para determinar si IL se comporta de acuerdo con lo esperado.</span><span class="sxs-lookup"><span data-stu-id="616fe-106">(For more information on IL, see [Managed Execution Process](../../standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="616fe-107">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="616fe-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="616fe-108">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="616fe-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="616fe-109">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="616fe-109">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="616fe-110">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="616fe-110">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="616fe-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="616fe-111">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a><span data-ttu-id="616fe-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="616fe-112">Parameters</span></span>

| <span data-ttu-id="616fe-113">Argumento</span><span class="sxs-lookup"><span data-stu-id="616fe-113">Argument</span></span> | <span data-ttu-id="616fe-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="616fe-114">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="616fe-115">El nombre del archivo de código fuente con extensión .il.</span><span class="sxs-lookup"><span data-stu-id="616fe-115">The name of the .il source file.</span></span> <span data-ttu-id="616fe-116">Este archivo consta de directivas de declaraciones de metadatos e instrucciones simbólicas de IL.</span><span class="sxs-lookup"><span data-stu-id="616fe-116">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="616fe-117">Con *Ilasm.exe* se pueden proporcionar varios argumentos de archivo de código fuente para producir un único archivo PE.</span><span class="sxs-lookup"><span data-stu-id="616fe-117">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="616fe-118">**Nota:** Asegúrese de que la última línea de código del archivo de código fuente .il tiene un espacio en blanco al final o un carácter de fin de línea.</span><span class="sxs-lookup"><span data-stu-id="616fe-118">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="616fe-119">Opción</span><span class="sxs-lookup"><span data-stu-id="616fe-119">Option</span></span> | <span data-ttu-id="616fe-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="616fe-120">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="616fe-121">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="616fe-121">**/32bitpreferred**</span></span>|<span data-ttu-id="616fe-122">Crea una imagen preferida de 32 bits (PE32).</span><span class="sxs-lookup"><span data-stu-id="616fe-122">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="616fe-123">**/alignment:** `integer`</span><span class="sxs-lookup"><span data-stu-id="616fe-123">**/alignment:** `integer`</span></span>|<span data-ttu-id="616fe-124">Establece FileAlignment en el valor especificado por `integer` en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="616fe-124">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="616fe-125">Si se especifica la directiva IL .alignment en el archivo, esta opción la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="616fe-125">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="616fe-126">**/appcontainer**</span><span class="sxs-lookup"><span data-stu-id="616fe-126">**/appcontainer**</span></span>|<span data-ttu-id="616fe-127">Genera un archivo *.dll* o *.exe* que se ejecuta en el contenedor de la aplicación de Windows, como salida.</span><span class="sxs-lookup"><span data-stu-id="616fe-127">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="616fe-128">**/arm**</span><span class="sxs-lookup"><span data-stu-id="616fe-128">**/arm**</span></span>|<span data-ttu-id="616fe-129">Especifica Advanced RISC Machine (ARM) como procesador de destino.</span><span class="sxs-lookup"><span data-stu-id="616fe-129">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="616fe-130">Si no se especifican los bits de la imagen, el valor predeterminado es **/32bitpreferred**.</span><span class="sxs-lookup"><span data-stu-id="616fe-130">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="616fe-131">**/base:** `integer`</span><span class="sxs-lookup"><span data-stu-id="616fe-131">**/base:** `integer`</span></span>|<span data-ttu-id="616fe-132">Establece ImageBase en el valor especificado por `integer` en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="616fe-132">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="616fe-133">Si se especifica la directiva IL .imagebase en el archivo, esta opción la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="616fe-133">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="616fe-134">**/clock**</span><span class="sxs-lookup"><span data-stu-id="616fe-134">**/clock**</span></span>|<span data-ttu-id="616fe-135">Mide e informa de los siguientes tiempos de compilación en milisegundos para el archivo de código fuente .il especificado:</span><span class="sxs-lookup"><span data-stu-id="616fe-135">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="616fe-136">**Total Run**: Tiempo total empleado en la ejecución de todas las operaciones específicas que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="616fe-136">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="616fe-137">**Startup**: Carga y apertura del archivo.</span><span class="sxs-lookup"><span data-stu-id="616fe-137">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="616fe-138">**Emitting MD**: Emisión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="616fe-138">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="616fe-139">**Ref to Def Resolution**: Resolución de referencias a definiciones del archivo.</span><span class="sxs-lookup"><span data-stu-id="616fe-139">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="616fe-140">**CEE File Generation**: Generación de la imagen de archivo en memoria.</span><span class="sxs-lookup"><span data-stu-id="616fe-140">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="616fe-141">**PE File Writing**: Escritura de la imagen en un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="616fe-141">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="616fe-142">**/debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="616fe-142">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="616fe-143">Incluye información de depuración (nombres de variables locales y argumentos, y números de línea).</span><span class="sxs-lookup"><span data-stu-id="616fe-143">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="616fe-144">Crea un archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="616fe-144">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="616fe-145">**/debug** sin ningún valor adicional deshabilita la optimización JIT y usa puntos de secuencia del archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="616fe-145">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="616fe-146">**IMPL** deshabilita la optimización JIT y usa puntos de secuencia implícitos.</span><span class="sxs-lookup"><span data-stu-id="616fe-146">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="616fe-147">**OPT** habilita la optimización JIT y usa puntos de secuencia implícitos.</span><span class="sxs-lookup"><span data-stu-id="616fe-147">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="616fe-148">**/dll**</span><span class="sxs-lookup"><span data-stu-id="616fe-148">**/dll**</span></span>|<span data-ttu-id="616fe-149">Genera un archivo *.dll* como archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="616fe-149">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="616fe-150">**/enc:** `file`</span><span class="sxs-lookup"><span data-stu-id="616fe-150">**/enc:** `file`</span></span>|<span data-ttu-id="616fe-151">Crea deltas Editar y continuar a partir del archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="616fe-151">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="616fe-152">Este argumento es solo para uso académico, no se admite el uso comercial del mismo.</span><span class="sxs-lookup"><span data-stu-id="616fe-152">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="616fe-153">**/exe**</span><span class="sxs-lookup"><span data-stu-id="616fe-153">**/exe**</span></span>|<span data-ttu-id="616fe-154">Genera un archivo ejecutable como archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="616fe-154">Produces an executable file as output.</span></span> <span data-ttu-id="616fe-155">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="616fe-155">This is the default.</span></span>|
|<span data-ttu-id="616fe-156">**/flags:** `integer`</span><span class="sxs-lookup"><span data-stu-id="616fe-156">**/flags:** `integer`</span></span>|<span data-ttu-id="616fe-157">Establece ImageFlags en el valor especificado por `integer` en el encabezado de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="616fe-157">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="616fe-158">Si se especifica la directiva IL .corflags en el archivo, esta opción la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="616fe-158">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="616fe-159">Vea CorHdr.h, COMIMAGE_FLAGS para obtener una lista de los valores válidos para *integer*.</span><span class="sxs-lookup"><span data-stu-id="616fe-159">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="616fe-160">**/fold**</span><span class="sxs-lookup"><span data-stu-id="616fe-160">**/fold**</span></span>|<span data-ttu-id="616fe-161">Forma un solo cuerpo a partir de cuerpos de método idénticos.</span><span class="sxs-lookup"><span data-stu-id="616fe-161">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="616fe-162">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="616fe-162">/**highentropyva**</span></span>|<span data-ttu-id="616fe-163">Genera un archivo ejecutable de salida que admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="616fe-163">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="616fe-164">(Es el valor predeterminado de **/appcontainer**).</span><span class="sxs-lookup"><span data-stu-id="616fe-164">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="616fe-165">**/include:** `includePath`</span><span class="sxs-lookup"><span data-stu-id="616fe-165">**/include:** `includePath`</span></span>|<span data-ttu-id="616fe-166">Establece una ruta de acceso para buscar los archivos incluidos con `#include`.</span><span class="sxs-lookup"><span data-stu-id="616fe-166">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="616fe-167">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="616fe-167">**/itanium**</span></span>|<span data-ttu-id="616fe-168">Especifica Intel Itanium como procesador de destino.</span><span class="sxs-lookup"><span data-stu-id="616fe-168">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="616fe-169">Si no se especifican los bits de la imagen, el valor predeterminado es **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="616fe-169">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="616fe-170">**/key:** `keyFile`</span><span class="sxs-lookup"><span data-stu-id="616fe-170">**/key:** `keyFile`</span></span>|<span data-ttu-id="616fe-171">Compila `filename` con una firma segura mediante la clave privada contenida en `keyFile`.</span><span class="sxs-lookup"><span data-stu-id="616fe-171">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="616fe-172">**/key:**  @`keySource`</span><span class="sxs-lookup"><span data-stu-id="616fe-172">**/key:** @`keySource`</span></span>|<span data-ttu-id="616fe-173">Compila `filename` con una firma segura mediante la clave privada generada en `keySource`.</span><span class="sxs-lookup"><span data-stu-id="616fe-173">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="616fe-174">**/listing**</span><span class="sxs-lookup"><span data-stu-id="616fe-174">**/listing**</span></span>|<span data-ttu-id="616fe-175">Genera un archivo del lista en la salida estándar.</span><span class="sxs-lookup"><span data-stu-id="616fe-175">Produces a listing file on the standard output.</span></span> <span data-ttu-id="616fe-176">Si se omite esta opción, no se genera ningún archivo de lista.</span><span class="sxs-lookup"><span data-stu-id="616fe-176">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="616fe-177">Este parámetro no es compatible con .NET Framework 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="616fe-177">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="616fe-178">**/mdv:** `versionString`</span><span class="sxs-lookup"><span data-stu-id="616fe-178">**/mdv:** `versionString`</span></span>|<span data-ttu-id="616fe-179">Establece la cadena de versión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="616fe-179">Sets the metadata version string.</span></span>|
|<span data-ttu-id="616fe-180">**/msv:** `major`.`minor`</span><span class="sxs-lookup"><span data-stu-id="616fe-180">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="616fe-181">Establece la versión del flujo de metadatos, donde `major` y `minor` son valores enteros.</span><span class="sxs-lookup"><span data-stu-id="616fe-181">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="616fe-182">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="616fe-182">**/noautoinherit**</span></span>|<span data-ttu-id="616fe-183">Deshabilita la herencia predeterminada de <xref:System.Object> cuando no se especifica ninguna clase base.</span><span class="sxs-lookup"><span data-stu-id="616fe-183">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="616fe-184">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="616fe-184">**/nocorstub**</span></span>|<span data-ttu-id="616fe-185">Suprime la generación de código auxiliar de CORExeMain.</span><span class="sxs-lookup"><span data-stu-id="616fe-185">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="616fe-186">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="616fe-186">**/nologo**</span></span>|<span data-ttu-id="616fe-187">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="616fe-187">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="616fe-188">**/output:** `file.ext`</span><span class="sxs-lookup"><span data-stu-id="616fe-188">**/output:** `file.ext`</span></span>|<span data-ttu-id="616fe-189">Especifica el nombre y la extensión del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="616fe-189">Specifies the output file name and extension.</span></span> <span data-ttu-id="616fe-190">De forma predeterminada, el nombre del archivo de salida coincide con el nombre del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="616fe-190">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="616fe-191">La extensión predeterminada es *.exe*.</span><span class="sxs-lookup"><span data-stu-id="616fe-191">The default extension is *.exe*.</span></span> <span data-ttu-id="616fe-192">Si se especifica la opción **/dll**, la extensión predeterminada es *.dll*.</span><span class="sxs-lookup"><span data-stu-id="616fe-192">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="616fe-193">**Nota:** La especificación de **/output**:myfile.dll no establece la opción **/dll**.</span><span class="sxs-lookup"><span data-stu-id="616fe-193">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="616fe-194">Si no se especifica **/dll**, el resultado será un archivo ejecutable denominado *myfile.dll*.</span><span class="sxs-lookup"><span data-stu-id="616fe-194">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="616fe-195">**/optimize**</span><span class="sxs-lookup"><span data-stu-id="616fe-195">**/optimize**</span></span>|<span data-ttu-id="616fe-196">Optimiza las instrucciones largas en instrucciones cortas.</span><span class="sxs-lookup"><span data-stu-id="616fe-196">Optimizes long instructions to short.</span></span> <span data-ttu-id="616fe-197">Por ejemplo, `br` en `br.s`.</span><span class="sxs-lookup"><span data-stu-id="616fe-197">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="616fe-198">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="616fe-198">**/pe64**</span></span>|<span data-ttu-id="616fe-199">Crea una imagen de 64 bits (PE32+).</span><span class="sxs-lookup"><span data-stu-id="616fe-199">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="616fe-200">Si no se especifica un procesador de destino, el valor predeterminado es `/itanium`.</span><span class="sxs-lookup"><span data-stu-id="616fe-200">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="616fe-201">**/pdb**</span><span class="sxs-lookup"><span data-stu-id="616fe-201">**/pdb**</span></span>|<span data-ttu-id="616fe-202">Crea un archivo PDB sin habilitar un seguimiento de la información de depuración.</span><span class="sxs-lookup"><span data-stu-id="616fe-202">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="616fe-203">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="616fe-203">**/quiet**</span></span>|<span data-ttu-id="616fe-204">Especifica el modo silencioso; no se notifica el progreso del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="616fe-204">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="616fe-205">**/resource:** `file.res`</span><span class="sxs-lookup"><span data-stu-id="616fe-205">**/resource:** `file.res`</span></span>|<span data-ttu-id="616fe-206">Incluye el archivo de recursos especificado con formato \*.res en el archivo *.exe* o *.dll* resultante.</span><span class="sxs-lookup"><span data-stu-id="616fe-206">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="616fe-207">Solo se puede especificar un archivo .res con la opción **/resource** .</span><span class="sxs-lookup"><span data-stu-id="616fe-207">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="616fe-208">**/ssver:** `int`.`int`</span><span class="sxs-lookup"><span data-stu-id="616fe-208">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="616fe-209">Establece el número de versión del subsistema en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="616fe-209">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="616fe-210">Para **/appcontainer** y **/arm** el número de versión mínimo es 6.02.</span><span class="sxs-lookup"><span data-stu-id="616fe-210">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="616fe-211">**/stack:** `stackSize`</span><span class="sxs-lookup"><span data-stu-id="616fe-211">**/stack:** `stackSize`</span></span>|<span data-ttu-id="616fe-212">Establece el valor de SizeOfStackReserve en el encabezado NT opcional en `stackSize`.</span><span class="sxs-lookup"><span data-stu-id="616fe-212">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="616fe-213">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="616fe-213">**/stripreloc**</span></span>|<span data-ttu-id="616fe-214">Especifica que no es necesaria ninguna reubicación base.</span><span class="sxs-lookup"><span data-stu-id="616fe-214">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="616fe-215">**/subsystem:** `integer`</span><span class="sxs-lookup"><span data-stu-id="616fe-215">**/subsystem:** `integer`</span></span>|<span data-ttu-id="616fe-216">Establece subsystem en el valor especificado por `integer` en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="616fe-216">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="616fe-217">Si se especifica la directiva IL .subsystem en el archivo, este comando la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="616fe-217">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="616fe-218">Vea winnt.h, IMAGE_SUBSYSTEM para obtener una lista de los valores válidos para `integer`.</span><span class="sxs-lookup"><span data-stu-id="616fe-218">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="616fe-219">**/x64**</span><span class="sxs-lookup"><span data-stu-id="616fe-219">**/x64**</span></span>|<span data-ttu-id="616fe-220">Especifica un procesador AMD de 64 bits como procesador de destino.</span><span class="sxs-lookup"><span data-stu-id="616fe-220">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="616fe-221">Si no se especifican los bits de la imagen, el valor predeterminado es **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="616fe-221">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="616fe-222">**/?**</span><span class="sxs-lookup"><span data-stu-id="616fe-222">**/?**</span></span>|<span data-ttu-id="616fe-223">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="616fe-223">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="616fe-224">Ninguna de las opciones de *Ilasm.exe* distingue entre mayúsculas y minúsculas, y se reconocen mediante las tres primeras letras.</span><span class="sxs-lookup"><span data-stu-id="616fe-224">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="616fe-225">Por ejemplo, **/lis** equivale a **/listing** y **/res**:myresfile.res equivale a **/resource**:myresfile.res. Las opciones que especifican argumentos aceptan un signo de dos puntos (:) o un signo igual (=) como separador entre la opción y el argumento.</span><span class="sxs-lookup"><span data-stu-id="616fe-225">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="616fe-226">Por ejemplo, **/output**:*file.ext* es equivalente a **/output**=*file.ext*.</span><span class="sxs-lookup"><span data-stu-id="616fe-226">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="616fe-227">Comentarios</span><span class="sxs-lookup"><span data-stu-id="616fe-227">Remarks</span></span>

<span data-ttu-id="616fe-228">El Ensamblador de IL ayuda a los proveedores de herramientas a diseñar e implementar generadores IL.</span><span class="sxs-lookup"><span data-stu-id="616fe-228">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="616fe-229">Mediante el uso de *Ilasm.exe*, los desarrolladores de herramientas y compiladores se pueden concentrar en la generación de IL y metadatos sin necesidad de preocuparse por la emisión de IL en el formato de archivo PE.</span><span class="sxs-lookup"><span data-stu-id="616fe-229">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="616fe-230">Al igual que otros compiladores orientados al tiempo de ejecución, como C# y Visual Basic, *Ilasm.exe* no genera archivos objeto intermedios y no requiere una etapa de vinculación para crear un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="616fe-230">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="616fe-231">El Ensamblador de IL puede expresar todos los metadatos existentes y las características de IL que caracterizan a los lenguajes de programación orientados al runtime.</span><span class="sxs-lookup"><span data-stu-id="616fe-231">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="616fe-232">Esto permite que el código administrado escrito en cualquiera de estos lenguajes de programación se pueda expresar en el Ensamblador de IL y compilar con *Ilasm.exe* de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="616fe-232">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="616fe-233">Si la última línea de código del archivo de código fuente .il no tiene espacio en blanco al final o un carácter de fin de línea, podría producirse un error en la compilación.</span><span class="sxs-lookup"><span data-stu-id="616fe-233">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="616fe-234">Se puede usar *Ilasm.exe* conjuntamente con su herramienta complementaria [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="616fe-234">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="616fe-235">*Ildasm.exe* toma un archivo PE que contiene código IL y crea un archivo de texto adecuado como entrada para *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="616fe-235">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="616fe-236">Esta técnica es muy útil cuando, por ejemplo, se compila código en un lenguaje de programación que no admite todos los atributos de metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="616fe-236">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="616fe-237">Una vez compilado el código y ejecutada la salida mediante *Ildasm.exe*, el archivo de texto de IL resultante se puede editar manualmente para agregar los atributos que faltan.</span><span class="sxs-lookup"><span data-stu-id="616fe-237">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="616fe-238">Después, se puede ejecutar este archivo de texto mediante *Ilasm.exe* para producir un archivo ejecutable final.</span><span class="sxs-lookup"><span data-stu-id="616fe-238">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="616fe-239">También se puede usar esta técnica para generar un único archivo PE a partir de varios archivos PE generados originalmente por compiladores diferentes.</span><span class="sxs-lookup"><span data-stu-id="616fe-239">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="616fe-240">Actualmente no se puede usar esta técnica con archivos PE que contienen código nativo incrustado (por ejemplo, archivos PE generados por Visual C++).</span><span class="sxs-lookup"><span data-stu-id="616fe-240">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="616fe-241">Para que este uso combinado de *Ildasm.exe* e *Ilasm.exe* sea lo más preciso posible, de forma predeterminada, el ensamblador no sustituye las codificaciones cortas por las largas que se hayan podido escribir en los códigos fuente de IL (o que haya emitido otro compilador).</span><span class="sxs-lookup"><span data-stu-id="616fe-241">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="616fe-242">Use la opción **/optimize** para sustituir las codificaciones cortas siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="616fe-242">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="616fe-243">*Ildasm.exe* solo funciona en archivos existentes en disco.</span><span class="sxs-lookup"><span data-stu-id="616fe-243">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="616fe-244">No funciona en archivos instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="616fe-244">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="616fe-245">Para obtener más información sobre la gramática de IL, vea el archivo asmparse.grammar en Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="616fe-245">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="version-information"></a><span data-ttu-id="616fe-246">Información de versión</span><span class="sxs-lookup"><span data-stu-id="616fe-246">Version Information</span></span>

<span data-ttu-id="616fe-247">A partir de .NET Framework 4.5, se puede asociar un atributo personalizado a una implementación de interfaz mediante código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="616fe-247">Starting with the .NET Framework 4.5, you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

```il
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

<span data-ttu-id="616fe-248">A partir de .NET Framework 4.5, se puede especificar un objeto binario grande (BLOB) de serialización arbitraria mediante su representación binaria sin formato, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="616fe-248">Starting with the .NET Framework 4.5, you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="616fe-249">Para obtener más información sobre la gramática de IL, vea el archivo asmparse.grammar en Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="616fe-249">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="616fe-250">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="616fe-250">Examples</span></span>

<span data-ttu-id="616fe-251">El comando siguiente ensambla el archivo IL *myTestFile.il* y genera el archivo ejecutable *myTestFile.exe*.</span><span class="sxs-lookup"><span data-stu-id="616fe-251">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="616fe-252">El comando siguiente ensambla el archivo IL *myTestFile.il* y genera el archivo *.dll* *myTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="616fe-252">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="616fe-253">El comando siguiente ensambla el archivo IL *myTestFile.il* y genera el archivo *.dll* *myNewTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="616fe-253">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="616fe-254">En el siguiente ejemplo de código se muestra una aplicación muy simple que muestra "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="616fe-254">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="616fe-255">en la consola.</span><span class="sxs-lookup"><span data-stu-id="616fe-255">to the console.</span></span> <span data-ttu-id="616fe-256">Puede compilar este código y, después, usar la herramienta [*Ildasm.exe*](ildasm-exe-il-disassembler.md) para generar un archivo IL.</span><span class="sxs-lookup"><span data-stu-id="616fe-256">You can compile this code and then use the [*Ildasm.exe*](ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

<span data-ttu-id="616fe-257">El siguiente ejemplo de código IL se corresponde con el ejemplo de código de C# anterior.</span><span class="sxs-lookup"><span data-stu-id="616fe-257">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="616fe-258">Puede compilar este código en un ensamblado con la herramienta Ensamblador de IL.</span><span class="sxs-lookup"><span data-stu-id="616fe-258">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="616fe-259">Tanto el ejemplo de código IL como el de C# muestran "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="616fe-259">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="616fe-260">en la consola.</span><span class="sxs-lookup"><span data-stu-id="616fe-260">to the console.</span></span>

```il
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a><span data-ttu-id="616fe-261">Vea también</span><span class="sxs-lookup"><span data-stu-id="616fe-261">See also</span></span>

- [<span data-ttu-id="616fe-262">Herramientas</span><span class="sxs-lookup"><span data-stu-id="616fe-262">Tools</span></span>](index.md)
- [<span data-ttu-id="616fe-263">*Ildasm.exe* (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="616fe-263">*Ildasm.exe* (IL Disassembler)</span></span>](ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="616fe-264">Proceso de ejecución administrada</span><span class="sxs-lookup"><span data-stu-id="616fe-264">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="616fe-265">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="616fe-265">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
