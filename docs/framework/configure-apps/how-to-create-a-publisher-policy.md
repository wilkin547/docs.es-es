---
title: Procedimiento para crear una directiva de publicador
description: Obtenga información sobre cómo los proveedores de ensamblados pueden crear un archivo de directiva de edición con un ensamblado actualizado en .NET, para estipular que las aplicaciones deben usar la versión más reciente.
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 23e9d8144ec5742e0371d566b7af59dc9dd30c9b
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105410"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="07f18-103">Procedimiento para crear una directiva de publicador</span><span class="sxs-lookup"><span data-stu-id="07f18-103">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="07f18-104">Los proveedores de ensamblados pueden indicar que las aplicaciones deben usar una versión más reciente de un ensamblado mediante la inclusión de un archivo de directiva de edición con el ensamblado actualizado.</span><span class="sxs-lookup"><span data-stu-id="07f18-104">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="07f18-105">El archivo de directiva de edición especifica la redirección de ensamblados y la configuración de base de código, y usa el mismo formato que un archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="07f18-105">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="07f18-106">El archivo de directiva de edición se compila en un ensamblado y se coloca en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="07f18-106">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="07f18-107">Hay tres pasos implicados en la creación de una directiva de edición:</span><span class="sxs-lookup"><span data-stu-id="07f18-107">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="07f18-108">Cree un archivo de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="07f18-108">Create a publisher policy file.</span></span>

2. <span data-ttu-id="07f18-109">Cree un ensamblado de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="07f18-109">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="07f18-110">Agregue el ensamblado de directiva de edición a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="07f18-110">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="07f18-111">El esquema de la Directiva de edición se describe en [redirigir versiones de ensamblado](redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="07f18-111">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="07f18-112">En el ejemplo siguiente se muestra un archivo de directiva de edición que redirige una versión de `myAssembly` a otra.</span><span class="sxs-lookup"><span data-stu-id="07f18-112">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="07f18-113">Para obtener información sobre cómo especificar una base de código, vea [especificar la ubicación de un ensamblado](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="07f18-113">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="07f18-114">Crear el ensamblado de directiva de edición</span><span class="sxs-lookup"><span data-stu-id="07f18-114">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="07f18-115">Use el [enlazador de ensamblados (Al.exe)](../tools/al-exe-assembly-linker.md) para crear el ensamblado de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="07f18-115">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="07f18-116">Para crear un ensamblado de directiva de edición</span><span class="sxs-lookup"><span data-stu-id="07f18-116">To create a publisher policy assembly</span></span>

<span data-ttu-id="07f18-117">Escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="07f18-117">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="07f18-118">En este comando:</span><span class="sxs-lookup"><span data-stu-id="07f18-118">In this command:</span></span>

- <span data-ttu-id="07f18-119">El `publisherPolicyFile` argumento es el nombre del archivo de directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="07f18-119">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="07f18-120">El `publisherPolicyAssemblyFile` argumento es el nombre del ensamblado de directiva de edición que es el resultado de este comando.</span><span class="sxs-lookup"><span data-stu-id="07f18-120">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="07f18-121">El nombre del archivo de ensamblado debe seguir el formato:</span><span class="sxs-lookup"><span data-stu-id="07f18-121">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="07f18-122">'policy.majorNumber.minorNumber.mainAssemblyName.dll '</span><span class="sxs-lookup"><span data-stu-id="07f18-122">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="07f18-123">El `keyPairFile` argumento es el nombre del archivo que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="07f18-123">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="07f18-124">Debe firmar el ensamblado y el ensamblado de directiva de edición con el mismo par de claves.</span><span class="sxs-lookup"><span data-stu-id="07f18-124">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="07f18-125">El `processorArchitecture` argumento identifica la plataforma de destino de un ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="07f18-125">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="07f18-126">La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="07f18-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="07f18-127">La capacidad de dirigirse a una arquitectura de procesador específica está disponible a partir de .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="07f18-127">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="07f18-128">El siguiente comando crea un ensamblado de directiva `policy.1.0.myAssembly` de edición llamado desde un archivo de directiva de edición denominado `pub.config` , asigna un nombre seguro al ensamblado mediante el par de claves del `sgKey.snk` archivo y especifica que el ensamblado tiene como destino la arquitectura de procesador x86.</span><span class="sxs-lookup"><span data-stu-id="07f18-128">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="07f18-129">El ensamblado de directiva de edición debe coincidir con la arquitectura del procesador del ensamblado al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="07f18-129">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="07f18-130">Por lo tanto, si el ensamblado tiene un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valor de <xref:System.Reflection.ProcessorArchitecture.MSIL> , el ensamblado de directiva de edición para ese ensamblado debe crearse con `/platform:anycpu` .</span><span class="sxs-lookup"><span data-stu-id="07f18-130">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="07f18-131">Debe proporcionar un ensamblado de directiva de edición independiente para cada ensamblado específico del procesador.</span><span class="sxs-lookup"><span data-stu-id="07f18-131">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="07f18-132">Una consecuencia de esta regla es que para cambiar la arquitectura del procesador de un ensamblado, debe cambiar el componente principal o secundario del número de versión, para que pueda proporcionar un nuevo ensamblado de directiva de edición con la arquitectura de procesador correcta.</span><span class="sxs-lookup"><span data-stu-id="07f18-132">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="07f18-133">El ensamblado de directiva de edición anterior no puede atender el ensamblado cuando el ensamblado tiene una arquitectura de procesador diferente.</span><span class="sxs-lookup"><span data-stu-id="07f18-133">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="07f18-134">Otra consecuencia es que el enlazador de la versión 2,0 no se puede usar para crear un ensamblado de directiva de edición para un ensamblado compilado con versiones anteriores del .NET Framework, porque siempre especifica la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="07f18-134">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="07f18-135">Agregar el ensamblado de directiva de edición a la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="07f18-135">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="07f18-136">Use la [herramienta caché global de ensamblados (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para agregar el ensamblado de directiva de edición a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="07f18-136">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="07f18-137">Para agregar el ensamblado de directiva de edición a la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="07f18-137">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="07f18-138">Escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="07f18-138">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="07f18-139">El comando siguiente agrega `policy.1.0.myAssembly.dll` a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="07f18-139">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="07f18-140">El ensamblado de directiva de edición no se puede Agregar a la caché global de ensamblados a menos que el archivo de directiva de edición original especificado en el `/link` argumento se encuentre en el mismo directorio que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07f18-140">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="07f18-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="07f18-141">See also</span></span>

- [<span data-ttu-id="07f18-142">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="07f18-142">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="07f18-143">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="07f18-143">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="07f18-144">Configurar aplicaciones con archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="07f18-144">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="07f18-145">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="07f18-145">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="07f18-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="07f18-146">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="07f18-147">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="07f18-147">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
