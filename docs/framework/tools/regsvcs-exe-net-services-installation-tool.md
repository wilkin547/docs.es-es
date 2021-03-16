---
title: Regsvcs.exe (Herramienta de instalación de servicios de .NET)
description: Use Regsvcs.exe, la Herramienta de instalación de servicios de .NET. Cargue y registre un ensamblado, configure los servicios agregados mediante programación a una clase, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
ms.openlocfilehash: a989ddf8b14806879917e4078f60486f225b00e3
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259208"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="4ae0b-104">Regsvcs.exe (Herramienta de instalación de servicios de .NET)</span><span class="sxs-lookup"><span data-stu-id="4ae0b-104">Regsvcs.exe (.NET Services Installation Tool)</span></span>

<span data-ttu-id="4ae0b-105">La herramienta Instalación de servicios de .NET realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4ae0b-105">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="4ae0b-106">Carga y registra un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-106">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="4ae0b-107">Genera, registra e instala una biblioteca de tipos en una aplicación COM+ específica.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-107">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="4ae0b-108">Configura los servicios que se han agregado a la clase mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-108">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="4ae0b-109">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="4ae0b-109">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="4ae0b-110">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ae0b-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae0b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ae0b-111">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a><span data-ttu-id="4ae0b-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ae0b-112">Parameters</span></span>  
  
|<span data-ttu-id="4ae0b-113">Argumento</span><span class="sxs-lookup"><span data-stu-id="4ae0b-113">Argument</span></span>|<span data-ttu-id="4ae0b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ae0b-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4ae0b-115">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="4ae0b-115">*assemblyFile.dll*</span></span>|<span data-ttu-id="4ae0b-116">Archivo de ensamblado de origen con el que se va a trabajar.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-116">The source assembly file.</span></span> <span data-ttu-id="4ae0b-117">El ensamblado debe estar firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-117">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="4ae0b-118">Para obtener más información, vea [Procedimiento para firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="4ae0b-118">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="4ae0b-119">Opción</span><span class="sxs-lookup"><span data-stu-id="4ae0b-119">Option</span></span>|<span data-ttu-id="4ae0b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ae0b-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4ae0b-121">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="4ae0b-121">**/appdir:** *path*</span></span>|<span data-ttu-id="4ae0b-122">Especifica el directorio raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-122">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="4ae0b-123">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="4ae0b-123">**/appname:** *applicationName*</span></span>|<span data-ttu-id="4ae0b-124">Especifica el nombre de la aplicación COM+ que se busca o se crea.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-124">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="4ae0b-125">**/c**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-125">**/c**</span></span>|<span data-ttu-id="4ae0b-126">Crea la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-126">Creates the target application.</span></span>|  
|<span data-ttu-id="4ae0b-127">**/componly**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-127">**/componly**</span></span>|<span data-ttu-id="4ae0b-128">Solo configura componentes; no tiene en cuenta métodos o interfaces.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-128">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="4ae0b-129">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-129">**/exapp**</span></span>|<span data-ttu-id="4ae0b-130">Indica a la herramienta que debe contar con una aplicación existente.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-130">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="4ae0b-131">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-131">**/extlb**</span></span>|<span data-ttu-id="4ae0b-132">Utiliza una biblioteca de tipos existente.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-132">Uses an existing type library.</span></span>|  
|<span data-ttu-id="4ae0b-133">**/fc**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-133">**/fc**</span></span>|<span data-ttu-id="4ae0b-134">Busca o crea la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-134">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="4ae0b-135">**/help**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-135">**/help**</span></span>|<span data-ttu-id="4ae0b-136">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-136">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="4ae0b-137">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-137">**/noreconfig**</span></span>|<span data-ttu-id="4ae0b-138">No vuelve a configurar una aplicación de destino existente.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-138">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="4ae0b-139">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-139">**/nologo**</span></span>|<span data-ttu-id="4ae0b-140">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-140">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="4ae0b-141">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="4ae0b-141">**/parname:** *name*</span></span>|<span data-ttu-id="4ae0b-142">Especifica el nombre o el identificador de la aplicación COM+ que se busca o se crea.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-142">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="4ae0b-143">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-143">**/reconfig**</span></span>|<span data-ttu-id="4ae0b-144">Vuelve a configurar una aplicación de destino existente.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-144">Reconfigures an existing target application.</span></span> <span data-ttu-id="4ae0b-145">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-145">This is the default.</span></span>|  
|<span data-ttu-id="4ae0b-146">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="4ae0b-146">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="4ae0b-147">Especifica el archivo de biblioteca de tipos que se instala.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-147">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="4ae0b-148">**/u**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-148">**/u**</span></span>|<span data-ttu-id="4ae0b-149">Desinstala la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-149">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="4ae0b-150">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-150">**/quiet**</span></span>|<span data-ttu-id="4ae0b-151">Especifica el modo silencioso; suprime el logotipo y la presentación de mensajes de operaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-151">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="4ae0b-152">**/?**</span><span class="sxs-lookup"><span data-stu-id="4ae0b-152">**/?**</span></span>|<span data-ttu-id="4ae0b-153">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-153">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ae0b-154">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ae0b-154">Remarks</span></span>  

 <span data-ttu-id="4ae0b-155">Regsvcs.exe requiere un archivo de ensamblado de origen especificado por *assemblyFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-155">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="4ae0b-156">Este ensamblado debe estar firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-156">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="4ae0b-157">Para obtener más información sobre la firma con nombres seguros, vea [Procedimiento para firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="4ae0b-157">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="4ae0b-158">Los nombres de la aplicación de destino y del archivo de biblioteca de tipos son opcionales.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-158">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="4ae0b-159">El argumento *applicationName* se puede generar a partir del archivo de ensamblado de origen, y Regsvcs.exe lo creará si no existe todavía.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-159">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="4ae0b-160">El argumento *typelibraryfile* puede especificar un nombre de biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-160">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="4ae0b-161">Si no se especifica ningún nombre de biblioteca de tipos, Regsvcs.exe utiliza el nombre del ensamblado como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-161">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="4ae0b-162">Cuando Regsvcs.exe registra los métodos de un componente, se le aplican las [peticiones](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) y las [peticiones de vínculos](../misc/link-demands.md) de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-162">When Regsvcs.exe registers a component's methods, it is subject to the [demands](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="4ae0b-163">Como la herramienta se ejecuta en un entorno de confianza total, la mayoría de las peticiones de permisos se llevan a cabo satisfactoriamente.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-163">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="4ae0b-164">Sin embargo, Regsvcs.exe no puede registrar componentes con métodos protegidos por una petición o una petición de vínculo para <xref:System.Security.Permissions.StrongNameIdentityPermission> o <xref:System.Security.Permissions.PublisherIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-164">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="4ae0b-165">Debe tener privilegios administrativos en el equipo local para utilizar Regsvcs.exe.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-165">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="4ae0b-166">Si Regsvcs.exe genera un error durante la realización de alguna de estas acciones, muestra los mensajes de error correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-166">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4ae0b-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4ae0b-167">Examples</span></span>  

 <span data-ttu-id="4ae0b-168">El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="4ae0b-169">El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="4ae0b-169">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ae0b-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ae0b-170">See also</span></span>

- [<span data-ttu-id="4ae0b-171">Herramientas</span><span class="sxs-lookup"><span data-stu-id="4ae0b-171">Tools</span></span>](index.md)
- [<span data-ttu-id="4ae0b-172">Cómo: Firma de un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="4ae0b-172">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="4ae0b-173">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="4ae0b-173">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
