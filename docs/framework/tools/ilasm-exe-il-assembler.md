---
title: Ilasm.exe (Ensamblador de IL)
description: Empiece a usar Ilasm.exe, el ensamblador de IL. Esta herramienta genera un archivo ejecutable portable (PE) a partir de un ensamblado de lenguaje intermedio (IL).
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
ms.openlocfilehash: be654c27af2b3e0e281c734069f2de469b901446
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258044"
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="06853-104">Ilasm.exe (Ensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="06853-104">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="06853-105">El Ensamblador de IL genera un archivo portable ejecutable (PE) a partir del ensamblado de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="06853-105">The IL Assembler generates a portable executable (PE) file from intermediate language (IL) assembly.</span></span> <span data-ttu-id="06853-106">Para obtener información sobre IL, consulte [Proceso de ejecución administrada](../../standard/managed-execution-process.md). Se puede ejecutar el archivo ejecutable resultante, que contiene IL y los metadatos requeridos, para determinar si IL se comporta de acuerdo con lo esperado.</span><span class="sxs-lookup"><span data-stu-id="06853-106">(For more information on IL, see [Managed Execution Process](../../standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="06853-107">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="06853-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="06853-108">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="06853-108">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>

<span data-ttu-id="06853-109">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="06853-109">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="06853-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06853-110">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a><span data-ttu-id="06853-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06853-111">Parameters</span></span>

| <span data-ttu-id="06853-112">Argumento</span><span class="sxs-lookup"><span data-stu-id="06853-112">Argument</span></span> | <span data-ttu-id="06853-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="06853-113">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="06853-114">El nombre del archivo de código fuente con extensión .il.</span><span class="sxs-lookup"><span data-stu-id="06853-114">The name of the .il source file.</span></span> <span data-ttu-id="06853-115">Este archivo consta de directivas de declaraciones de metadatos e instrucciones simbólicas de IL.</span><span class="sxs-lookup"><span data-stu-id="06853-115">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="06853-116">Con *Ilasm.exe* se pueden proporcionar varios argumentos de archivo de código fuente para producir un único archivo PE.</span><span class="sxs-lookup"><span data-stu-id="06853-116">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="06853-117">**Nota:** Asegúrese de que la última línea de código del archivo de código fuente .il tiene un espacio en blanco al final o un carácter de fin de línea.</span><span class="sxs-lookup"><span data-stu-id="06853-117">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="06853-118">Opción</span><span class="sxs-lookup"><span data-stu-id="06853-118">Option</span></span> | <span data-ttu-id="06853-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="06853-119">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="06853-120">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="06853-120">**/32bitpreferred**</span></span>|<span data-ttu-id="06853-121">Crea una imagen preferida de 32 bits (PE32).</span><span class="sxs-lookup"><span data-stu-id="06853-121">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="06853-122">**/alignment:** `integer`</span><span class="sxs-lookup"><span data-stu-id="06853-122">**/alignment:** `integer`</span></span>|<span data-ttu-id="06853-123">Establece FileAlignment en el valor especificado por `integer` en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="06853-123">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="06853-124">Si se especifica la directiva IL .alignment en el archivo, esta opción la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="06853-124">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="06853-125">**/appcontainer**</span><span class="sxs-lookup"><span data-stu-id="06853-125">**/appcontainer**</span></span>|<span data-ttu-id="06853-126">Genera un archivo *.dll* o *.exe* que se ejecuta en el contenedor de la aplicación de Windows, como salida.</span><span class="sxs-lookup"><span data-stu-id="06853-126">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="06853-127">**/arm**</span><span class="sxs-lookup"><span data-stu-id="06853-127">**/arm**</span></span>|<span data-ttu-id="06853-128">Especifica Advanced RISC Machine (ARM) como procesador de destino.</span><span class="sxs-lookup"><span data-stu-id="06853-128">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="06853-129">Si no se especifican los bits de la imagen, el valor predeterminado es **/32bitpreferred**.</span><span class="sxs-lookup"><span data-stu-id="06853-129">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="06853-130">**/base:** `integer`</span><span class="sxs-lookup"><span data-stu-id="06853-130">**/base:** `integer`</span></span>|<span data-ttu-id="06853-131">Establece ImageBase en el valor especificado por `integer` en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="06853-131">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="06853-132">Si se especifica la directiva IL .imagebase en el archivo, esta opción la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="06853-132">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="06853-133">**/clock**</span><span class="sxs-lookup"><span data-stu-id="06853-133">**/clock**</span></span>|<span data-ttu-id="06853-134">Mide e informa de los siguientes tiempos de compilación en milisegundos para el archivo de código fuente .il especificado:</span><span class="sxs-lookup"><span data-stu-id="06853-134">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="06853-135">**Total Run**: Tiempo total empleado en la ejecución de todas las operaciones específicas que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="06853-135">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="06853-136">**Startup**: Carga y apertura del archivo.</span><span class="sxs-lookup"><span data-stu-id="06853-136">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="06853-137">**Emitting MD**: Emisión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="06853-137">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="06853-138">**Ref to Def Resolution**: Resolución de referencias a definiciones del archivo.</span><span class="sxs-lookup"><span data-stu-id="06853-138">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="06853-139">**CEE File Generation**: Generación de la imagen de archivo en memoria.</span><span class="sxs-lookup"><span data-stu-id="06853-139">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="06853-140">**PE File Writing**: Escritura de la imagen en un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="06853-140">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="06853-141">**/debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="06853-141">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="06853-142">Incluye información de depuración (nombres de variables locales y argumentos, y números de línea).</span><span class="sxs-lookup"><span data-stu-id="06853-142">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="06853-143">Crea un archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="06853-143">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="06853-144">**/debug** sin ningún valor adicional deshabilita la optimización JIT y usa puntos de secuencia del archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="06853-144">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="06853-145">**IMPL** deshabilita la optimización JIT y usa puntos de secuencia implícitos.</span><span class="sxs-lookup"><span data-stu-id="06853-145">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="06853-146">**OPT** habilita la optimización JIT y usa puntos de secuencia implícitos.</span><span class="sxs-lookup"><span data-stu-id="06853-146">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="06853-147">**/dll**</span><span class="sxs-lookup"><span data-stu-id="06853-147">**/dll**</span></span>|<span data-ttu-id="06853-148">Genera un archivo *.dll* como archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="06853-148">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="06853-149">**/enc:** `file`</span><span class="sxs-lookup"><span data-stu-id="06853-149">**/enc:** `file`</span></span>|<span data-ttu-id="06853-150">Crea deltas Editar y continuar a partir del archivo de código fuente especificado.</span><span class="sxs-lookup"><span data-stu-id="06853-150">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="06853-151">Este argumento es solo para uso académico, no se admite el uso comercial del mismo.</span><span class="sxs-lookup"><span data-stu-id="06853-151">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="06853-152">**/exe**</span><span class="sxs-lookup"><span data-stu-id="06853-152">**/exe**</span></span>|<span data-ttu-id="06853-153">Genera un archivo ejecutable como archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="06853-153">Produces an executable file as output.</span></span> <span data-ttu-id="06853-154">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="06853-154">This is the default.</span></span>|
|<span data-ttu-id="06853-155">**/flags:** `integer`</span><span class="sxs-lookup"><span data-stu-id="06853-155">**/flags:** `integer`</span></span>|<span data-ttu-id="06853-156">Establece ImageFlags en el valor especificado por `integer` en el encabezado de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="06853-156">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="06853-157">Si se especifica la directiva IL .corflags en el archivo, esta opción la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="06853-157">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="06853-158">Vea CorHdr.h, COMIMAGE_FLAGS para obtener una lista de los valores válidos para *integer*.</span><span class="sxs-lookup"><span data-stu-id="06853-158">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="06853-159">**/fold**</span><span class="sxs-lookup"><span data-stu-id="06853-159">**/fold**</span></span>|<span data-ttu-id="06853-160">Forma un solo cuerpo a partir de cuerpos de método idénticos.</span><span class="sxs-lookup"><span data-stu-id="06853-160">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="06853-161">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="06853-161">/**highentropyva**</span></span>|<span data-ttu-id="06853-162">Genera un archivo ejecutable de salida que admite la selección aleatoria del diseño del espacio de direcciones (ASLR) de alta entropía.</span><span class="sxs-lookup"><span data-stu-id="06853-162">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="06853-163">(Es el valor predeterminado de **/appcontainer**).</span><span class="sxs-lookup"><span data-stu-id="06853-163">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="06853-164">**/include:** `includePath`</span><span class="sxs-lookup"><span data-stu-id="06853-164">**/include:** `includePath`</span></span>|<span data-ttu-id="06853-165">Establece una ruta de acceso para buscar los archivos incluidos con `#include`.</span><span class="sxs-lookup"><span data-stu-id="06853-165">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="06853-166">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="06853-166">**/itanium**</span></span>|<span data-ttu-id="06853-167">Especifica Intel Itanium como procesador de destino.</span><span class="sxs-lookup"><span data-stu-id="06853-167">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="06853-168">Si no se especifican los bits de la imagen, el valor predeterminado es **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="06853-168">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="06853-169">**/key:** `keyFile`</span><span class="sxs-lookup"><span data-stu-id="06853-169">**/key:** `keyFile`</span></span>|<span data-ttu-id="06853-170">Compila `filename` con una firma segura mediante la clave privada contenida en `keyFile`.</span><span class="sxs-lookup"><span data-stu-id="06853-170">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="06853-171">**/key:**  @`keySource`</span><span class="sxs-lookup"><span data-stu-id="06853-171">**/key:** @`keySource`</span></span>|<span data-ttu-id="06853-172">Compila `filename` con una firma segura mediante la clave privada generada en `keySource`.</span><span class="sxs-lookup"><span data-stu-id="06853-172">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="06853-173">**/listing**</span><span class="sxs-lookup"><span data-stu-id="06853-173">**/listing**</span></span>|<span data-ttu-id="06853-174">Genera un archivo del lista en la salida estándar.</span><span class="sxs-lookup"><span data-stu-id="06853-174">Produces a listing file on the standard output.</span></span> <span data-ttu-id="06853-175">Si se omite esta opción, no se genera ningún archivo de lista.</span><span class="sxs-lookup"><span data-stu-id="06853-175">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="06853-176">Este parámetro no es compatible con .NET Framework 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="06853-176">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="06853-177">**/mdv:** `versionString`</span><span class="sxs-lookup"><span data-stu-id="06853-177">**/mdv:** `versionString`</span></span>|<span data-ttu-id="06853-178">Establece la cadena de versión de metadatos.</span><span class="sxs-lookup"><span data-stu-id="06853-178">Sets the metadata version string.</span></span>|
|<span data-ttu-id="06853-179">**/msv:** `major`.`minor`</span><span class="sxs-lookup"><span data-stu-id="06853-179">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="06853-180">Establece la versión del flujo de metadatos, donde `major` y `minor` son valores enteros.</span><span class="sxs-lookup"><span data-stu-id="06853-180">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="06853-181">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="06853-181">**/noautoinherit**</span></span>|<span data-ttu-id="06853-182">Deshabilita la herencia predeterminada de <xref:System.Object> cuando no se especifica ninguna clase base.</span><span class="sxs-lookup"><span data-stu-id="06853-182">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="06853-183">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="06853-183">**/nocorstub**</span></span>|<span data-ttu-id="06853-184">Suprime la generación de código auxiliar de CORExeMain.</span><span class="sxs-lookup"><span data-stu-id="06853-184">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="06853-185">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="06853-185">**/nologo**</span></span>|<span data-ttu-id="06853-186">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06853-186">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="06853-187">**/output:** `file.ext`</span><span class="sxs-lookup"><span data-stu-id="06853-187">**/output:** `file.ext`</span></span>|<span data-ttu-id="06853-188">Especifica el nombre y la extensión del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="06853-188">Specifies the output file name and extension.</span></span> <span data-ttu-id="06853-189">De forma predeterminada, el nombre del archivo de salida coincide con el nombre del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="06853-189">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="06853-190">La extensión predeterminada es *.exe*.</span><span class="sxs-lookup"><span data-stu-id="06853-190">The default extension is *.exe*.</span></span> <span data-ttu-id="06853-191">Si se especifica la opción **/dll**, la extensión predeterminada es *.dll*.</span><span class="sxs-lookup"><span data-stu-id="06853-191">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="06853-192">**Nota:** La especificación de **/output**:myfile.dll no establece la opción **/dll**.</span><span class="sxs-lookup"><span data-stu-id="06853-192">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="06853-193">Si no se especifica **/dll**, el resultado será un archivo ejecutable denominado *myfile.dll*.</span><span class="sxs-lookup"><span data-stu-id="06853-193">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="06853-194">**/optimize**</span><span class="sxs-lookup"><span data-stu-id="06853-194">**/optimize**</span></span>|<span data-ttu-id="06853-195">Optimiza las instrucciones largas en instrucciones cortas.</span><span class="sxs-lookup"><span data-stu-id="06853-195">Optimizes long instructions to short.</span></span> <span data-ttu-id="06853-196">Por ejemplo, `br` en `br.s`.</span><span class="sxs-lookup"><span data-stu-id="06853-196">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="06853-197">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="06853-197">**/pe64**</span></span>|<span data-ttu-id="06853-198">Crea una imagen de 64 bits (PE32+).</span><span class="sxs-lookup"><span data-stu-id="06853-198">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="06853-199">Si no se especifica un procesador de destino, el valor predeterminado es `/itanium`.</span><span class="sxs-lookup"><span data-stu-id="06853-199">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="06853-200">**/pdb**</span><span class="sxs-lookup"><span data-stu-id="06853-200">**/pdb**</span></span>|<span data-ttu-id="06853-201">Crea un archivo PDB sin habilitar un seguimiento de la información de depuración.</span><span class="sxs-lookup"><span data-stu-id="06853-201">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="06853-202">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="06853-202">**/quiet**</span></span>|<span data-ttu-id="06853-203">Especifica el modo silencioso; no se notifica el progreso del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="06853-203">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="06853-204">**/resource:** `file.res`</span><span class="sxs-lookup"><span data-stu-id="06853-204">**/resource:** `file.res`</span></span>|<span data-ttu-id="06853-205">Incluye el archivo de recursos especificado con formato \*.res en el archivo *.exe* o *.dll* resultante.</span><span class="sxs-lookup"><span data-stu-id="06853-205">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="06853-206">Solo se puede especificar un archivo .res con la opción **/resource** .</span><span class="sxs-lookup"><span data-stu-id="06853-206">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="06853-207">**/ssver:** `int`.`int`</span><span class="sxs-lookup"><span data-stu-id="06853-207">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="06853-208">Establece el número de versión del subsistema en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="06853-208">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="06853-209">Para **/appcontainer** y **/arm** el número de versión mínimo es 6.02.</span><span class="sxs-lookup"><span data-stu-id="06853-209">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="06853-210">**/stack:** `stackSize`</span><span class="sxs-lookup"><span data-stu-id="06853-210">**/stack:** `stackSize`</span></span>|<span data-ttu-id="06853-211">Establece el valor de SizeOfStackReserve en el encabezado NT opcional en `stackSize`.</span><span class="sxs-lookup"><span data-stu-id="06853-211">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="06853-212">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="06853-212">**/stripreloc**</span></span>|<span data-ttu-id="06853-213">Especifica que no es necesaria ninguna reubicación base.</span><span class="sxs-lookup"><span data-stu-id="06853-213">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="06853-214">**/subsystem:** `integer`</span><span class="sxs-lookup"><span data-stu-id="06853-214">**/subsystem:** `integer`</span></span>|<span data-ttu-id="06853-215">Establece subsystem en el valor especificado por `integer` en el encabezado NT opcional.</span><span class="sxs-lookup"><span data-stu-id="06853-215">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="06853-216">Si se especifica la directiva IL .subsystem en el archivo, este comando la reemplaza.</span><span class="sxs-lookup"><span data-stu-id="06853-216">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="06853-217">Vea winnt.h, IMAGE_SUBSYSTEM para obtener una lista de los valores válidos para `integer`.</span><span class="sxs-lookup"><span data-stu-id="06853-217">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="06853-218">**/x64**</span><span class="sxs-lookup"><span data-stu-id="06853-218">**/x64**</span></span>|<span data-ttu-id="06853-219">Especifica un procesador AMD de 64 bits como procesador de destino.</span><span class="sxs-lookup"><span data-stu-id="06853-219">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="06853-220">Si no se especifican los bits de la imagen, el valor predeterminado es **/pe64**.</span><span class="sxs-lookup"><span data-stu-id="06853-220">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="06853-221">**/?**</span><span class="sxs-lookup"><span data-stu-id="06853-221">**/?**</span></span>|<span data-ttu-id="06853-222">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="06853-222">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="06853-223">Ninguna de las opciones de *Ilasm.exe* distingue entre mayúsculas y minúsculas, y se reconocen mediante las tres primeras letras.</span><span class="sxs-lookup"><span data-stu-id="06853-223">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="06853-224">Por ejemplo, **/lis** equivale a **/listing** y **/res**:myresfile.res equivale a **/resource**:myresfile.res. Las opciones que especifican argumentos aceptan un signo de dos puntos (:) o un signo igual (=) como separador entre la opción y el argumento.</span><span class="sxs-lookup"><span data-stu-id="06853-224">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="06853-225">Por ejemplo, **/output**:*file.ext* es equivalente a **/output**=*file.ext*.</span><span class="sxs-lookup"><span data-stu-id="06853-225">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="06853-226">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06853-226">Remarks</span></span>

<span data-ttu-id="06853-227">El Ensamblador de IL ayuda a los proveedores de herramientas a diseñar e implementar generadores IL.</span><span class="sxs-lookup"><span data-stu-id="06853-227">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="06853-228">Mediante el uso de *Ilasm.exe*, los desarrolladores de herramientas y compiladores se pueden concentrar en la generación de IL y metadatos sin necesidad de preocuparse por la emisión de IL en el formato de archivo PE.</span><span class="sxs-lookup"><span data-stu-id="06853-228">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="06853-229">Al igual que otros compiladores orientados al tiempo de ejecución, como C# y Visual Basic, *Ilasm.exe* no genera archivos objeto intermedios y no requiere una etapa de vinculación para crear un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="06853-229">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="06853-230">El Ensamblador de IL puede expresar todos los metadatos existentes y las características de IL que caracterizan a los lenguajes de programación orientados al runtime.</span><span class="sxs-lookup"><span data-stu-id="06853-230">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="06853-231">Esto permite que el código administrado escrito en cualquiera de estos lenguajes de programación se pueda expresar en el Ensamblador de IL y compilar con *Ilasm.exe* de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="06853-231">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="06853-232">Si la última línea de código del archivo de código fuente .il no tiene espacio en blanco al final o un carácter de fin de línea, podría producirse un error en la compilación.</span><span class="sxs-lookup"><span data-stu-id="06853-232">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="06853-233">Se puede usar *Ilasm.exe* conjuntamente con su herramienta complementaria [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="06853-233">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="06853-234">*Ildasm.exe* toma un archivo PE que contiene código IL y crea un archivo de texto adecuado como entrada para *Ilasm.exe*.</span><span class="sxs-lookup"><span data-stu-id="06853-234">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="06853-235">Esta técnica es muy útil cuando, por ejemplo, se compila código en un lenguaje de programación que no admite todos los atributos de metadatos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="06853-235">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="06853-236">Una vez compilado el código y ejecutada la salida mediante *Ildasm.exe*, el archivo de texto de IL resultante se puede editar manualmente para agregar los atributos que faltan.</span><span class="sxs-lookup"><span data-stu-id="06853-236">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="06853-237">Después, se puede ejecutar este archivo de texto mediante *Ilasm.exe* para producir un archivo ejecutable final.</span><span class="sxs-lookup"><span data-stu-id="06853-237">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="06853-238">También se puede usar esta técnica para generar un único archivo PE a partir de varios archivos PE generados originalmente por compiladores diferentes.</span><span class="sxs-lookup"><span data-stu-id="06853-238">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="06853-239">Actualmente no se puede usar esta técnica con archivos PE que contienen código nativo incrustado (por ejemplo, archivos PE generados por Visual C++).</span><span class="sxs-lookup"><span data-stu-id="06853-239">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="06853-240">Para que este uso combinado de *Ildasm.exe* e *Ilasm.exe* sea lo más preciso posible, de forma predeterminada, el ensamblador no sustituye las codificaciones cortas por las largas que se hayan podido escribir en los códigos fuente de IL (o que haya emitido otro compilador).</span><span class="sxs-lookup"><span data-stu-id="06853-240">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="06853-241">Use la opción **/optimize** para sustituir las codificaciones cortas siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="06853-241">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="06853-242">*Ildasm.exe* solo funciona en archivos existentes en disco.</span><span class="sxs-lookup"><span data-stu-id="06853-242">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="06853-243">No funciona en archivos instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="06853-243">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="06853-244">Para obtener más información sobre la gramática de IL, vea el archivo asmparse.grammar en Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="06853-244">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="version-information"></a><span data-ttu-id="06853-245">Información de versión</span><span class="sxs-lookup"><span data-stu-id="06853-245">Version Information</span></span>

<span data-ttu-id="06853-246">A partir de .NET Framework 4.5, se puede asociar un atributo personalizado a una implementación de interfaz mediante código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="06853-246">Starting with the .NET Framework 4.5, you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

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

<span data-ttu-id="06853-247">A partir de .NET Framework 4.5, se puede especificar un objeto binario grande (BLOB) de serialización arbitraria mediante su representación binaria sin formato, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="06853-247">Starting with the .NET Framework 4.5, you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="06853-248">Para obtener más información sobre la gramática de IL, vea el archivo asmparse.grammar en Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="06853-248">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="06853-249">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="06853-249">Examples</span></span>

<span data-ttu-id="06853-250">El comando siguiente ensambla el archivo IL *myTestFile.il* y genera el archivo ejecutable *myTestFile.exe*.</span><span class="sxs-lookup"><span data-stu-id="06853-250">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="06853-251">El comando siguiente ensambla el archivo IL *myTestFile.il* y genera el archivo *.dll* *myTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="06853-251">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="06853-252">El comando siguiente ensambla el archivo IL *myTestFile.il* y genera el archivo *.dll* *myNewTestFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="06853-252">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="06853-253">En el siguiente ejemplo de código se muestra una aplicación muy simple que muestra "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="06853-253">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="06853-254">en la consola.</span><span class="sxs-lookup"><span data-stu-id="06853-254">to the console.</span></span> <span data-ttu-id="06853-255">Puede compilar este código y, después, usar la herramienta [*Ildasm.exe*](ildasm-exe-il-disassembler.md) para generar un archivo IL.</span><span class="sxs-lookup"><span data-stu-id="06853-255">You can compile this code and then use the [*Ildasm.exe*](ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

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

<span data-ttu-id="06853-256">El siguiente ejemplo de código IL se corresponde con el ejemplo de código de C# anterior.</span><span class="sxs-lookup"><span data-stu-id="06853-256">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="06853-257">Puede compilar este código en un ensamblado con la herramienta Ensamblador de IL.</span><span class="sxs-lookup"><span data-stu-id="06853-257">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="06853-258">Tanto el ejemplo de código IL como el de C# muestran "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="06853-258">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="06853-259">en la consola.</span><span class="sxs-lookup"><span data-stu-id="06853-259">to the console.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="06853-260">Vea también</span><span class="sxs-lookup"><span data-stu-id="06853-260">See also</span></span>

- [<span data-ttu-id="06853-261">Herramientas</span><span class="sxs-lookup"><span data-stu-id="06853-261">Tools</span></span>](index.md)
- [<span data-ttu-id="06853-262">*Ildasm.exe* (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="06853-262">*Ildasm.exe* (IL Disassembler)</span></span>](ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="06853-263">Proceso de ejecución administrada</span><span class="sxs-lookup"><span data-stu-id="06853-263">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="06853-264">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="06853-264">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
