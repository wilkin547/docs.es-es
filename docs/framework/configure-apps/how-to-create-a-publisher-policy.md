---
title: 'Cómo: Crear una directiva de publicador'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 313af6046fda8dd8905e8bda4e8c4aec187ef8bf
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568402"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="6c32e-102">Cómo: Crear una directiva de publicador</span><span class="sxs-lookup"><span data-stu-id="6c32e-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="6c32e-103">Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de edición con el ensamblado actualizado.</span><span class="sxs-lookup"><span data-stu-id="6c32e-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="6c32e-104">El archivo de directiva de edición especifica la redirección de ensamblados y la configuración de base de código, y usa el mismo formato que un archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c32e-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="6c32e-105">El archivo de directiva de edición se compila en un ensamblado y se coloca en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6c32e-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="6c32e-106">Hay tres pasos implicados en la creación de una directiva de edición:</span><span class="sxs-lookup"><span data-stu-id="6c32e-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="6c32e-107">Cree un archivo de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="6c32e-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="6c32e-108">Cree un ensamblado de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="6c32e-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="6c32e-109">Agregue el ensamblado de directiva de edición a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6c32e-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="6c32e-110">El esquema de la Directiva de edición se describe en [redirigir versiones de ensamblado](redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="6c32e-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="6c32e-111">En el ejemplo siguiente se muestra un archivo de directiva de edición que redirige una versión de `myAssembly` a otra.</span><span class="sxs-lookup"><span data-stu-id="6c32e-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="6c32e-112">Para obtener información sobre cómo especificar una base de código, vea [especificar la ubicación de un ensamblado](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="6c32e-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="6c32e-113">Crear el ensamblado de directiva de edición</span><span class="sxs-lookup"><span data-stu-id="6c32e-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="6c32e-114">Use [Assembly Linker (al. exe)](../tools/al-exe-assembly-linker.md) para crear el ensamblado de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="6c32e-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="6c32e-115">Para crear un ensamblado de directiva de edición</span><span class="sxs-lookup"><span data-stu-id="6c32e-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="6c32e-116">Escriba el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="6c32e-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="6c32e-117">En este comando:</span><span class="sxs-lookup"><span data-stu-id="6c32e-117">In this command:</span></span>

- <span data-ttu-id="6c32e-118">El `publisherPolicyFile` argumento es el nombre del archivo de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="6c32e-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="6c32e-119">El `publisherPolicyAssemblyFile` argumento es el nombre del ensamblado de directiva de edición que se obtiene de este comando.</span><span class="sxs-lookup"><span data-stu-id="6c32e-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="6c32e-120">El nombre del archivo de ensamblado debe seguir el formato:</span><span class="sxs-lookup"><span data-stu-id="6c32e-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="6c32e-121">' Policy. majorNumber. minorNumber. mainAssemblyName. dll '</span><span class="sxs-lookup"><span data-stu-id="6c32e-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="6c32e-122">El `keyPairFile` argumento es el nombre del archivo que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="6c32e-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="6c32e-123">Debe firmar el ensamblado y el ensamblado de directiva de edición con el mismo par de claves.</span><span class="sxs-lookup"><span data-stu-id="6c32e-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="6c32e-124">El argumento `processorArchitecture` identifica la plataforma de destino de un ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="6c32e-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6c32e-125">La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="6c32e-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="6c32e-126">La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="6c32e-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="6c32e-127">El siguiente comando crea un ensamblado de directiva de edición denominado `policy.1.0.myAssembly` a partir de un archivo de directiva de edición denominado `pub.config`, asigna un nombre seguro al ensamblado mediante el par de claves del archivo `sgKey.snk` y especifica que el ensamblado tiene como destino la arquitectura de procesador x86.</span><span class="sxs-lookup"><span data-stu-id="6c32e-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="6c32e-128">El ensamblado de directiva de edición debe coincidir con la arquitectura del procesador del ensamblado al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="6c32e-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="6c32e-129">Por lo tanto, si el ensamblado tiene un valor <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> de <xref:System.Reflection.ProcessorArchitecture.MSIL>, se debe crear el ensamblado de directiva de edición para ese ensamblado con `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="6c32e-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="6c32e-130">Debe proporcionar un ensamblado de directiva de edición independiente para cada ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="6c32e-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="6c32e-131">Una consecuencia de esta regla es que para cambiar la arquitectura del procesador de un ensamblado, debe cambiar el componente principal o secundario del número de versión, para que pueda proporcionar un nuevo ensamblado de directiva de edición con la arquitectura de procesador correcta.</span><span class="sxs-lookup"><span data-stu-id="6c32e-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="6c32e-132">El ensamblado de directiva de edición anterior no puede atender el ensamblado cuando el ensamblado tiene una arquitectura de procesador diferente.</span><span class="sxs-lookup"><span data-stu-id="6c32e-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="6c32e-133">Otra consecuencia es que el enlazador de la versión 2,0 no se puede usar para crear un ensamblado de directiva de edición para un ensamblado compilado con versiones anteriores del .NET Framework, porque siempre especifica la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="6c32e-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="6c32e-134">Agregar el ensamblado de directiva de edición a la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="6c32e-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="6c32e-135">Use la [herramienta caché global de ensamblados (Gacutil. exe)](../tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directiva de edición a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6c32e-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="6c32e-136">Para agregar el ensamblado de directiva de edición a la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="6c32e-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="6c32e-137">Escriba el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="6c32e-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="6c32e-138">El comando siguiente agrega `policy.1.0.myAssembly.dll` a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6c32e-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="6c32e-139">El ensamblado de directiva de edición no se puede Agregar a la caché global de ensamblados a menos que el archivo de directiva de edición original especificado en el argumento `/link` se encuentre en el mismo directorio que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6c32e-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c32e-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c32e-140">See also</span></span>

- [<span data-ttu-id="6c32e-141">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="6c32e-141">Programming with Assemblies</span></span>](../../standard/assembly/program.md)
- [<span data-ttu-id="6c32e-142">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="6c32e-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="6c32e-143">Configuración de aplicaciones mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6c32e-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="6c32e-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="6c32e-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="6c32e-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6c32e-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="6c32e-146">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="6c32e-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
