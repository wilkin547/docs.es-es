---
title: 'Cómo: Crear una directiva de publicador'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e7cac3c7e6c588a82e9dfff169ba7b7aa72c35f8
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028019"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="fddf8-102">Cómo: Crear una directiva de publicador</span><span class="sxs-lookup"><span data-stu-id="fddf8-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="fddf8-103">Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de publicador con el ensamblado actualizado.</span><span class="sxs-lookup"><span data-stu-id="fddf8-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="fddf8-104">El archivo de directiva de publicador especifica redirección de ensamblado y la configuración de base de código y usa el mismo formato que un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fddf8-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="fddf8-105">El archivo de directiva de publicador se compila en un ensamblado y colocar en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fddf8-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="fddf8-106">Hay tres pasos implicados en la creación de una directiva de publicador:</span><span class="sxs-lookup"><span data-stu-id="fddf8-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1.  <span data-ttu-id="fddf8-107">Cree un archivo de directiva de publicador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-107">Create a publisher policy file.</span></span>  
  
2.  <span data-ttu-id="fddf8-108">Crear un ensamblado de directivas de publicador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-108">Create a publisher policy assembly.</span></span>  
  
3.  <span data-ttu-id="fddf8-109">Agregue el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fddf8-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="fddf8-110">Se describe el esquema de directiva de publicador en [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="fddf8-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="fddf8-111">El ejemplo siguiente muestra un editor de archivo de directiva que redirige una versión de `myAssembly` a otro.</span><span class="sxs-lookup"><span data-stu-id="fddf8-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="fddf8-112">Para obtener información sobre cómo especificar un código base, vea [especificar la ubicación del ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="fddf8-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="fddf8-113">Crear el ensamblado de directivas de publicador</span><span class="sxs-lookup"><span data-stu-id="fddf8-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="fddf8-114">Use la [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) para crear el ensamblado de directivas de publicador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="fddf8-115">Para crear un ensamblado de directivas de publicador</span><span class="sxs-lookup"><span data-stu-id="fddf8-115">To create a publisher policy assembly</span></span>  
  
1.  <span data-ttu-id="fddf8-116">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fddf8-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="fddf8-117">**al/Link:** *directivas* **/out:** *publisherPolicyAssemblyFile* **/keyfile:**  *keyPairFile* **/Platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="fddf8-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="fddf8-118">En este comando:</span><span class="sxs-lookup"><span data-stu-id="fddf8-118">In this command:</span></span>  
  
    -   <span data-ttu-id="fddf8-119">El *directivas* argumento es el nombre del archivo de directiva de publicador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="fddf8-120">El *publisherPolicyAssemblyFile* argumento es el nombre del ensamblado de directiva de publicador que da como resultado de este comando.</span><span class="sxs-lookup"><span data-stu-id="fddf8-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="fddf8-121">El nombre de archivo de ensamblado debe tener el formato:</span><span class="sxs-lookup"><span data-stu-id="fddf8-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="fddf8-122">**Directiva.**</span><span class="sxs-lookup"><span data-stu-id="fddf8-122">**policy.**</span></span> <span data-ttu-id="fddf8-123">*número principal* **.**</span><span class="sxs-lookup"><span data-stu-id="fddf8-123">*majorNumber* **.**</span></span> <span data-ttu-id="fddf8-124">*número secundario* **.**</span><span class="sxs-lookup"><span data-stu-id="fddf8-124">*minorNumber* **.**</span></span> <span data-ttu-id="fddf8-125">*nombre de ensamblado principal* **.dll**</span><span class="sxs-lookup"><span data-stu-id="fddf8-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="fddf8-126">El *keyPairFile* argumento es el nombre del archivo que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="fddf8-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="fddf8-127">Debe firmar el ensamblado y el ensamblado de directivas del publicador con el mismo par de claves.</span><span class="sxs-lookup"><span data-stu-id="fddf8-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="fddf8-128">El *processorArchitecture* argumento identifica la plataforma de destino de un ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fddf8-129">La capacidad para tener como destino una arquitectura de procesador específico es nueva en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fddf8-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="fddf8-130">El siguiente comando crea un ensamblado de directivas de publicador denominado `policy.1.0.myAssembly` desde un archivo de directiva de publicador llama `pub.config`, asigna un nombre seguro al ensamblado mediante el par de claves en el `sgKey.snk` de archivos y especifica que el ensamblado tiene como destino el x86 arquitectura de procesador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="fddf8-131">El ensamblado de directivas de publicador debe coincidir con la arquitectura del procesador del ensamblado que se aplica.</span><span class="sxs-lookup"><span data-stu-id="fddf8-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="fddf8-132">Por lo tanto, si el ensamblado tiene un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valor <xref:System.Reflection.ProcessorArchitecture.MSIL>, el ensamblado de directivas de publicador para dicho ensamblado debe crearse con `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="fddf8-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="fddf8-133">Debe proporcionar otro ensamblado de directivas de publicador para cada ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="fddf8-134">Una consecuencia de esta regla es que con el fin de cambiar la arquitectura de procesador para un ensamblado, debe cambiar el componente principal o secundario del número de versión, por lo que puede proporcionar un nuevo ensamblado de directivas de publicador con la arquitectura correcta del procesador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="fddf8-135">El ensamblado de directiva de publicador anterior no puede reparar el ensamblado cuando el ensamblado tiene una arquitectura de procesador distinta.</span><span class="sxs-lookup"><span data-stu-id="fddf8-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="fddf8-136">Otra consecuencia es que la versión 2.0 del vinculador no puede utilizarse para crear un ensamblado de directivas de publicador para un ensamblado compilado con versiones anteriores de .NET Framework, porque siempre especifica la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="fddf8-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="fddf8-137">Agregar el ensamblado de directivas de publicador a la caché Global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="fddf8-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="fddf8-138">Use la [herramienta caché Global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directivas de publicador a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fddf8-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="fddf8-139">Para agregar el ensamblado de directivas de publicador a la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="fddf8-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1.  <span data-ttu-id="fddf8-140">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fddf8-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="fddf8-141">\**gacutil /i\*\*\*publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="fddf8-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="fddf8-142">El comando siguiente agrega `policy.1.0.myAssembly.dll` a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fddf8-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fddf8-143">No se puede agregar el ensamblado de directivas de publicador a la caché global de ensamblados, a menos que se encuentra el archivo de directiva de publicador original en el mismo directorio que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fddf8-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fddf8-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="fddf8-144">See Also</span></span>  
 [<span data-ttu-id="fddf8-145">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="fddf8-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="fddf8-146">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="fddf8-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="fddf8-147">Configurar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fddf8-147">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="fddf8-148">Configurar aplicaciones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fddf8-148">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [<span data-ttu-id="fddf8-149">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="fddf8-149">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="fddf8-150">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fddf8-150">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="fddf8-151">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="fddf8-151">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
