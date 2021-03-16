---
title: Peverify.exe (Herramienta PEVerify)
description: Use Peverify.exe (comprobación de ejecutable portable) para ayudar a determinar si el código y los metadatos del lenguaje intermedio de Microsoft (MSIL) cumplen los estándares de seguridad de tipos de .NET.
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
ms.openlocfilehash: b51b01e639719df7ecfde53819e3137813f7c46f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259255"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="2a27e-103">Peverify.exe (herramienta PEVerify)</span><span class="sxs-lookup"><span data-stu-id="2a27e-103">Peverify.exe (PEVerify tool)</span></span>

<span data-ttu-id="2a27e-104">La herramienta PEVerify ayuda a los desarrolladores que generan lenguaje intermedio de Microsoft (MSIL) (como autores de compiladores y desarrolladores de motores de scripts) a determinar si el código MSIL y los metadatos asociados satisfacen los requisitos de seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="2a27e-104">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers and script engine developers) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="2a27e-105">Algunos compiladores solo generan código con seguridad de tipos comprobable si se evita el uso de determinadas construcciones de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="2a27e-105">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="2a27e-106">Si utiliza un compilador con estas características, conviene que compruebe que no ha puesto en peligro la seguridad de tipos del código.</span><span class="sxs-lookup"><span data-stu-id="2a27e-106">If you're using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="2a27e-107">Puede ejecutar la herramienta PEVerify en los archivos con el fin de comprobar el lenguaje MSIL y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="2a27e-107">You can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="2a27e-108">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2a27e-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="2a27e-109">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="2a27e-109">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>
  
## <a name="syntax"></a><span data-ttu-id="2a27e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a27e-110">Syntax</span></span>  
  
