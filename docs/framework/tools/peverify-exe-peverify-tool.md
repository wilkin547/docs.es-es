---
title: Peverify.exe (Herramienta PEVerify)
ms.date: 03/30/2017
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e70324192f56214d273ae2a819a9c08be7d49b1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409232"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="c3194-102">Peverify.exe (Herramienta PEVerify)</span><span class="sxs-lookup"><span data-stu-id="c3194-102">Peverify.exe (PEVerify Tool)</span></span>
<span data-ttu-id="c3194-103">La herramienta PEVerify ayuda a los desarrolladores que generan lenguaje intermedio de Microsoft (MSIL) (como autores de compiladores, desarrolladores de motores de scripts, etc.) a determinar si el código MSIL y los metadatos asociados satisfacen los requisitos de seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="c3194-103">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers, script engine developers, and so on) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="c3194-104">Algunos compiladores solo generan código con seguridad de tipos comprobable si se evita el uso de determinadas construcciones de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="c3194-104">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="c3194-105">Si, como desarrollador, está utilizando un compilador con estas características, puede que desee comprobar que no ha puesto en peligro la seguridad de tipos del código.</span><span class="sxs-lookup"><span data-stu-id="c3194-105">If, as a developer, you are using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="c3194-106">Para ello, ejecute la herramienta PEVerify en los archivos con el fin de comprobar el lenguaje MSIL y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c3194-106">In this situation, you can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="c3194-107">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c3194-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="c3194-108">Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores (o el Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="c3194-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="c3194-109">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c3194-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="c3194-110">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3194-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3194-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3194-111">Syntax</span></span>  
  
