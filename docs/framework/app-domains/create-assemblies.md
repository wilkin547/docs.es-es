---
title: Crear ensamblados
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 993c7f590f30b44f45e4833b4364b40ad9748b58
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607767"
---
# <a name="creating-assemblies"></a><span data-ttu-id="beac3-102">Crear ensamblados</span><span class="sxs-lookup"><span data-stu-id="beac3-102">Creating Assemblies</span></span>

<span data-ttu-id="beac3-103">Para crear ensamblados de un solo archivo o de varios archivos, se puede usar un IDE, como Visual Studio, o los compiladores y las herramientas que proporciona el [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="beac3-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span> <span data-ttu-id="beac3-104">El ensamblado más sencillo es un solo archivo que tiene un nombre simple y se carga en un solo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="beac3-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="beac3-105">Este ensamblado no se somete a la comprobación de versión y no pueden hacer referencia a él otros ensamblados fuera del directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="beac3-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="beac3-106">Para desinstalar la aplicación que se compone del ensamblado, basta con eliminar el directorio en el que reside.</span><span class="sxs-lookup"><span data-stu-id="beac3-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="beac3-107">Muchos desarrolladores solo necesitan un ensamblado de estas características para implementar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="beac3-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="beac3-108">Puede crear un ensamblado de varios archivos a partir de varios módulos de código y archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="beac3-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="beac3-109">También puede crear un ensamblado que compartan varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="beac3-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="beac3-110">Un ensamblado compartido debe tener un nombre seguro y puede implementarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="beac3-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="beac3-111">Existen varias opciones al agrupar módulos de código y recursos en ensamblados, en función de los factores siguientes:</span><span class="sxs-lookup"><span data-stu-id="beac3-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="beac3-112">Control de versiones</span><span class="sxs-lookup"><span data-stu-id="beac3-112">Versioning</span></span>

     <span data-ttu-id="beac3-113">Agrupar módulos con la misma información de versión.</span><span class="sxs-lookup"><span data-stu-id="beac3-113">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="beac3-114">Implementación</span><span class="sxs-lookup"><span data-stu-id="beac3-114">Deployment</span></span>

     <span data-ttu-id="beac3-115">Agrupar módulos de código y recursos compatibles con el modelo de implementación.</span><span class="sxs-lookup"><span data-stu-id="beac3-115">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="beac3-116">Reutilización</span><span class="sxs-lookup"><span data-stu-id="beac3-116">Reuse</span></span>

     <span data-ttu-id="beac3-117">Agrupar módulos si se pueden usar juntos lógicamente con el mismo fin.</span><span class="sxs-lookup"><span data-stu-id="beac3-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="beac3-118">Por ejemplo, un ensamblado formado por tipos y clases que se usan con poca frecuencia para el mantenimiento de programas puede colocarse en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="beac3-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="beac3-119">Además, los tipos que está previsto compartir con varias aplicaciones deben agruparse en un ensamblado y el ensamblado debe firmarse con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="beac3-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="beac3-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="beac3-120">Security</span></span>

     <span data-ttu-id="beac3-121">Agrupar módulos que contienen tipos que requieren los mismos permisos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="beac3-121">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="beac3-122">Ámbito</span><span class="sxs-lookup"><span data-stu-id="beac3-122">Scoping</span></span>

     <span data-ttu-id="beac3-123">Agrupar módulos que contienen tipos cuya visibilidad se debe restringir al mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="beac3-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="beac3-124">Deben tenerse en cuenta consideraciones especiales cuando los ensamblados de Common Language Runtime se ponen a disposición de aplicaciones COM no administradas.</span><span class="sxs-lookup"><span data-stu-id="beac3-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="beac3-125">Para obtener más información sobre cómo trabajar con código no administrado, vea [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md) (Exponer componentes de .NET Framework en COM).</span><span class="sxs-lookup"><span data-stu-id="beac3-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="beac3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="beac3-126">See also</span></span>

- [<span data-ttu-id="beac3-127">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="beac3-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="beac3-128">Versiones de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="beac3-128">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)
- [<span data-ttu-id="beac3-129">Cómo: Compilar un ensamblado de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="beac3-129">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)
- [<span data-ttu-id="beac3-130">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="beac3-130">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="beac3-131">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="beac3-131">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="beac3-132">Ensamblados de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="beac3-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)