```console  
peverify filename [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a27e-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a27e-111">Parameters</span></span>  
  
|<span data-ttu-id="2a27e-112">Argumento</span><span class="sxs-lookup"><span data-stu-id="2a27e-112">Argument</span></span>|<span data-ttu-id="2a27e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a27e-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="2a27e-114">*filename*</span><span class="sxs-lookup"><span data-stu-id="2a27e-114">*filename*</span></span>|<span data-ttu-id="2a27e-115">Archivo portable ejecutable (PE) para el que se comprueban el lenguaje MSIL y los metadatos.</span><span class="sxs-lookup"><span data-stu-id="2a27e-115">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="2a27e-116">Opción</span><span class="sxs-lookup"><span data-stu-id="2a27e-116">Option</span></span>|<span data-ttu-id="2a27e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a27e-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2a27e-118">**/break=** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="2a27e-118">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="2a27e-119">Anula la comprobación si se generan tantos errores como indica *maxErrorCount*.</span><span class="sxs-lookup"><span data-stu-id="2a27e-119">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="2a27e-120">Este parámetro no es compatible con .NET Framework versión 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2a27e-120">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="2a27e-121">**/clock**</span><span class="sxs-lookup"><span data-stu-id="2a27e-121">**/clock**</span></span>|<span data-ttu-id="2a27e-122">Mide los siguientes tiempos de comprobación en milisegundos y los notifica:</span><span class="sxs-lookup"><span data-stu-id="2a27e-122">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="2a27e-123">**MD Val. cycle**</span><span class="sxs-lookup"><span data-stu-id="2a27e-123">**MD Val. cycle**</span></span><br /> <span data-ttu-id="2a27e-124">Ciclo de validación de metadatos</span><span class="sxs-lookup"><span data-stu-id="2a27e-124">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="2a27e-125">**MD Val. pure**</span><span class="sxs-lookup"><span data-stu-id="2a27e-125">**MD Val. pure**</span></span><br /> <span data-ttu-id="2a27e-126">Validación pura de metadatos</span><span class="sxs-lookup"><span data-stu-id="2a27e-126">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="2a27e-127">**IL Ver. cycle**</span><span class="sxs-lookup"><span data-stu-id="2a27e-127">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="2a27e-128">Ciclo de comprobación del Lenguaje intermedio de Microsoft (MSIL)</span><span class="sxs-lookup"><span data-stu-id="2a27e-128">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="2a27e-129">**IL Ver pure**</span><span class="sxs-lookup"><span data-stu-id="2a27e-129">**IL Ver pure**</span></span><br /> <span data-ttu-id="2a27e-130">Comprobación pura de MSIL</span><span class="sxs-lookup"><span data-stu-id="2a27e-130">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="2a27e-131">Los valores de **MD Val. cycle** e **IL Ver. cycle** incluyen el tiempo requerido para realizar los procedimientos necesarios de inicio y de cierre.</span><span class="sxs-lookup"><span data-stu-id="2a27e-131">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="2a27e-132">Los valores de **MD Val. pure** e **IL Ver pure** reflejan el tiempo requerido únicamente para realizar la validación o comprobación.</span><span class="sxs-lookup"><span data-stu-id="2a27e-132">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="2a27e-133">**/help**</span><span class="sxs-lookup"><span data-stu-id="2a27e-133">**/help**</span></span>|<span data-ttu-id="2a27e-134">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="2a27e-134">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="2a27e-135">**/hresult**</span><span class="sxs-lookup"><span data-stu-id="2a27e-135">**/hresult**</span></span>|<span data-ttu-id="2a27e-136">Muestra los códigos de error en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="2a27e-136">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="2a27e-137">**/ignore=** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="2a27e-137">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="2a27e-138">Omite los códigos de error especificados.</span><span class="sxs-lookup"><span data-stu-id="2a27e-138">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="2a27e-139">**/ignore=@** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="2a27e-139">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="2a27e-140">Omite los códigos de error enumerados en el archivo de respuesta especificado.</span><span class="sxs-lookup"><span data-stu-id="2a27e-140">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="2a27e-141">**/il**</span><span class="sxs-lookup"><span data-stu-id="2a27e-141">**/il**</span></span>|<span data-ttu-id="2a27e-142">Realiza comprobaciones de la seguridad de tipos de MSIL en los métodos implementados en el ensamblado especificado por *filename*.</span><span class="sxs-lookup"><span data-stu-id="2a27e-142">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="2a27e-143">La herramienta devuelve descripciones detalladas de cada uno de los problemas encontrados, salvo que se especifique la opción **/quiet**.</span><span class="sxs-lookup"><span data-stu-id="2a27e-143">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="2a27e-144">**/md**</span><span class="sxs-lookup"><span data-stu-id="2a27e-144">**/md**</span></span>|<span data-ttu-id="2a27e-145">Realiza comprobaciones de validación de metadatos en el ensamblado especificado por *filename*.</span><span class="sxs-lookup"><span data-stu-id="2a27e-145">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="2a27e-146">Esta opción recorre la estructura completa de metadatos en el archivo y genera un informe de todos los problemas de validación encontrados.</span><span class="sxs-lookup"><span data-stu-id="2a27e-146">This option walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="2a27e-147">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="2a27e-147">**/nologo**</span></span>|<span data-ttu-id="2a27e-148">Suprime la presentación de la versión del producto y de la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="2a27e-148">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="2a27e-149">**/nosymbols**</span><span class="sxs-lookup"><span data-stu-id="2a27e-149">**/nosymbols**</span></span>|<span data-ttu-id="2a27e-150">En .NET Framework versión 2.0, se suprimen los números de línea para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="2a27e-150">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="2a27e-151">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="2a27e-151">**/quiet**</span></span>|<span data-ttu-id="2a27e-152">Especifica el modo silencioso; suprime la salida de los informes relativos a problemas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="2a27e-152">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="2a27e-153">No obstante, Peverify.exe notifica si el archivo tiene seguridad de tipos, aunque no proporciona información sobre los problemas que impiden comprobar la seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="2a27e-153">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="2a27e-154">Comprueba solo los métodos transparentes.</span><span class="sxs-lookup"><span data-stu-id="2a27e-154">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="2a27e-155">**/unique**</span><span class="sxs-lookup"><span data-stu-id="2a27e-155">**/unique**</span></span>|<span data-ttu-id="2a27e-156">Omite la repetición de códigos de error.</span><span class="sxs-lookup"><span data-stu-id="2a27e-156">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="2a27e-157">**/verbose**</span><span class="sxs-lookup"><span data-stu-id="2a27e-157">**/verbose**</span></span>|<span data-ttu-id="2a27e-158">En .NET Framework versión 2.0, se muestra información adicional en los mensajes de comprobación de MSIL.</span><span class="sxs-lookup"><span data-stu-id="2a27e-158">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="2a27e-159">**/?**</span><span class="sxs-lookup"><span data-stu-id="2a27e-159">**/?**</span></span>|<span data-ttu-id="2a27e-160">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="2a27e-160">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a27e-161">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a27e-161">Remarks</span></span>  

 <span data-ttu-id="2a27e-162">Common Language Runtime se basa en la ejecución con seguridad de tipos del código de la aplicación para ayudar a imponer mecanismos de aislamiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="2a27e-162">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="2a27e-163">Normalmente, el código en el que no [se puede comprobar la seguridad de tipos](../../standard/security/key-security-concepts.md#type-safety-and-security) no se puede ejecutar, aunque puede establecer una directiva de seguridad para permitir la ejecución de código de confianza pero que no se puede comprobar.</span><span class="sxs-lookup"><span data-stu-id="2a27e-163">Normally, code that is not [verifiably type safe](../../standard/security/key-security-concepts.md#type-safety-and-security) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="2a27e-164">Si no se especifican las opciones **/md** o **/il**, Peverify.exe realiza ambos tipos de comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="2a27e-164">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="2a27e-165">Primero realiza comprobaciones de tipo **/md**.</span><span class="sxs-lookup"><span data-stu-id="2a27e-165">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="2a27e-166">Si no hay errores, realiza comprobaciones de tipo **/il**.</span><span class="sxs-lookup"><span data-stu-id="2a27e-166">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="2a27e-167">Si especifica ambas opciones ( **/md** e **/il**), se realizarán comprobaciones de tipo **/il** aunque existan errores en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="2a27e-167">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="2a27e-168">Así, si no hay ningún error de metadatos, **peverify** *filename* equivale a **peverify** *filename* **/md** **/il**.</span><span class="sxs-lookup"><span data-stu-id="2a27e-168">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="2a27e-169">Peverify.exe realiza comprobaciones exhaustivas de MSIL basándose en el análisis del flujo de datos y en una lista que contiene centenares de reglas sobre metadatos válidos.</span><span class="sxs-lookup"><span data-stu-id="2a27e-169">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="2a27e-170">Para obtener información detallada sobre las comprobaciones que realiza Peverify.exe, vea las secciones sobre especificaciones para la validación de metadatos y para el conjunto de instrucciones de MSIL en la carpeta Tools Developers Guide de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="2a27e-170">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the Windows SDK.</span></span>  
  
<span data-ttu-id="2a27e-171">.NET Framework versión 2.0 o posterior admite devoluciones de `byref` comprobable especificadas mediante las siguientes instrucciones de MSIL: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` y `unbox`.</span><span class="sxs-lookup"><span data-stu-id="2a27e-171">.NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call`, and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2a27e-172">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2a27e-172">Examples</span></span>  

 <span data-ttu-id="2a27e-173">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="2a27e-173">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```console  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="2a27e-174">Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a27e-174">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="2a27e-175">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="2a27e-175">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="2a27e-176">La herramienta muestra el tiempo necesario para ejecutar estas comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="2a27e-176">The tool displays the time required to perform these checks.</span></span>  
  