```  
peverify filename [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3194-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3194-112">Parameters</span></span>  
  
|<span data-ttu-id="c3194-113">Argumento</span><span class="sxs-lookup"><span data-stu-id="c3194-113">Argument</span></span>|<span data-ttu-id="c3194-114">Description</span><span class="sxs-lookup"><span data-stu-id="c3194-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c3194-115">*filename*</span><span class="sxs-lookup"><span data-stu-id="c3194-115">*filename*</span></span>|<span data-ttu-id="c3194-116">Archivo portable ejecutable (PE) para el que se comprueban el lenguaje MSIL y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c3194-116">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="c3194-117">Opción</span><span class="sxs-lookup"><span data-stu-id="c3194-117">Option</span></span>|<span data-ttu-id="c3194-118">Description</span><span class="sxs-lookup"><span data-stu-id="c3194-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c3194-119">**/break=** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="c3194-119">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="c3194-120">Anula la comprobación si se generan tantos errores como indica *maxErrorCount*.</span><span class="sxs-lookup"><span data-stu-id="c3194-120">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="c3194-121">Este parámetro no es compatible con .NET Framework versión 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="c3194-121">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="c3194-122">**/clock**</span><span class="sxs-lookup"><span data-stu-id="c3194-122">**/clock**</span></span>|<span data-ttu-id="c3194-123">Mide los siguientes tiempos de comprobación en milisegundos y los notifica:</span><span class="sxs-lookup"><span data-stu-id="c3194-123">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="c3194-124">**MD Val. cycle**</span><span class="sxs-lookup"><span data-stu-id="c3194-124">**MD Val. cycle**</span></span><br /> <span data-ttu-id="c3194-125">Ciclo de validación de metadatos</span><span class="sxs-lookup"><span data-stu-id="c3194-125">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="c3194-126">**MD Val. pure**</span><span class="sxs-lookup"><span data-stu-id="c3194-126">**MD Val. pure**</span></span><br /> <span data-ttu-id="c3194-127">Validación pura de metadatos</span><span class="sxs-lookup"><span data-stu-id="c3194-127">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="c3194-128">**IL Ver. cycle**</span><span class="sxs-lookup"><span data-stu-id="c3194-128">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="c3194-129">Ciclo de comprobación del Lenguaje intermedio de Microsoft (MSIL)</span><span class="sxs-lookup"><span data-stu-id="c3194-129">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="c3194-130">**IL Ver pure**</span><span class="sxs-lookup"><span data-stu-id="c3194-130">**IL Ver pure**</span></span><br /> <span data-ttu-id="c3194-131">Comprobación pura de MSIL</span><span class="sxs-lookup"><span data-stu-id="c3194-131">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="c3194-132">Los valores de **MD Val. cycle** e **IL Ver. cycle** incluyen el tiempo requerido para realizar los procedimientos necesarios de inicio y de cierre.</span><span class="sxs-lookup"><span data-stu-id="c3194-132">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="c3194-133">Los valores de **MD Val. pure** e **IL Ver pure** reflejan el tiempo requerido únicamente para realizar la validación o comprobación.</span><span class="sxs-lookup"><span data-stu-id="c3194-133">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="c3194-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="c3194-134">**/help**</span></span>|<span data-ttu-id="c3194-135">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c3194-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="c3194-136">**/hresult**</span><span class="sxs-lookup"><span data-stu-id="c3194-136">**/hresult**</span></span>|<span data-ttu-id="c3194-137">Muestra los códigos de error en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="c3194-137">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="c3194-138">**/ignore=** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="c3194-138">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="c3194-139">Omite los códigos de error especificados.</span><span class="sxs-lookup"><span data-stu-id="c3194-139">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="c3194-140">**/ignore=@** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="c3194-140">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="c3194-141">Omite los códigos de error enumerados en el archivo de respuesta especificado.</span><span class="sxs-lookup"><span data-stu-id="c3194-141">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="c3194-142">**/il**</span><span class="sxs-lookup"><span data-stu-id="c3194-142">**/il**</span></span>|<span data-ttu-id="c3194-143">Realiza comprobaciones de la seguridad de tipos de MSIL en los métodos implementados en el ensamblado especificado por *filename*.</span><span class="sxs-lookup"><span data-stu-id="c3194-143">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="c3194-144">La herramienta devuelve descripciones detalladas de cada uno de los problemas encontrados, salvo que se especifique la opción **/quiet**.</span><span class="sxs-lookup"><span data-stu-id="c3194-144">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="c3194-145">**/md**</span><span class="sxs-lookup"><span data-stu-id="c3194-145">**/md**</span></span>|<span data-ttu-id="c3194-146">Realiza comprobaciones de validación de metadatos en el ensamblado especificado por *filename*.</span><span class="sxs-lookup"><span data-stu-id="c3194-146">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="c3194-147">Para ello recorre la estructura completa de metadatos en el archivo y genera un informe de todos los problemas de validación encontrados.</span><span class="sxs-lookup"><span data-stu-id="c3194-147">This walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="c3194-148">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="c3194-148">**/nologo**</span></span>|<span data-ttu-id="c3194-149">Suprime la presentación de la versión del producto y de la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="c3194-149">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="c3194-150">**/nosymbols**</span><span class="sxs-lookup"><span data-stu-id="c3194-150">**/nosymbols**</span></span>|<span data-ttu-id="c3194-151">En .NET Framework versión 2.0, se suprimen los números de línea para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="c3194-151">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="c3194-152">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="c3194-152">**/quiet**</span></span>|<span data-ttu-id="c3194-153">Especifica el modo silencioso; suprime la salida de los informes relativos a problemas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="c3194-153">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="c3194-154">No obstante, Peverify.exe notifica si el archivo tiene seguridad de tipos, aunque no proporciona información sobre los problemas que impiden comprobar la seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="c3194-154">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="c3194-155">Comprueba solo los métodos transparentes.</span><span class="sxs-lookup"><span data-stu-id="c3194-155">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="c3194-156">**/unique**</span><span class="sxs-lookup"><span data-stu-id="c3194-156">**/unique**</span></span>|<span data-ttu-id="c3194-157">Omite la repetición de códigos de error.</span><span class="sxs-lookup"><span data-stu-id="c3194-157">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="c3194-158">**/verbose**</span><span class="sxs-lookup"><span data-stu-id="c3194-158">**/verbose**</span></span>|<span data-ttu-id="c3194-159">En .NET Framework versión 2.0, se muestra información adicional en los mensajes de comprobación de MSIL.</span><span class="sxs-lookup"><span data-stu-id="c3194-159">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="c3194-160">**/?**</span><span class="sxs-lookup"><span data-stu-id="c3194-160">**/?**</span></span>|<span data-ttu-id="c3194-161">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c3194-161">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3194-162">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3194-162">Remarks</span></span>  
 <span data-ttu-id="c3194-163">Common Language Runtime se basa en la ejecución con seguridad de tipos del código de la aplicación para ayudar a imponer mecanismos de aislamiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="c3194-163">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="c3194-164">Normalmente, el código en el que no [se puede comprobar la seguridad de tipos](http://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc) no se puede ejecutar, aunque puede establecer una directiva de seguridad para permitir la ejecución de código de confianza pero que no se puede comprobar.</span><span class="sxs-lookup"><span data-stu-id="c3194-164">Normally, code that is not [verifiably type safe](http://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="c3194-165">Si no se especifican las opciones **/md** o **/il**, Peverify.exe realiza ambos tipos de comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="c3194-165">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="c3194-166">Primero realiza comprobaciones de tipo **/md**.</span><span class="sxs-lookup"><span data-stu-id="c3194-166">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="c3194-167">Si no hay errores, realiza comprobaciones de tipo **/il**.</span><span class="sxs-lookup"><span data-stu-id="c3194-167">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="c3194-168">Si especifica ambas opciones (**/md** e **/il**), se realizarán comprobaciones de tipo **/il** aunque existan errores en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c3194-168">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="c3194-169">Así, si no hay ningún error de metadatos, **peverify** *filename* es equivalente a **peverify** *filename* **/md** **/il**.</span><span class="sxs-lookup"><span data-stu-id="c3194-169">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="c3194-170">Peverify.exe realiza comprobaciones exhaustivas de MSIL basándose en el análisis del flujo de datos y en una lista que contiene centenares de reglas sobre metadatos válidos.</span><span class="sxs-lookup"><span data-stu-id="c3194-170">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="c3194-171">Para obtener información detallada sobre las comprobaciones que realiza Peverify.exe, vea las secciones sobre especificaciones para la validación de metadatos y para el conjunto de instrucciones de MSIL en la carpeta Tools Developers Guide de [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3194-171">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="c3194-172">Tenga en cuenta que .NET Framework versión 2.0 o posterior admite devoluciones de los datos `byref` que se puedan comprobar especificadas mediante las siguientes instrucciones de MSIL: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` y `unbox`.</span><span class="sxs-lookup"><span data-stu-id="c3194-172">Note that the .NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c3194-173">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c3194-173">Examples</span></span>  
 <span data-ttu-id="c3194-174">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="c3194-174">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="c3194-175">Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.</span><span class="sxs-lookup"><span data-stu-id="c3194-175">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="c3194-176">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="c3194-176">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="c3194-177">La herramienta muestra el tiempo necesario para ejecutar estas comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="c3194-177">The tool displays the time required to perform these checks.</span></span>  
  
