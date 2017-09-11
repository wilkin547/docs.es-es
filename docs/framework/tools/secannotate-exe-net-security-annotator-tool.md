---
title: SecAnnotate.exe (Herramienta Anotador de seguridad de .NET)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SecAnnotate.exe
- Security Annotator tool
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cdfe635b913f379a031994ad359a7d6ab657c255
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="secannotateexe-net-security-annotator-tool"></a><span data-ttu-id="f719f-102">SecAnnotate.exe (Herramienta Anotador de seguridad de .NET)</span><span class="sxs-lookup"><span data-stu-id="f719f-102">SecAnnotate.exe (.NET Security Annotator Tool)</span></span>
<span data-ttu-id="f719f-103">La herramienta Anotador de seguridad de .NET (SecAnnotate.exe) es una aplicación de línea de comandos que identifica los elementos `SecurityCritical` y `SecuritySafeCritical` de uno o más ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f719f-103">The .NET Security Annotator tool (SecAnnotate.exe) is a command-line application that identifies the `SecurityCritical` and `SecuritySafeCritical` portions of one or more assemblies.</span></span>  
  
 <span data-ttu-id="f719f-104">El [Anotador de seguridad](http://go.microsoft.com/fwlink/?LinkId=198007), que es una extensión de Visual Studio, proporciona una interfaz gráfica de usuario a SecAnnotate.exe y permite ejecutar la herramienta desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f719f-104">A Visual Studio extension, [Security Annotator](http://go.microsoft.com/fwlink/?LinkId=198007), provides a graphical user interface to SecAnnotate.exe and enables you to run the tool from Visual Studio.</span></span>  
  
 <span data-ttu-id="f719f-105">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f719f-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f719f-106">Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores (o el Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="f719f-106">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="f719f-107">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f719f-107">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="f719f-108">En el símbolo del sistema, escriba lo siguiente (los valores de *parameters* se describen en la sección siguiente y *assemblies* se compone de uno o varios nombres de ensamblado separados por espacios en blanco):</span><span class="sxs-lookup"><span data-stu-id="f719f-108">At the command prompt, type the following, where *parameters* are described in the following section, and *assemblies* consist of one or more assembly names separated by blanks:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f719f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f719f-109">Syntax</span></span>  
  
```  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f719f-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f719f-110">Parameters</span></span>  
  
|<span data-ttu-id="f719f-111">Opción</span><span class="sxs-lookup"><span data-stu-id="f719f-111">Option</span></span>|<span data-ttu-id="f719f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f719f-112">Description</span></span>|  
|------------|-----------------|  
|`/a`<br /><br /> <span data-ttu-id="f719f-113">o</span><span class="sxs-lookup"><span data-stu-id="f719f-113">or</span></span><br /><br /> `/showstatistics`|<span data-ttu-id="f719f-114">Muestra estadísticas sobre el uso de transparencia en los ensamblados que se van a analizar.</span><span class="sxs-lookup"><span data-stu-id="f719f-114">Shows statistics about the use of transparency in assemblies that are being analyzed.</span></span>|  
|<span data-ttu-id="f719f-115">`/d:` *directory*</span><span class="sxs-lookup"><span data-stu-id="f719f-115">`/d:` *directory*</span></span><br /><br /> <span data-ttu-id="f719f-116">o</span><span class="sxs-lookup"><span data-stu-id="f719f-116">or</span></span><br /><br /> <span data-ttu-id="f719f-117">`/referencedir:` *directory*</span><span class="sxs-lookup"><span data-stu-id="f719f-117">`/referencedir:` *directory*</span></span>|<span data-ttu-id="f719f-118">Especifica el directorio en el que buscar los ensamblados dependientes durante la anotación.</span><span class="sxs-lookup"><span data-stu-id="f719f-118">Specifies a directory to search for dependent assemblies during annotation.</span></span>|  
|`/i`<br /><br /> <span data-ttu-id="f719f-119">o</span><span class="sxs-lookup"><span data-stu-id="f719f-119">or</span></span><br /><br /> `/includesignatures`|<span data-ttu-id="f719f-120">Incluye información de signatura ampliada en el archivo de informe de anotación.</span><span class="sxs-lookup"><span data-stu-id="f719f-120">Includes extended signature information in the annotation report file.</span></span>|  
|`/n`<br /><br /> <span data-ttu-id="f719f-121">o</span><span class="sxs-lookup"><span data-stu-id="f719f-121">or</span></span><br /><br /> `/nogac`|<span data-ttu-id="f719f-122">Suprime la búsqueda de los ensamblados a los que se hace referencia en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f719f-122">Suppresses searching for referenced assemblies in the global assembly cache.</span></span>|  
|<span data-ttu-id="f719f-123">`/o:` *output.xml*</span><span class="sxs-lookup"><span data-stu-id="f719f-123">`/o:` *output.xml*</span></span><br /><br /> <span data-ttu-id="f719f-124">o</span><span class="sxs-lookup"><span data-stu-id="f719f-124">or</span></span><br /><br /> <span data-ttu-id="f719f-125">`/out:` *output.xml*</span><span class="sxs-lookup"><span data-stu-id="f719f-125">`/out:` *output.xml*</span></span>|<span data-ttu-id="f719f-126">Especifica el archivo de anotación de salida.</span><span class="sxs-lookup"><span data-stu-id="f719f-126">Specifies the output annotation file.</span></span>|  
|<span data-ttu-id="f719f-127">`/p:` *maxpasses*</span><span class="sxs-lookup"><span data-stu-id="f719f-127">`/p:` *maxpasses*</span></span><br /><br /> <span data-ttu-id="f719f-128">o</span><span class="sxs-lookup"><span data-stu-id="f719f-128">or</span></span><br /><br /> <span data-ttu-id="f719f-129">`/maximumpasses:` *maxpasses*</span><span class="sxs-lookup"><span data-stu-id="f719f-129">`/maximumpasses:` *maxpasses*</span></span>|<span data-ttu-id="f719f-130">Especifica el número máximo de pasos de anotación que se realizan en los ensamblados antes de detener la generación de nuevas anotaciones.</span><span class="sxs-lookup"><span data-stu-id="f719f-130">Specifies the maximum number of annotation passes to make on assemblies before stopping the generation of new annotations.</span></span>|  
|`/q`<br /><br /> <span data-ttu-id="f719f-131">o</span><span class="sxs-lookup"><span data-stu-id="f719f-131">or</span></span><br /><br /> `/quiet`|<span data-ttu-id="f719f-132">Especifica el modo silencioso, en el que el anotador no genera mensajes de salida de estado; solo genera información de error.</span><span class="sxs-lookup"><span data-stu-id="f719f-132">Specifies quiet mode, in which the annotator does not output status messages; it outputs only error information.</span></span>|  
|<span data-ttu-id="f719f-133">`/r:` *assembly*</span><span class="sxs-lookup"><span data-stu-id="f719f-133">`/r:` *assembly*</span></span><br /><br /> <span data-ttu-id="f719f-134">o</span><span class="sxs-lookup"><span data-stu-id="f719f-134">or</span></span><br /><br /> <span data-ttu-id="f719f-135">`/referenceassembly:` *assembly*</span><span class="sxs-lookup"><span data-stu-id="f719f-135">`/referenceassembly:` *assembly*</span></span>|<span data-ttu-id="f719f-136">Incluye el ensamblado especificado al resolver ensamblados dependientes durante la anotación.</span><span class="sxs-lookup"><span data-stu-id="f719f-136">Includes the specified assembly when resolving dependent assemblies during annotation.</span></span> <span data-ttu-id="f719f-137">Los ensamblados de referencia tienen prioridad sobre los ensamblados que se encuentran en la ruta de acceso de referencia.</span><span class="sxs-lookup"><span data-stu-id="f719f-137">Reference assemblies are given priority over assemblies that are found in the reference path.</span></span>|  
|<span data-ttu-id="f719f-138">`/s:` *rulename*</span><span class="sxs-lookup"><span data-stu-id="f719f-138">`/s:` *rulename*</span></span><br /><br /> <span data-ttu-id="f719f-139">o</span><span class="sxs-lookup"><span data-stu-id="f719f-139">or</span></span><br /><br /> <span data-ttu-id="f719f-140">`/suppressrule:` *rulename*</span><span class="sxs-lookup"><span data-stu-id="f719f-140">`/suppressrule:` *rulename*</span></span>|<span data-ttu-id="f719f-141">Suprime la ejecución de la regla de transparencia especificada en los ensamblados de entrada.</span><span class="sxs-lookup"><span data-stu-id="f719f-141">Suppresses running the specified transparency rule on the input assemblies.</span></span>|  
|`/t`<br /><br /> <span data-ttu-id="f719f-142">o</span><span class="sxs-lookup"><span data-stu-id="f719f-142">or</span></span><br /><br /> `/forcetransparent`|<span data-ttu-id="f719f-143">Fuerza a la herramienta Anotador a tratar todos los ensamblados que no tienen ninguna anotación de transparencia como si fueran completamente transparentes.</span><span class="sxs-lookup"><span data-stu-id="f719f-143">Forces the Annotator tool to treat all assemblies that do not have any transparency annotations as if they were entirely transparent.</span></span>|  
|<span data-ttu-id="f719f-144">`/t`:*assembly*</span><span class="sxs-lookup"><span data-stu-id="f719f-144">`/t`:*assembly*</span></span><br /><br /> <span data-ttu-id="f719f-145">o</span><span class="sxs-lookup"><span data-stu-id="f719f-145">or</span></span><br /><br /> <span data-ttu-id="f719f-146">`/forcetransparent`:*assembly*</span><span class="sxs-lookup"><span data-stu-id="f719f-146">`/forcetransparent`:*assembly*</span></span>|<span data-ttu-id="f719f-147">Fuerza al ensamblado proporcionado a que sea transparente, independientemente de las anotaciones de nivel de ensamblado actuales.</span><span class="sxs-lookup"><span data-stu-id="f719f-147">Force the given assembly to be transparent, regardless of its current assembly-level annotations.</span></span>|  
|||  
|`/v`<br /><br /> <span data-ttu-id="f719f-148">o</span><span class="sxs-lookup"><span data-stu-id="f719f-148">or</span></span><br /><br /> `/verify`|<span data-ttu-id="f719f-149">Comprueba únicamente que las anotaciones de un ensamblado sean correctas, pero no intenta ejecutar varios pasos para buscar todas las anotaciones necesarias si el ensamblado no supera la comprobación.</span><span class="sxs-lookup"><span data-stu-id="f719f-149">Verifies only that an assembly's annotations are correct; does not attempt to make multiple passes to find all required annotations if the assembly does not verify.</span></span>|  
|`/x`<br /><br /> <span data-ttu-id="f719f-150">o</span><span class="sxs-lookup"><span data-stu-id="f719f-150">or</span></span><br /><br /> `/verbose`|<span data-ttu-id="f719f-151">Especifica resultados detallados al anotar.</span><span class="sxs-lookup"><span data-stu-id="f719f-151">Specifies verbose output while annotating.</span></span>|  
|<span data-ttu-id="f719f-152">`/y:` *directory*</span><span class="sxs-lookup"><span data-stu-id="f719f-152">`/y:` *directory*</span></span><br /><br /> <span data-ttu-id="f719f-153">o</span><span class="sxs-lookup"><span data-stu-id="f719f-153">or</span></span><br /><br /> <span data-ttu-id="f719f-154">`/symbolpath:` *directory*</span><span class="sxs-lookup"><span data-stu-id="f719f-154">`/symbolpath:` *directory*</span></span>|<span data-ttu-id="f719f-155">Incluye el directorio especificado al buscar archivos de símbolos durante la anotación.</span><span class="sxs-lookup"><span data-stu-id="f719f-155">Includes the specified directory when searching for symbol files during annotation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f719f-156">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f719f-156">Remarks</span></span>  
 <span data-ttu-id="f719f-157">Los parámetros y ensamblados también se pueden proporcionar en un archivo de respuesta que se especifica en la línea de comandos y lleva el prefijo de una arroba (@).</span><span class="sxs-lookup"><span data-stu-id="f719f-157">Parameters and assemblies may also be provided in a response file that is specified on the command line and prefixed with an at sign (@).</span></span> <span data-ttu-id="f719f-158">Cada línea del archivo de respuesta debe contener un nombre de ensamblado o parámetro único.</span><span class="sxs-lookup"><span data-stu-id="f719f-158">Each line in the response file should contain a single parameter or assembly name.</span></span>  
  
 <span data-ttu-id="f719f-159">Para obtener más información sobre el Anotador de seguridad de .NET, vea la entrada sobre [cómo usar SecAnnotate para analizar los ensamblados y detectar infracciones de transparencia](http://go.microsoft.com/fwlink/?LinkId=187648) en el blog de seguridad de .NET.</span><span class="sxs-lookup"><span data-stu-id="f719f-159">For more information about the .NET Security Annotator, see the entry [Using SecAnnotate to Analyze Your Assemblies for Transparency Violations](http://go.microsoft.com/fwlink/?LinkId=187648) in the .NET Security blog.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f719f-160">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f719f-160">Examples</span></span>

