---
title: Referencia de la API no administrada
ms.custom: 
ms.date: 11/06/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- runtime, unmanaged APIs
- common language runtime, unmanaged APIs
- native API reference [.NET Framework]
- unmanaged API reference [.NET Framework]
ms.assetid: 9aa000ee-c04c-492c-ae4f-83ecdf4fdbbe
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9836d8d02bb81fc19a5b3a1714e32fcefeb8791d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="unmanaged-api-reference"></a><span data-ttu-id="1e4b0-102">Referencia de la API no administrada</span><span class="sxs-lookup"><span data-stu-id="1e4b0-102">Unmanaged API Reference</span></span>
<span data-ttu-id="1e4b0-103">En esta sección se incluye información acerca de las API no administradas que se pueden utilizar en aplicaciones relacionadas con código administrado, como hosts en tiempo de ejecución, compiladores, desensambladores, ofuscadores, depuradores y generadores de perfiles.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-103">This section includes information on unmanaged APIs that can be used by managed-code-related applications, such as runtime hosts, compilers, disassemblers, obfuscators, debuggers, and profilers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e4b0-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1e4b0-104">In This Section</span></span>  
 [<span data-ttu-id="1e4b0-105">Tipos de datos comunes</span><span class="sxs-lookup"><span data-stu-id="1e4b0-105">Common Data Types</span></span>](../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)  
 <span data-ttu-id="1e4b0-106">Enumera los tipos de datos comunes que se usan, especialmente en las API de depuración y de generación de perfiles no administradas.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-106">Lists the common data types that are used, particularly in the unmanaged profiling and debugging APIs.</span></span>  
  
 [<span data-ttu-id="1e4b0-107">ALink</span><span class="sxs-lookup"><span data-stu-id="1e4b0-107">ALink</span></span>](../../../docs/framework/unmanaged-api/alink/index.md)  
 <span data-ttu-id="1e4b0-108">Describe la API ALink, que admite la creación de ensamblados .NET Framework y módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-108">Describes the ALink API, which supports the creation of .NET Framework assemblies and unbound modules.</span></span>  
  
 [<span data-ttu-id="1e4b0-109">Authenticode</span><span class="sxs-lookup"><span data-stu-id="1e4b0-109">Authenticode</span></span>](../../../docs/framework/unmanaged-api/authenticode/index.md)  
 <span data-ttu-id="1e4b0-110">Admite el módulo de creación y verificación de licencias Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-110">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
 [<span data-ttu-id="1e4b0-111">Constantes</span><span class="sxs-lookup"><span data-stu-id="1e4b0-111">Constants</span></span>](../../../docs/framework/unmanaged-api/constants-unmanaged-api-reference.md)  
 <span data-ttu-id="1e4b0-112">Describe las constantes que se definen en CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-112">Describes the constants that are defined in CorSym.idl.</span></span>  
  
 [<span data-ttu-id="1e4b0-113">Atributos de interfaz personalizados</span><span class="sxs-lookup"><span data-stu-id="1e4b0-113">Custom Interface Attributes</span></span>](http://msdn.microsoft.com/en-us/940952f9-46ad-4a1a-920f-118dc0bdcd9f)  
 <span data-ttu-id="1e4b0-114">Describe los atributos de interfaz personalizados del Modelo de objetos componentes (COM).</span><span class="sxs-lookup"><span data-stu-id="1e4b0-114">Describes component object model (COM) custom interface attributes.</span></span>  
  
 [<span data-ttu-id="1e4b0-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="1e4b0-115">Debugging</span></span>](../../../docs/framework/unmanaged-api/debugging/index.md)  
 <span data-ttu-id="1e4b0-116">Describe la API de depuración, que permite a un depurador depurar el código que se ejecuta en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1e4b0-116">Describes the debugging API, which enables a debugger to debug code that runs in the common language runtime (CLR) environment.</span></span>  
  
 [<span data-ttu-id="1e4b0-117">Almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1e4b0-117">Diagnostics Symbol Store</span></span>](../../../docs/framework/unmanaged-api/diagnostics/index.md)  
 <span data-ttu-id="1e4b0-118">Describe la API de almacén de símbolos de diagnóstico, que permite a un compilador generar información sobre símbolos para que la use un depurador.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-118">Describes the diagnostics symbol store API, which enables a compiler to generate symbol information for use by a debugger.</span></span>  
  
 [<span data-ttu-id="1e4b0-119">Fusión</span><span class="sxs-lookup"><span data-stu-id="1e4b0-119">Fusion</span></span>](../../../docs/framework/unmanaged-api/fusion/index.md)  
 <span data-ttu-id="1e4b0-120">Describe la API de fusión, que permite a un host de tiempo de ejecución acceder a las propiedades de los recursos de una aplicación para encontrar las versiones correctas de estos recursos para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-120">Describes the fusion API, which enables a runtime host to access the properties of an application's resources in order to locate the correct versions of those resources for the application.</span></span>  
  
 [<span data-ttu-id="1e4b0-121">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1e4b0-121">Hosting</span></span>](../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="1e4b0-122">Describe la API de hospedaje, que permite a los hosts no administrados integrar CLR en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-122">Describes the hosting API, which enables unmanaged hosts to integrate the CLR into their applications.</span></span>  
  
 [<span data-ttu-id="1e4b0-123">Metadatos</span><span class="sxs-lookup"><span data-stu-id="1e4b0-123">Metadata</span></span>](../../../docs/framework/unmanaged-api/metadata/index.md)  
 <span data-ttu-id="1e4b0-124">Describe la API de metadatos, que permite a un cliente, como un compilador, generar o acceder a los metadatos de un componente sin que CLR cargue los tipos.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-124">Describes the metadata API, which enables a client such as a compiler to generate or access a component's metadata without the types being loaded by the CLR.</span></span>  
  
 [<span data-ttu-id="1e4b0-125">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1e4b0-125">Profiling</span></span>](../../../docs/framework/unmanaged-api/profiling/index.md)  
 <span data-ttu-id="1e4b0-126">Describe la API de generación de perfiles, que permite a un generador de perfiles supervisar la ejecución que CLR hace de un programa.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-126">Describes the profiling API, which enables a profiler to monitor a program's execution by the CLR.</span></span>  
  
 [<span data-ttu-id="1e4b0-127">Nombres seguros</span><span class="sxs-lookup"><span data-stu-id="1e4b0-127">Strong Naming</span></span>](../../../docs/framework/unmanaged-api/strong-naming/index.md)  
 <span data-ttu-id="1e4b0-128">Describe la API de nombres seguros, que permite a un cliente administrar la firma de ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-128">Describes the strong naming API, which enables a client to administer strong name signing for assemblies.</span></span>  

 [<span data-ttu-id="1e4b0-129">WMI y contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="1e4b0-129">WMI and Performance Counters</span></span>](wmi/index.md)  
 <span data-ttu-id="1e4b0-130">Describe las API que encapsulan llamadas a las bibliotecas de Windows Management Instrumentation (WMI).</span><span class="sxs-lookup"><span data-stu-id="1e4b0-130">Describes the APIs that wrap calls to Windows Management Instrumentation (WMI) libraries.</span></span>
  
 [<span data-ttu-id="1e4b0-131">Funciones auxiliares Tlbexp</span><span class="sxs-lookup"><span data-stu-id="1e4b0-131">Tlbexp Helper Functions</span></span>](../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="1e4b0-132">Describe las dos funciones auxiliares y la interfaz que usa el Exportador de la biblioteca de tipos (Tlbexp.exe) durante el proceso de conversión de ensamblado a biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="1e4b0-132">Describes the two helper functions and interface used by the Type Library Exporter (Tlbexp.exe) during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e4b0-133">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1e4b0-133">Related Sections</span></span>  
 [<span data-ttu-id="1e4b0-134">Guía de desarrollo</span><span class="sxs-lookup"><span data-stu-id="1e4b0-134">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
  
 [<span data-ttu-id="1e4b0-135">Información avanzada para .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1e4b0-135">Advanced Reading for the .NET Framework</span></span>](http://msdn.microsoft.com/en-us/faae8083-fecb-4514-b133-b0a5a32a7c3c)
