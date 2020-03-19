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
ms.openlocfilehash: 9d5f8c80937c36e975d42d6efb0a83295cb28be9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73104983"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="20ccb-102">Peverify.exe (Herramienta PEVerify)</span><span class="sxs-lookup"><span data-stu-id="20ccb-102">Peverify.exe (PEVerify Tool)</span></span>
<span data-ttu-id="20ccb-103">La herramienta PEVerify ayuda a los desarrolladores que generan lenguaje intermedio de Microsoft (MSIL) (como autores de compiladores, desarrolladores de motores de scripts, etc.) a determinar si el código MSIL y los metadatos asociados satisfacen los requisitos de seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="20ccb-103">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers, script engine developers, and so on) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="20ccb-104">Algunos compiladores solo generan código con seguridad de tipos comprobable si se evita el uso de determinadas construcciones de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="20ccb-104">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="20ccb-105">Si, como desarrollador, está utilizando un compilador con estas características, puede que desee comprobar que no ha puesto en peligro la seguridad de tipos del código.</span><span class="sxs-lookup"><span data-stu-id="20ccb-105">If, as a developer, you are using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="20ccb-106">Para ello, ejecute la herramienta PEVerify en los archivos con el fin de comprobar el lenguaje MSIL y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="20ccb-106">In this situation, you can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="20ccb-107">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20ccb-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="20ccb-108">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="20ccb-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="20ccb-109">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="20ccb-109">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="20ccb-110">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20ccb-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ccb-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20ccb-111">Syntax</span></span>  
  
