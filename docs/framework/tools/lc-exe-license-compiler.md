---
title: Lc.exe (Compilador de licencias)
description: Use Lc.exe, el compilador de licencias. Esta herramienta lee los archivos de texto que tienen información de licencia y crea un archivo binario para insertarlo en un ejecutable de CLR como un recurso.
ms.date: 03/30/2017
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
ms.openlocfilehash: 1a9806cd71f9990d9ce70b35b3af760a22347003
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258808"
---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="54d6b-104">Lc.exe (Compilador de licencias)</span><span class="sxs-lookup"><span data-stu-id="54d6b-104">Lc.exe (License Compiler)</span></span>

<span data-ttu-id="54d6b-105">El Compilador de licencias lee archivos de texto que contienen información sobre licencias y crea un archivo binario que se puede incrustar como recurso en un archivo ejecutable de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="54d6b-105">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="54d6b-106">El Diseñador de Windows Forms genera o actualiza automáticamente un archivo de texto .licx siempre que se agrega al formulario un control con licencia.</span><span class="sxs-lookup"><span data-stu-id="54d6b-106">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="54d6b-107">Como parte de la compilación, el sistema del proyecto transforma el archivo de texto .licx en un recurso binario .licenses que proporciona compatibilidad para la licencia de controles .NET.</span><span class="sxs-lookup"><span data-stu-id="54d6b-107">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="54d6b-108">A continuación, el recurso binario se incrustará en los resultados del proyecto.</span><span class="sxs-lookup"><span data-stu-id="54d6b-108">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="54d6b-109">No se admite la compilación cruzada entre 32 y 64 bits cuando se usa la herramienta Compilador de licencias al generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="54d6b-109">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="54d6b-110">Esto se debe a que el Compilador de licencias tiene que cargar los ensamblados, y no se permite cargar ensamblados de 64 bits de una aplicación de 32 bits y viceversa.</span><span class="sxs-lookup"><span data-stu-id="54d6b-110">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="54d6b-111">En este caso, utilice el Compilador de licencias desde la línea de comandos para compilar la licencia manualmente y especifique la arquitectura correspondiente.</span><span class="sxs-lookup"><span data-stu-id="54d6b-111">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="54d6b-112">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="54d6b-112">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="54d6b-113">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="54d6b-113">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="54d6b-114">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="54d6b-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d6b-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54d6b-115">Syntax</span></span>  
  
