---
title: Programación con ensamblados
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
ms.openlocfilehash: 9f07d36d9e47189d53e367fd1406e5684c024aa3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107054"
---
# <a name="program-with-assemblies"></a><span data-ttu-id="3d5c1-102">Programación con ensamblados</span><span class="sxs-lookup"><span data-stu-id="3d5c1-102">Program with assemblies</span></span>
<span data-ttu-id="3d5c1-103">Los ensamblados son los bloques de creación de .NET Framework; constituyen la unidad fundamental de implementación, control de versiones, reutilización, ámbitos de activación y permisos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="3d5c1-104">Los ensamblados proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="3d5c1-105">Son una colección de tipos y recursos compilados para funcionar en conjunto y formar una unidad lógica de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="3d5c1-106">Para la ejecución, un tipo no existe fuera del contexto de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="3d5c1-107">En esta sección se describe cómo crear módulos, crear ensamblados a partir de módulos, crear un par de claves y firmar un ensamblado con un nombre seguro, e instalar un ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="3d5c1-108">Además, se explica cómo usar el [Desensamblador de MSIL (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) para ver la información del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d5c1-109">A partir de la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará ningún ensamblado compilado con una versión de .NET Framework que tenga un número de versión superior al tiempo de ejecución cargado actualmente.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="3d5c1-110">Esto se aplica a la combinación de los componentes principal y secundario del número de versión.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d5c1-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3d5c1-111">In this section</span></span>  
 [<span data-ttu-id="3d5c1-112">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3d5c1-112">Create assemblies</span></span>](create.md)  
 <span data-ttu-id="3d5c1-113">Proporciona información general sobre los ensamblados de archivos individuales y múltiples archivos.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="3d5c1-114">Nombres de ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d5c1-114">Assembly names</span></span>](names.md)  
 <span data-ttu-id="3d5c1-115">Proporciona información general sobre la nomenclatura del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="3d5c1-116">Cómo: Determinar el nombre completo de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d5c1-116">How to: Determine an assembly's fully qualified name</span></span>](find-fully-qualified-name.md)  
 <span data-ttu-id="3d5c1-117">Describe cómo determinar el nombre completo de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="3d5c1-118">Ejecutar aplicaciones de Intranet con plena confianza</span><span class="sxs-lookup"><span data-stu-id="3d5c1-118">Run intranet applications in full trust</span></span>](../../framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="3d5c1-119">Describe cómo especificar la directiva de seguridad heredada para los ensamblados de plena confianza en un recurso compartido de la intranet.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="3d5c1-120">Ubicación del ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d5c1-120">Assembly location</span></span>](location.md)  
 <span data-ttu-id="3d5c1-121">Proporciona una visión general de dónde ubicar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="3d5c1-122">Cómo: Compilar un ensamblado de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="3d5c1-122">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)  
 <span data-ttu-id="3d5c1-123">Describe cómo crear un ensamblado de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="3d5c1-124">Ensamblados de varios archivos</span><span class="sxs-lookup"><span data-stu-id="3d5c1-124">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="3d5c1-125">Describe las razones para crear ensamblados de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="3d5c1-126">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="3d5c1-126">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)  
 <span data-ttu-id="3d5c1-127">Describe cómo crear un ensamblado de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="3d5c1-128">Establecer atributos de ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d5c1-128">Set assembly attributes</span></span>](set-attributes.md)  
 <span data-ttu-id="3d5c1-129">Describe los atributos de ensamblado y cómo establecerlos.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="3d5c1-130">Creación y uso de ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="3d5c1-130">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)  
 <span data-ttu-id="3d5c1-131">Describe cómo y por qué se firman los ensamblados con un nombre seguro e incluye temas de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="3d5c1-132">Retraso de la firma de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d5c1-132">Delay-sign an assembly</span></span>](delay-sign.md)  
 <span data-ttu-id="3d5c1-133">Describe cómo se retrasa la firma de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="3d5c1-134">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="3d5c1-134">Work with assemblies and the global assembly cache</span></span>](../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="3d5c1-135">Explica cómo y por qué se agregan ensamblados a la caché global de ensamblados e incluye temas de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="3d5c1-136">Cómo: Ver el contenido de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d5c1-136">How to: View assembly contents</span></span>](view-contents.md)  
 <span data-ttu-id="3d5c1-137">Describe cómo usar el Desensamblador de MSIL (Ildasm.exe) para ver el contenido del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="3d5c1-138">Reenvío de tipos en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3d5c1-138">Type forwarding in the common language runtime</span></span>](type-forwarding.md)  
 <span data-ttu-id="3d5c1-139">Describe cómo usar el reenvío de tipos para pasar un tipo a un ensamblado diferente sin interrumpir las aplicaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3d5c1-140">Referencia</span><span class="sxs-lookup"><span data-stu-id="3d5c1-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="3d5c1-141">Clase de .NET Framework que representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3d5c1-142">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3d5c1-142">Related sections</span></span>  
 [<span data-ttu-id="3d5c1-143">Cómo: Obtener información sobre tipos y miembros desde un ensamblado</span><span class="sxs-lookup"><span data-stu-id="3d5c1-143">How to: Obtain type and member information from an assembly</span></span>](../../framework/reflection-and-codedom/get-type-member-information.md)  
 <span data-ttu-id="3d5c1-144">Describe cómo obtener mediante programación el tipo y otra información de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="3d5c1-145">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="3d5c1-145">Assemblies in .NET</span></span>](index.md)  
 <span data-ttu-id="3d5c1-146">Proporciona información conceptual sobre los ensamblados Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="3d5c1-147">Versiones de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="3d5c1-147">Assembly versioning</span></span>](versioning.md)  
 <span data-ttu-id="3d5c1-148">Proporciona información general sobre el enlace de ensamblado y los atributos <xref:System.Reflection.AssemblyVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="3d5c1-149">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3d5c1-149">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="3d5c1-150">Describe la forma en que el tiempo de ejecución determina el ensamblado que se va a usar para llevar a cabo una solicitud de enlace.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 <span data-ttu-id="3d5c1-151">[Reflexión](../../framework/reflection-and-codedom/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="3d5c1-151">[Reflection](../../framework/reflection-and-codedom/reflection.md) </span></span>  
 <span data-ttu-id="3d5c1-152">Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3d5c1-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