```  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="c3194-178">Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.</span><span class="sxs-lookup"><span data-stu-id="c3194-178">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="c3194-179">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="c3194-179">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="c3194-180">No obstante, Peverify.exe se detiene cuando llega al número máximo de errores (100).</span><span class="sxs-lookup"><span data-stu-id="c3194-180">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="c3194-181">La herramienta también omite los códigos de error especificados.</span><span class="sxs-lookup"><span data-stu-id="c3194-181">The tool also ignores the specified error codes.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="c3194-182">El comando siguiente genera el mismo resultado que el ejemplo anterior, pero especifica los códigos de error que se omiten en el archivo de respuesta `ignoreErrors.rsp`.</span><span class="sxs-lookup"><span data-stu-id="c3194-182">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="c3194-183">El archivo de respuesta puede contener una lista de códigos de error separados por comas.</span><span class="sxs-lookup"><span data-stu-id="c3194-183">The response file can contain a comma-separated list of error codes.</span></span>  
  
```  
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="c3194-184">El archivo de respuesta también puede tener un formato que incluya un código de error por línea.</span><span class="sxs-lookup"><span data-stu-id="c3194-184">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```  
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3194-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3194-185">See Also</span></span>  
 [<span data-ttu-id="c3194-186">Herramientas</span><span class="sxs-lookup"><span data-stu-id="c3194-186">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="c3194-187">NO ESTÁ EN LA COMPILACIÓN: Escribir código seguro comprobable</span><span class="sxs-lookup"><span data-stu-id="c3194-187">NIB: Writing Verifiably Type-Safe Code</span></span>](http://msdn.microsoft.com/library/d18f10ef-3b48-4f47-8726-96714021547b)  
 [<span data-ttu-id="c3194-188">Seguridad y protección de tipos</span><span class="sxs-lookup"><span data-stu-id="c3194-188">Type Safety and Security</span></span>](http://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc)  
 [<span data-ttu-id="c3194-189">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="c3194-189">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
