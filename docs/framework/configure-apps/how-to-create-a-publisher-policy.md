---
title: Procedimiento para crear una directiva de publicador
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646055"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="066f6-102">Procedimiento para crear una directiva de publicador</span><span class="sxs-lookup"><span data-stu-id="066f6-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="066f6-103">Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de publicador con el ensamblado actualizado.</span><span class="sxs-lookup"><span data-stu-id="066f6-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="066f6-104">El archivo de directiva de publicador especifica la redirección de ensamblados y la configuración de base de código, y utiliza el mismo formato que un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="066f6-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="066f6-105">El archivo de directiva de publicador se compila en un ensamblado y se coloca en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="066f6-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="066f6-106">Hay tres pasos implicados en la creación de una directiva de publicador:</span><span class="sxs-lookup"><span data-stu-id="066f6-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="066f6-107">Cree un archivo de directiva de publicador.</span><span class="sxs-lookup"><span data-stu-id="066f6-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="066f6-108">Cree un ensamblado de directiva de publicador.</span><span class="sxs-lookup"><span data-stu-id="066f6-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="066f6-109">Agregue el ensamblado de directiva de publicador a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="066f6-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="066f6-110">El esquema para la directiva de publicador se describe en Redirección de [versiones](redirect-assembly-versions.md)de ensamblado .</span><span class="sxs-lookup"><span data-stu-id="066f6-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="066f6-111">En el ejemplo siguiente se muestra un `myAssembly` archivo de directiva de publicador que redirige una versión a otra.</span><span class="sxs-lookup"><span data-stu-id="066f6-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="066f6-112">Para obtener información sobre cómo especificar una base de código, consulte [Especificación](specify-assembly-location.md)de la ubicación de un ensamblado .</span><span class="sxs-lookup"><span data-stu-id="066f6-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="066f6-113">Creación del ensamblado de directivas de publicador</span><span class="sxs-lookup"><span data-stu-id="066f6-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="066f6-114">Use el vinculador de [ensamblados (Al.exe)](../tools/al-exe-assembly-linker.md) para crear el ensamblado de directiva de publicador.</span><span class="sxs-lookup"><span data-stu-id="066f6-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="066f6-115">Para crear un ensamblado de directiva de publicador</span><span class="sxs-lookup"><span data-stu-id="066f6-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="066f6-116">Escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="066f6-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="066f6-117">En este comando:</span><span class="sxs-lookup"><span data-stu-id="066f6-117">In this command:</span></span>

- <span data-ttu-id="066f6-118">El `publisherPolicyFile` argumento es el nombre del archivo de directiva del publicador.</span><span class="sxs-lookup"><span data-stu-id="066f6-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="066f6-119">El `publisherPolicyAssemblyFile` argumento es el nombre del ensamblado de directiva de publicador que resulta de este comando.</span><span class="sxs-lookup"><span data-stu-id="066f6-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="066f6-120">El nombre del archivo de ensamblado debe seguir el formato:</span><span class="sxs-lookup"><span data-stu-id="066f6-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="066f6-121">'policy.majorNumber.minorNumber.mainAssemblyName.dll'</span><span class="sxs-lookup"><span data-stu-id="066f6-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="066f6-122">El `keyPairFile` argumento es el nombre del archivo que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="066f6-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="066f6-123">Debe firmar el ensamblado y el ensamblado de directiva de publicador con el mismo par de claves.</span><span class="sxs-lookup"><span data-stu-id="066f6-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="066f6-124">El `processorArchitecture` argumento identifica la plataforma de destino de un ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="066f6-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="066f6-125">La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="066f6-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="066f6-126">La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="066f6-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="066f6-127">El siguiente comando crea un `policy.1.0.myAssembly` ensamblado de directiva `pub.config`de publicador al que se llama desde `sgKey.snk` un archivo de directiva de publicador denominado , asigna un nombre seguro al ensamblado mediante el par de claves del archivo y especifica que el ensamblado tiene como destino la arquitectura del procesador x86.</span><span class="sxs-lookup"><span data-stu-id="066f6-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="066f6-128">El ensamblado de directiva de publicador debe coincidir con la arquitectura de procesador del ensamblado al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="066f6-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="066f6-129">Por lo tanto, <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> si <xref:System.Reflection.ProcessorArchitecture.MSIL>el ensamblado tiene un valor de `/platform:anycpu`, el ensamblado de directiva de publicador para ese ensamblado debe crearse con .</span><span class="sxs-lookup"><span data-stu-id="066f6-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="066f6-130">Debe proporcionar un ensamblado de directiva de publicador independiente para cada ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="066f6-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="066f6-131">Una consecuencia de esta regla es que para cambiar la arquitectura del procesador para un ensamblado, debe cambiar el componente principal o secundario del número de versión, de modo que pueda proporcionar un nuevo ensamblado de directiva de publicador con la arquitectura de procesador correcta.</span><span class="sxs-lookup"><span data-stu-id="066f6-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="066f6-132">El ensamblado de directiva de publicador anterior no puede reparar el ensamblado una vez que el ensamblado tiene una arquitectura de procesador diferente.</span><span class="sxs-lookup"><span data-stu-id="066f6-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="066f6-133">Otra consecuencia es que el vinculador de la versión 2.0 no se puede usar para crear un ensamblado de directiva de publicador para un ensamblado compilado con versiones anteriores de .NET Framework, porque siempre especifica la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="066f6-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="066f6-134">Agregar el ensamblado de directivas de publicador a la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="066f6-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="066f6-135">Utilice la herramienta Caché global de [ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directiva de publicador a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="066f6-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="066f6-136">Para agregar el ensamblado de directiva de publicador a la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="066f6-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="066f6-137">Escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="066f6-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="066f6-138">El siguiente comando `policy.1.0.myAssembly.dll` se agrega a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="066f6-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="066f6-139">El ensamblado de directiva de publicador no se puede agregar a `/link` la caché global de ensamblados a menos que el archivo de directiva de publicador original especificado en el argumento se encuentre en el mismo directorio que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="066f6-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="066f6-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="066f6-140">See also</span></span>

- [<span data-ttu-id="066f6-141">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="066f6-141">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="066f6-142">Cómo el motor en tiempo de ejecución localiza ensamblados</span><span class="sxs-lookup"><span data-stu-id="066f6-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="066f6-143">Configurar aplicaciones con archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="066f6-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="066f6-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="066f6-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="066f6-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="066f6-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="066f6-146">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="066f6-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
