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
ms.openlocfilehash: 474018b8bc39e4d5c36bd4bc6481072b218d6270
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558399"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="cc855-104">Regsvcs.exe (Herramienta de instalación de servicios de .NET)</span><span class="sxs-lookup"><span data-stu-id="cc855-104">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="cc855-105">La herramienta Instalación de servicios de .NET realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cc855-105">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="cc855-106">Carga y registra un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cc855-106">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="cc855-107">Genera, registra e instala una biblioteca de tipos en una aplicación COM+ específica.</span><span class="sxs-lookup"><span data-stu-id="cc855-107">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="cc855-108">Configura los servicios que se han agregado a la clase mediante programación.</span><span class="sxs-lookup"><span data-stu-id="cc855-108">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="cc855-109">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="cc855-109">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="cc855-110">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="cc855-110">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="cc855-111">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc855-111">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc855-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc855-112">Syntax</span></span>  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a><span data-ttu-id="cc855-113">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc855-113">Parameters</span></span>  
  
|<span data-ttu-id="cc855-114">Argumento</span><span class="sxs-lookup"><span data-stu-id="cc855-114">Argument</span></span>|<span data-ttu-id="cc855-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc855-115">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="cc855-116">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="cc855-116">*assemblyFile.dll*</span></span>|<span data-ttu-id="cc855-117">Archivo de ensamblado de origen con el que se va a trabajar.</span><span class="sxs-lookup"><span data-stu-id="cc855-117">The source assembly file.</span></span> <span data-ttu-id="cc855-118">El ensamblado debe estar firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="cc855-118">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="cc855-119">Para obtener más información, vea [Procedimiento para firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="cc855-119">For more information, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span>|  
  
|<span data-ttu-id="cc855-120">Opción</span><span class="sxs-lookup"><span data-stu-id="cc855-120">Option</span></span>|<span data-ttu-id="cc855-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc855-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cc855-122">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="cc855-122">**/appdir:** *path*</span></span>|<span data-ttu-id="cc855-123">Especifica el directorio raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc855-123">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="cc855-124">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="cc855-124">**/appname:** *applicationName*</span></span>|<span data-ttu-id="cc855-125">Especifica el nombre de la aplicación COM+ que se busca o se crea.</span><span class="sxs-lookup"><span data-stu-id="cc855-125">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="cc855-126">**/c**</span><span class="sxs-lookup"><span data-stu-id="cc855-126">**/c**</span></span>|<span data-ttu-id="cc855-127">Crea la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="cc855-127">Creates the target application.</span></span>|  
|<span data-ttu-id="cc855-128">**/componly**</span><span class="sxs-lookup"><span data-stu-id="cc855-128">**/componly**</span></span>|<span data-ttu-id="cc855-129">Solo configura componentes; no tiene en cuenta métodos o interfaces.</span><span class="sxs-lookup"><span data-stu-id="cc855-129">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="cc855-130">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="cc855-130">**/exapp**</span></span>|<span data-ttu-id="cc855-131">Indica a la herramienta que debe contar con una aplicación existente.</span><span class="sxs-lookup"><span data-stu-id="cc855-131">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="cc855-132">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="cc855-132">**/extlb**</span></span>|<span data-ttu-id="cc855-133">Utiliza una biblioteca de tipos existente.</span><span class="sxs-lookup"><span data-stu-id="cc855-133">Uses an existing type library.</span></span>|  
|<span data-ttu-id="cc855-134">**/fc**</span><span class="sxs-lookup"><span data-stu-id="cc855-134">**/fc**</span></span>|<span data-ttu-id="cc855-135">Busca o crea la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="cc855-135">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="cc855-136">**/help**</span><span class="sxs-lookup"><span data-stu-id="cc855-136">**/help**</span></span>|<span data-ttu-id="cc855-137">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="cc855-137">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="cc855-138">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="cc855-138">**/noreconfig**</span></span>|<span data-ttu-id="cc855-139">No vuelve a configurar una aplicación de destino existente.</span><span class="sxs-lookup"><span data-stu-id="cc855-139">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="cc855-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="cc855-140">**/nologo**</span></span>|<span data-ttu-id="cc855-141">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc855-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="cc855-142">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="cc855-142">**/parname:** *name*</span></span>|<span data-ttu-id="cc855-143">Especifica el nombre o el identificador de la aplicación COM+ que se busca o se crea.</span><span class="sxs-lookup"><span data-stu-id="cc855-143">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="cc855-144">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="cc855-144">**/reconfig**</span></span>|<span data-ttu-id="cc855-145">Vuelve a configurar una aplicación de destino existente.</span><span class="sxs-lookup"><span data-stu-id="cc855-145">Reconfigures an existing target application.</span></span> <span data-ttu-id="cc855-146">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cc855-146">This is the default.</span></span>|  
|<span data-ttu-id="cc855-147">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="cc855-147">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="cc855-148">Especifica el archivo de biblioteca de tipos que se instala.</span><span class="sxs-lookup"><span data-stu-id="cc855-148">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="cc855-149">**/u**</span><span class="sxs-lookup"><span data-stu-id="cc855-149">**/u**</span></span>|<span data-ttu-id="cc855-150">Desinstala la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="cc855-150">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="cc855-151">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="cc855-151">**/quiet**</span></span>|<span data-ttu-id="cc855-152">Especifica el modo silencioso; suprime el logotipo y la presentación de mensajes de operaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="cc855-152">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="cc855-153">**/?**</span><span class="sxs-lookup"><span data-stu-id="cc855-153">**/?**</span></span>|<span data-ttu-id="cc855-154">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="cc855-154">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc855-155">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc855-155">Remarks</span></span>  
 <span data-ttu-id="cc855-156">Regsvcs.exe requiere un archivo de ensamblado de origen especificado por *assemblyFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="cc855-156">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="cc855-157">Este ensamblado debe estar firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="cc855-157">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="cc855-158">Para obtener más información sobre la firma con nombres seguros, vea [Procedimiento para firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="cc855-158">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../standard/assembly/sign-strong-name.md).</span></span> <span data-ttu-id="cc855-159">Los nombres de la aplicación de destino y del archivo de biblioteca de tipos son opcionales.</span><span class="sxs-lookup"><span data-stu-id="cc855-159">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="cc855-160">El argumento *applicationName* se puede generar a partir del archivo de ensamblado de origen, y Regsvcs.exe lo creará si no existe todavía.</span><span class="sxs-lookup"><span data-stu-id="cc855-160">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="cc855-161">El argumento *typelibraryfile* puede especificar un nombre de biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="cc855-161">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="cc855-162">Si no se especifica ningún nombre de biblioteca de tipos, Regsvcs.exe utiliza el nombre del ensamblado como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cc855-162">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="cc855-163">Cuando Regsvcs.exe registra los métodos de un componente, se le aplican las [peticiones](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) y las [peticiones de vínculos](../misc/link-demands.md) de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="cc855-163">When Regsvcs.exe registers a component's methods, it is subject to the [demands](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="cc855-164">Como la herramienta se ejecuta en un entorno de confianza total, la mayoría de las peticiones de permisos se llevan a cabo satisfactoriamente.</span><span class="sxs-lookup"><span data-stu-id="cc855-164">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="cc855-165">Sin embargo, Regsvcs.exe no puede registrar componentes con métodos protegidos por una petición o una petición de vínculo para <xref:System.Security.Permissions.StrongNameIdentityPermission> o <xref:System.Security.Permissions.PublisherIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="cc855-165">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="cc855-166">Debe tener privilegios administrativos en el equipo local para utilizar Regsvcs.exe.</span><span class="sxs-lookup"><span data-stu-id="cc855-166">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="cc855-167">Si Regsvcs.exe genera un error durante la realización de alguna de estas acciones, muestra los mensajes de error correspondientes.</span><span class="sxs-lookup"><span data-stu-id="cc855-167">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cc855-168">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="cc855-168">Examples</span></span>  
 <span data-ttu-id="cc855-169">El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="cc855-169">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="cc855-170">El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="cc855-170">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc855-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc855-171">See also</span></span>

- [<span data-ttu-id="cc855-172">Herramientas</span><span class="sxs-lookup"><span data-stu-id="cc855-172">Tools</span></span>](index.md)
- [<span data-ttu-id="cc855-173">Cómo: Firma de un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="cc855-173">How to: Sign an Assembly with a Strong Name</span></span>](../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="cc855-174">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="cc855-174">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