```console  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="2a27e-177">Después de ejecutar la solicitud anterior correctamente, Peverify.exe muestra el mensaje siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a27e-177">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="2a27e-178">El comando siguiente realiza comprobaciones de validación de metadatos y comprobaciones de seguridad de tipos de MSIL en los métodos implementados en el ensamblado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="2a27e-178">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="2a27e-179">No obstante, Peverify.exe se detiene cuando llega al número máximo de errores (100).</span><span class="sxs-lookup"><span data-stu-id="2a27e-179">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="2a27e-180">La herramienta también omite los códigos de error especificados.</span><span class="sxs-lookup"><span data-stu-id="2a27e-180">The tool also ignores the specified error codes.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="2a27e-181">El comando siguiente genera el mismo resultado que el ejemplo anterior, pero especifica los códigos de error que se omiten en el archivo de respuesta `ignoreErrors.rsp`.</span><span class="sxs-lookup"><span data-stu-id="2a27e-181">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="2a27e-182">El archivo de respuesta puede contener una lista de códigos de error separados por comas.</span><span class="sxs-lookup"><span data-stu-id="2a27e-182">The response file can contain a comma-separated list of error codes.</span></span>  
  
```text
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="2a27e-183">El archivo de respuesta también puede tener un formato que incluya un código de error por línea.</span><span class="sxs-lookup"><span data-stu-id="2a27e-183">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```text
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a27e-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a27e-184">See also</span></span>

- [<span data-ttu-id="2a27e-185">Herramientas</span><span class="sxs-lookup"><span data-stu-id="2a27e-185">Tools</span></span>](index.md)
- [<span data-ttu-id="2a27e-186">Escritura de código con seguridad de tipos comprobable</span><span class="sxs-lookup"><span data-stu-id="2a27e-186">Writing Verifiably Type-Safe Code</span></span>](../misc/code-access-security-basics.md#typesafe_code)
- [<span data-ttu-id="2a27e-187">Seguridad y protección de tipos</span><span class="sxs-lookup"><span data-stu-id="2a27e-187">Type Safety and Security</span></span>](../../standard/security/key-security-concepts.md#type-safety-and-security)
- [<span data-ttu-id="2a27e-188">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="2a27e-188">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