```console
      lc /target:  
targetPE /complist:filename [-outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="54d6b-116">Opción</span><span class="sxs-lookup"><span data-stu-id="54d6b-116">Option</span></span>|<span data-ttu-id="54d6b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="54d6b-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="54d6b-118">**/complist:** *filename*</span><span class="sxs-lookup"><span data-stu-id="54d6b-118">**/complist:** *filename*</span></span>|<span data-ttu-id="54d6b-119">Especifica el nombre de un archivo que contiene la lista de componentes con licencia que se van a incluir en el archivo .licenses.</span><span class="sxs-lookup"><span data-stu-id="54d6b-119">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="54d6b-120">Se hace referencia a cada componente utilizando su nombre completo con un solo componente por línea.</span><span class="sxs-lookup"><span data-stu-id="54d6b-120">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="54d6b-121">Los usuarios de la línea de comandos pueden especificar un archivo independiente para cada formulario del proyecto.</span><span class="sxs-lookup"><span data-stu-id="54d6b-121">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="54d6b-122">Lc.exe acepta varios archivos de entrada y crea un único archivo .licenses.</span><span class="sxs-lookup"><span data-stu-id="54d6b-122">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="54d6b-123">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="54d6b-123">**/h**[**elp**]</span></span>|<span data-ttu-id="54d6b-124">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="54d6b-124">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="54d6b-125">**/i:** *module*</span><span class="sxs-lookup"><span data-stu-id="54d6b-125">**/i:** *module*</span></span>|<span data-ttu-id="54d6b-126">Especifica los módulos que contienen los componentes enumerados en el archivo **/complist**.</span><span class="sxs-lookup"><span data-stu-id="54d6b-126">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="54d6b-127">Para especificar más de un módulo, use varias marcas **/i**.</span><span class="sxs-lookup"><span data-stu-id="54d6b-127">To specify more than one module, use multiple **/i** flags.</span></span>|  
|<span data-ttu-id="54d6b-128">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="54d6b-128">**/nologo**</span></span>|<span data-ttu-id="54d6b-129">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54d6b-129">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="54d6b-130">**/outdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="54d6b-130">**/outdir:** *path*</span></span>|<span data-ttu-id="54d6b-131">Especifica el directorio en el que se coloca el archivo .licenses de resultados.</span><span class="sxs-lookup"><span data-stu-id="54d6b-131">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="54d6b-132">**/target:** *targetPE*</span><span class="sxs-lookup"><span data-stu-id="54d6b-132">**/target:** *targetPE*</span></span>|<span data-ttu-id="54d6b-133">Especifica el archivo ejecutable para el que se genera el archivo .licenses.</span><span class="sxs-lookup"><span data-stu-id="54d6b-133">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|<span data-ttu-id="54d6b-134">**/v**</span><span class="sxs-lookup"><span data-stu-id="54d6b-134">**/v**</span></span>|<span data-ttu-id="54d6b-135">Especifica el modo detallado; muestra información del progreso de la compilación.</span><span class="sxs-lookup"><span data-stu-id="54d6b-135">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="54d6b-136">**@** *file*</span><span class="sxs-lookup"><span data-stu-id="54d6b-136">**@** *file*</span></span>|<span data-ttu-id="54d6b-137">Especifica el archivo de respuesta (.rsp).</span><span class="sxs-lookup"><span data-stu-id="54d6b-137">Specifies the response (.rsp) file.</span></span>|  
|<span data-ttu-id="54d6b-138">**/?**</span><span class="sxs-lookup"><span data-stu-id="54d6b-138">**/?**</span></span>|<span data-ttu-id="54d6b-139">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="54d6b-139">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="54d6b-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54d6b-140">Example</span></span>  
  
1. <span data-ttu-id="54d6b-141">Si usa un control con licencia `MyCompany.Samples.LicControl1` dentro de `Samples.DLL` en una aplicación denominada `HostApp.exe` *,*  puede crear un archivo `HostAppLic.txt` que contenga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="54d6b-141">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```text
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. <span data-ttu-id="54d6b-142">Se puede crear el archivo .licenses denominado `HostApp.exe.licenses` utilizando el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="54d6b-142">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```console  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. <span data-ttu-id="54d6b-143">Se puede compilar el archivo `HostApp.exe` que incluya el archivo .licenses como un recurso.</span><span class="sxs-lookup"><span data-stu-id="54d6b-143">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="54d6b-144">Si está compilando una aplicación en C#, debe utilizar el comando siguiente para compilarla.</span><span class="sxs-lookup"><span data-stu-id="54d6b-144">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```console
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="54d6b-145">El comando siguiente compila `myApp.licenses` a partir de las listas de componentes con licencia especificadas por `hostapplic.txt`, `hostapplic2.txt` y `hostapplic3.txt`.</span><span class="sxs-lookup"><span data-stu-id="54d6b-145">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="54d6b-146">El argumento `modulesList` especifica los módulos que contienen los componentes con licencia.</span><span class="sxs-lookup"><span data-stu-id="54d6b-146">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```console  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="54d6b-147">Ejemplo de archivo de respuesta</span><span class="sxs-lookup"><span data-stu-id="54d6b-147">Response File Example</span></span>  

 <span data-ttu-id="54d6b-148">La siguiente lista muestra un ejemplo de un archivo de respuesta, `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="54d6b-148">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="54d6b-149">Para más información sobre los archivos de respuesta, consulte [Archivos de respuesta](/visualstudio/msbuild/msbuild-response-files).</span><span class="sxs-lookup"><span data-stu-id="54d6b-149">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```text  
/target:hostapp.exe  
/complist:hostapplic.txt
/i:WFCPrj.dll
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="54d6b-150">La siguiente línea de comandos usa el archivo `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="54d6b-150">The following command line uses the `response.rsp` file.</span></span>  
  
```console  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="54d6b-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="54d6b-151">See also</span></span>

- [<span data-ttu-id="54d6b-152">Herramientas</span><span class="sxs-lookup"><span data-stu-id="54d6b-152">Tools</span></span>](index.md)
- [<span data-ttu-id="54d6b-153">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="54d6b-153">Al.exe (Assembly Linker)</span></span>](al-exe-assembly-linker.md)
- [<span data-ttu-id="54d6b-154">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="54d6b-154">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
