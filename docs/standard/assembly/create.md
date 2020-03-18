---
title: Creación de ensamblados
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
ms.openlocfilehash: 81fffb2b2e1d56d6068bf6f663a13fad6968a383
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73740508"
---
# <a name="create-assemblies"></a><span data-ttu-id="602d4-102">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="602d4-102">Create assemblies</span></span>

<span data-ttu-id="602d4-103">Para crear ensamblados de un solo archivo o de varios archivos, se puede usar un IDE, como Visual Studio, o los compiladores y las herramientas que proporciona Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="602d4-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows SDK.</span></span> <span data-ttu-id="602d4-104">El ensamblado más sencillo es un solo archivo que tiene un nombre simple y se carga en un solo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="602d4-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="602d4-105">Este ensamblado no se somete a la comprobación de versión y no pueden hacer referencia a él otros ensamblados fuera del directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="602d4-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="602d4-106">Para desinstalar la aplicación que se compone del ensamblado, basta con eliminar el directorio en el que reside.</span><span class="sxs-lookup"><span data-stu-id="602d4-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="602d4-107">Muchos desarrolladores solo necesitan un ensamblado de estas características para implementar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="602d4-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="602d4-108">Puede crear un ensamblado de varios archivos a partir de varios módulos de código y archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="602d4-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="602d4-109">También puede crear un ensamblado que compartan varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="602d4-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="602d4-110">Un ensamblado compartido debe tener un nombre seguro y puede implementarse en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="602d4-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="602d4-111">Existen varias opciones al agrupar módulos de código y recursos en ensamblados, en función de los factores siguientes:</span><span class="sxs-lookup"><span data-stu-id="602d4-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="602d4-112">Control de versiones</span><span class="sxs-lookup"><span data-stu-id="602d4-112">Versioning</span></span>

     <span data-ttu-id="602d4-113">Agrupar módulos con la misma información de versión.</span><span class="sxs-lookup"><span data-stu-id="602d4-113">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="602d4-114">Implementación</span><span class="sxs-lookup"><span data-stu-id="602d4-114">Deployment</span></span>

     <span data-ttu-id="602d4-115">Agrupar módulos de código y recursos compatibles con el modelo de implementación.</span><span class="sxs-lookup"><span data-stu-id="602d4-115">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="602d4-116">Reutilización</span><span class="sxs-lookup"><span data-stu-id="602d4-116">Reuse</span></span>

     <span data-ttu-id="602d4-117">Agrupar módulos si se pueden usar juntos lógicamente con el mismo fin.</span><span class="sxs-lookup"><span data-stu-id="602d4-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="602d4-118">Por ejemplo, un ensamblado formado por tipos y clases que se usan con poca frecuencia para el mantenimiento de programas puede colocarse en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="602d4-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="602d4-119">Además, los tipos que está previsto compartir con varias aplicaciones deben agruparse en un ensamblado y el ensamblado debe firmarse con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="602d4-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="602d4-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="602d4-120">Security</span></span>

     <span data-ttu-id="602d4-121">Agrupar módulos que contienen tipos que requieren los mismos permisos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="602d4-121">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="602d4-122">Ámbito</span><span class="sxs-lookup"><span data-stu-id="602d4-122">Scoping</span></span>

     <span data-ttu-id="602d4-123">Agrupar módulos que contienen tipos cuya visibilidad se debe restringir al mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="602d4-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="602d4-124">Se deben tener en cuenta consideraciones especiales a la hora de poner los ensamblados de Common Language Runtime a disposición de aplicaciones COM no administradas.</span><span class="sxs-lookup"><span data-stu-id="602d4-124">There are special considerations when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="602d4-125">Para obtener más información sobre cómo trabajar con código no administrado, vea [Exposición de los componentes de .NET a COM](../../framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="602d4-125">For more information about working with unmanaged code, see [Expose .NET Framework components to COM](../../framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="602d4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="602d4-126">See also</span></span>

- [<span data-ttu-id="602d4-127">Control de versiones de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="602d4-127">Assembly versioning</span></span>](versioning.md)
- [<span data-ttu-id="602d4-128">Cómo: Compilar un ensamblado de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="602d4-128">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)
- [<span data-ttu-id="602d4-129">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="602d4-129">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="602d4-130">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="602d4-130">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="602d4-131">Ensamblados de varios archivos</span><span class="sxs-lookup"><span data-stu-id="602d4-131">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)
