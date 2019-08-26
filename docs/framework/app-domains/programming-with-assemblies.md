---
title: Programar con ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f427e2260fb26be7db0a29c47f38a3cb32dd34e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921432"
---
# <a name="programming-with-assemblies"></a><span data-ttu-id="679a4-102">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="679a4-102">Programming with Assemblies</span></span>
<span data-ttu-id="679a4-103">Los ensamblados son los bloques de creación de .NET Framework; constituyen la unidad fundamental de implementación, control de versiones, reutilización, ámbitos de activación y permisos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="679a4-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="679a4-104">Los ensamblados proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="679a4-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="679a4-105">Son una colección de tipos y recursos compilados para funcionar en conjunto y formar una unidad lógica de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="679a4-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="679a4-106">Para la ejecución, un tipo no existe fuera del contexto de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="679a4-107">En esta sección se describe cómo crear módulos, crear ensamblados a partir de módulos, crear un par de claves y firmar un ensamblado con un nombre seguro, e instalar un ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="679a4-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="679a4-108">Además, se explica cómo usar el [Desensamblador de MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para ver la información del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="679a4-109">A partir de la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará ningún ensamblado compilado con una versión de .NET Framework que tenga un número de versión superior al tiempo de ejecución cargado actualmente.</span><span class="sxs-lookup"><span data-stu-id="679a4-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="679a4-110">Esto se aplica a la combinación de los componentes principal y secundario del número de versión.</span><span class="sxs-lookup"><span data-stu-id="679a4-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="679a4-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="679a4-111">In This Section</span></span>  
 [<span data-ttu-id="679a4-112">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="679a4-112">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="679a4-113">Proporciona información general sobre los ensamblados de archivos individuales y múltiples archivos.</span><span class="sxs-lookup"><span data-stu-id="679a4-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="679a4-114">Nombres de ensamblado</span><span class="sxs-lookup"><span data-stu-id="679a4-114">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
 <span data-ttu-id="679a4-115">Proporciona información general sobre la nomenclatura del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="679a4-116">Cómo: Determinar el nombre completo de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="679a4-116">How to: Determine an Assembly's Fully Qualified Name</span></span>](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 <span data-ttu-id="679a4-117">Describe cómo determinar el nombre completo de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="679a4-118">Ejecutar aplicaciones de Intranet con plena confianza</span><span class="sxs-lookup"><span data-stu-id="679a4-118">Running Intranet Applications in Full Trust</span></span>](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="679a4-119">Describe cómo especificar la directiva de seguridad heredada para los ensamblados de plena confianza en un recurso compartido de la intranet.</span><span class="sxs-lookup"><span data-stu-id="679a4-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="679a4-120">Ubicación del ensamblado</span><span class="sxs-lookup"><span data-stu-id="679a4-120">Assembly Location</span></span>](../../../docs/framework/app-domains/assembly-location.md)  
 <span data-ttu-id="679a4-121">Proporciona una visión general de dónde ubicar los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="679a4-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="679a4-122">Cómo: Compilar un ensamblado de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="679a4-122">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 <span data-ttu-id="679a4-123">Describe cómo crear un ensamblado de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="679a4-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="679a4-124">Ensamblados de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="679a4-124">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="679a4-125">Describe las razones para crear ensamblados de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="679a4-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="679a4-126">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="679a4-126">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 <span data-ttu-id="679a4-127">Describe cómo crear un ensamblado de varios archivos.</span><span class="sxs-lookup"><span data-stu-id="679a4-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="679a4-128">Configurar atributos de ensamblados</span><span class="sxs-lookup"><span data-stu-id="679a4-128">Setting Assembly Attributes</span></span>](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 <span data-ttu-id="679a4-129">Describe los atributos de ensamblado y cómo establecerlos.</span><span class="sxs-lookup"><span data-stu-id="679a4-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="679a4-130">Crear y utilizar ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="679a4-130">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 <span data-ttu-id="679a4-131">Describe cómo y por qué se firman los ensamblados con un nombre seguro e incluye temas de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="679a4-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="679a4-132">Retrasar la firma de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="679a4-132">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 <span data-ttu-id="679a4-133">Describe cómo se retrasa la firma de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="679a4-134">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="679a4-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="679a4-135">Explica cómo y por qué se agregan ensamblados a la caché global de ensamblados e incluye temas de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="679a4-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="679a4-136">Cómo: Ver el contenido de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="679a4-136">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="679a4-137">Describe cómo usar el Desensamblador de MSIL (Ildasm.exe) para ver el contenido del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="679a4-138">Reenvío de tipos en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="679a4-138">Type Forwarding in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 <span data-ttu-id="679a4-139">Describe cómo usar el reenvío de tipos para pasar un tipo a un ensamblado diferente sin interrumpir las aplicaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="679a4-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="679a4-140">Referencia</span><span class="sxs-lookup"><span data-stu-id="679a4-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="679a4-141">Clase de .NET Framework que representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="679a4-142">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="679a4-142">Related Sections</span></span>  
 [<span data-ttu-id="679a4-143">Cómo: Obtener información sobre tipos y miembros desde un ensamblado</span><span class="sxs-lookup"><span data-stu-id="679a4-143">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="679a4-144">Describe cómo obtener mediante programación el tipo y otra información de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="679a4-145">Ensamblados en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="679a4-145">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="679a4-146">Proporciona información conceptual sobre los ensamblados Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="679a4-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="679a4-147">Versiones de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="679a4-147">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 <span data-ttu-id="679a4-148">Proporciona información general sobre el enlace de ensamblado y los atributos <xref:System.Reflection.AssemblyVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="679a4-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="679a4-149">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="679a4-149">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="679a4-150">Describe la forma en que el tiempo de ejecución determina el ensamblado que se va a usar para llevar a cabo una solicitud de enlace.</span><span class="sxs-lookup"><span data-stu-id="679a4-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 [<span data-ttu-id="679a4-151">Reflexión</span><span class="sxs-lookup"><span data-stu-id="679a4-151">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="679a4-152">Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="679a4-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