```console  
peverify filename [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="20ccb-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20ccb-112">Parameters</span></span>  
  
|<span data-ttu-id="20ccb-113">Argumento</span><span class="sxs-lookup"><span data-stu-id="20ccb-113">Argument</span></span>|<span data-ttu-id="20ccb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="20ccb-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="20ccb-115">*filename*</span><span class="sxs-lookup"><span data-stu-id="20ccb-115">*filename*</span></span>|<span data-ttu-id="20ccb-116">Archivo portable ejecutable (PE) para el que se comprueban el lenguaje MSIL y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="20ccb-116">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="20ccb-117">Opción</span><span class="sxs-lookup"><span data-stu-id="20ccb-117">Option</span></span>|<span data-ttu-id="20ccb-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="20ccb-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="20ccb-119">**/break=** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="20ccb-119">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="20ccb-120">Anula la comprobación si se generan tantos errores como indica *maxErrorCount*.</span><span class="sxs-lookup"><span data-stu-id="20ccb-120">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="20ccb-121">Este parámetro no es compatible con .NET Framework versión 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="20ccb-121">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="20ccb-122">**/clock**</span><span class="sxs-lookup"><span data-stu-id="20ccb-122">**/clock**</span></span>|<span data-ttu-id="20ccb-123">Mide los siguientes tiempos de comprobación en milisegundos y los notifica:</span><span class="sxs-lookup"><span data-stu-id="20ccb-123">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="20ccb-124">**MD Val. cycle**</span><span class="sxs-lookup"><span data-stu-id="20ccb-124">**MD Val. cycle**</span></span><br /> <span data-ttu-id="20ccb-125">Ciclo de validación de metadatos</span><span class="sxs-lookup"><span data-stu-id="20ccb-125">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="20ccb-126">**MD Val. pure**</span><span class="sxs-lookup"><span data-stu-id="20ccb-126">**MD Val. pure**</span></span><br /> <span data-ttu-id="20ccb-127">Validación pura de metadatos</span><span class="sxs-lookup"><span data-stu-id="20ccb-127">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="20ccb-128">**IL Ver. cycle**</span><span class="sxs-lookup"><span data-stu-id="20ccb-128">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="20ccb-129">Ciclo de comprobación del Lenguaje intermedio de Microsoft (MSIL)</span><span class="sxs-lookup"><span data-stu-id="20ccb-129">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="20ccb-130">**IL Ver pure**</span><span class="sxs-lookup"><span data-stu-id="20ccb-130">**IL Ver pure**</span></span><br /> <span data-ttu-id="20ccb-131">Comprobación pura de MSIL</span><span class="sxs-lookup"><span data-stu-id="20ccb-131">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="20ccb-132">Los valores de **MD Val. cycle** e **IL Ver. cycle** incluyen el tiempo requerido para realizar los procedimientos necesarios de inicio y de cierre.</span><span class="sxs-lookup"><span data-stu-id="20ccb-132">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="20ccb-133">Los valores de **MD Val. pure** e **IL Ver pure** reflejan el tiempo requerido únicamente para realizar la validación o comprobación.</span><span class="sxs-lookup"><span data-stu-id="20ccb-133">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="20ccb-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="20ccb-134">**/help**</span></span>|<span data-ttu-id="20ccb-135">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="20ccb-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="20ccb-136">**/hresult**</span><span class="sxs-lookup"><span data-stu-id="20ccb-136">**/hresult**</span></span>|<span data-ttu-id="20ccb-137">Muestra los códigos de error en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="20ccb-137">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="20ccb-138">**/ignore=** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="20ccb-138">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="20ccb-139">Omite los códigos de error especificados.</span><span class="sxs-lookup"><span data-stu-id="20ccb-139">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="20ccb-140">**/ignore=@** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="20ccb-140">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="20ccb-141">Omite los códigos de error enumerados en el archivo de respuesta especificado.</span><span class="sxs-lookup"><span data-stu-id="20ccb-141">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="20ccb-142">**/il**</span><span class="sxs-lookup"><span data-stu-id="20ccb-142">**/il**</span></span>|<span data-ttu-id="20ccb-143">Realiza comprobaciones de la seguridad de tipos de MSIL en los métodos implementados en el ensamblado especificado por *filename*.</span><span class="sxs-lookup"><span data-stu-id="20ccb-143">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="20ccb-144">La herramienta devuelve descripciones detalladas de cada uno de los problemas encontrados, salvo que se especifique la opción **/quiet**.</span><span class="sxs-lookup"><span data-stu-id="20ccb-144">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="20ccb-145">**/md**</span><span class="sxs-lookup"><span data-stu-id="20ccb-145">**/md**</span></span>|<span data-ttu-id="20ccb-146">Realiza comprobaciones de validación de metadatos en el ensamblado especificado por *filename*.</span><span class="sxs-lookup"><span data-stu-id="20ccb-146">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="20ccb-147">Para ello recorre la estructura completa de metadatos en el archivo y genera un informe de todos los problemas de validación encontrados.</span><span class="sxs-lookup"><span data-stu-id="20ccb-147">This walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="20ccb-148">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="20ccb-148">**/nologo**</span></span>|<span data-ttu-id="20ccb-149">Suprime la presentación de la versión del producto y de la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="20ccb-149">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="20ccb-150">**/nosymbols**</span><span class="sxs-lookup"><span data-stu-id="20ccb-150">**/nosymbols**</span></span>|<span data-ttu-id="20ccb-151">En .NET Framework versión 2.0, se suprimen los números de línea para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="20ccb-151">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="20ccb-152">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="20ccb-152">**/quiet**</span></span>|<span data-ttu-id="20ccb-153">Especifica el modo silencioso; suprime la salida de los informes relativos a problemas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="20ccb-153">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="20ccb-154">No obstante, Peverify.exe notifica si el archivo tiene seguridad de tipos, aunque no proporciona información sobre los problemas que impiden comprobar la seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="20ccb-154">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="20ccb-155">Comprueba solo los métodos transparentes.</span><span class="sxs-lookup"><span data-stu-id="20ccb-155">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="20ccb-156">**/unique**</span><span class="sxs-lookup"><span data-stu-id="20ccb-156">**/unique**</span></span>|<span data-ttu-id="20ccb-157">Omite la repetición de códigos de error.</span><span class="sxs-lookup"><span data-stu-id="20ccb-157">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="20ccb-158">**/verbose**</span><span class="sxs-lookup"><span data-stu-id="20ccb-158">**/verbose**</span></span>|<span data-ttu-id="20ccb-159">En .NET Framework versión 2.0, se muestra información adicional en los mensajes de comprobación de MSIL.</span><span class="sxs-lookup"><span data-stu-id="20ccb-159">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="20ccb-160">**/?**</span><span class="sxs-lookup"><span data-stu-id="20ccb-160">**/?**</span></span>|<span data-ttu-id="20ccb-161">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="20ccb-161">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20ccb-162">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20ccb-162">Remarks</span></span>  
 <span data-ttu-id="20ccb-163">Common Language Runtime se basa en la ejecución con seguridad de tipos del código de la aplicación para ayudar a imponer mecanismos de aislamiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="20ccb-163">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="20ccb-164">Normalmente, el código en el que no [se puede comprobar la seguridad de tipos](../../standard/security/key-security-concepts.md#type-safety-and-security) no se puede ejecutar, aunque puede establecer una directiva de seguridad para permitir la ejecución de código de confianza pero que no se puede comprobar.</span><span class="sxs-lookup"><span data-stu-id="20ccb-164">Normally, code that is not [verifiably type safe](../../standard/security/key-security-concepts.md#type-safety-and-security) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="20ccb-165">Si no se especifican las opciones **/md** o **/il**, Peverify.exe realiza ambos tipos de comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="20ccb-165">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="20ccb-166">Primero realiza comprobaciones de tipo **/md**.</span><span class="sxs-lookup"><span data-stu-id="20ccb-166">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="20ccb-167">Si no hay errores, realiza comprobaciones de tipo **/il**.</span><span class="sxs-lookup"><span data-stu-id="20ccb-167">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="20ccb-168">Si especifica ambas opciones ( **/md** e **/il**), se realizarán comprobaciones de tipo **/il** aunque existan errores en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="20ccb-168">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="20ccb-169">Así, si no hay ningún error de metadatos, **peverify** *filename* equivale a **peverify** *filename* **/md** **/il**.</span><span class="sxs-lookup"><span data-stu-id="20ccb-169">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="20ccb-170">Peverify.exe realiza comprobaciones exhaustivas de MSIL basándose en el análisis del flujo de datos y en una lista que contiene centenares de reglas sobre metadatos válidos.</span><span class="sxs-lookup"><span data-stu-id="20ccb-170">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="20ccb-171">Para obtener información detallada sobre las comprobaciones que realiza Peverify.exe, vea las secciones sobre especificaciones para la validación de metadatos y para el conjunto de instrucciones de MSIL en la carpeta Tools Developers Guide de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="20ccb-171">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the Windows SDK.</span></span>  
  
 <span data-ttu-id="20ccb-172">Tenga en cuenta que .NET Framework versión 2.0 o posterior admite devoluciones de los datos `byref` que se puedan comprobar especificadas mediante las siguientes instrucciones de MSIL: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` y `unbox`.</span><span class="sxs-lookup"><span data-stu-id="20ccb-172">Note that the .NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="20ccb-173">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="20ccb-173">Examples</span></span>  
 <span data-ttu-id="20ccb-174">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="20ccb-174">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```console  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="20ccb-175">Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.</span><span class="sxs-lookup"><span data-stu-id="20ccb-175">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="20ccb-176">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="20ccb-176">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="20ccb-177">La herramienta muestra el tiempo necesario para ejecutar estas comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="20ccb-177">The tool displays the time required to perform these checks.</span></span>  
  
```console  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="20ccb-178">Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.</span><span class="sxs-lookup"><span data-stu-id="20ccb-178">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="20ccb-179">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="20ccb-179">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="20ccb-180">No obstante, Peverify.exe se detiene cuando llega al número máximo de errores (100).</span><span class="sxs-lookup"><span data-stu-id="20ccb-180">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="20ccb-181">La herramienta también omite los códigos de error especificados.</span><span class="sxs-lookup"><span data-stu-id="20ccb-181">The tool also ignores the specified error codes.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="20ccb-182">El comando siguiente genera el mismo resultado que el ejemplo anterior, pero especifica los códigos de error que se omiten en el archivo de respuesta `ignoreErrors.rsp`.</span><span class="sxs-lookup"><span data-stu-id="20ccb-182">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="20ccb-183">El archivo de respuesta puede contener una lista de códigos de error separados por comas.</span><span class="sxs-lookup"><span data-stu-id="20ccb-183">The response file can contain a comma-separated list of error codes.</span></span>  
  
```text
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="20ccb-184">El archivo de respuesta también puede tener un formato que incluya un código de error por línea.</span><span class="sxs-lookup"><span data-stu-id="20ccb-184">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```text
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="20ccb-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="20ccb-185">See also</span></span>

- [<span data-ttu-id="20ccb-186">Herramientas</span><span class="sxs-lookup"><span data-stu-id="20ccb-186">Tools</span></span>](index.md)
- [<span data-ttu-id="20ccb-187">Escritura de código con seguridad de tipos comprobable</span><span class="sxs-lookup"><span data-stu-id="20ccb-187">Writing Verifiably Type-Safe Code</span></span>](../misc/code-access-security-basics.md#typesafe_code)
- [<span data-ttu-id="20ccb-188">Seguridad y protección de tipos</span><span class="sxs-lookup"><span data-stu-id="20ccb-188">Type Safety and Security</span></span>](../../standard/security/key-security-concepts.md#type-safety-and-security)
- [<span data-ttu-id="20ccb-189">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="20ccb-189">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
