---
title: Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: 6ee3b8cdf348a5eade3903e2d26b4f9b93886305
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706819"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="61a45-102">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="61a45-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>

<span data-ttu-id="61a45-103">En esta sección se describen las interfaces que los hosts no administrados pueden utilizar para integrar el Common Language Runtime (CLR) en el .NET Framework 4, .NET Framework 4,5 y versiones posteriores en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="61a45-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework 4, .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="61a45-104">Estas interfaces proporcionan métodos para que un host configure y cargue el tiempo de ejecución en un proceso.</span><span class="sxs-lookup"><span data-stu-id="61a45-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="61a45-105">A partir de la .NET Framework 4, todas las interfaces de hospedaje tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="61a45-105">Starting with the .NET Framework 4, all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="61a45-106">Usan la administración de la duración ( `AddRef` y `Release` ), la encapsulación (contexto implícito) y `QueryInterface` desde com.</span><span class="sxs-lookup"><span data-stu-id="61a45-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="61a45-107">No utilizan tipos COM como `BSTR` , `SAFEARRAY` o `VARIANT` .</span><span class="sxs-lookup"><span data-stu-id="61a45-107">They do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="61a45-108">No hay ningún modelo de apartamento, agregación o activación del registro que use la [función CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).</span><span class="sxs-lookup"><span data-stu-id="61a45-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61a45-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="61a45-109">In This Section</span></span>  

 [<span data-ttu-id="61a45-110">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-110">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="61a45-111">Proporciona métodos que inspeccionan el uso de la CPU y la memoria de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="61a45-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="61a45-112">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-112">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)  
 <span data-ttu-id="61a45-113">Permite al host especificar el administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="61a45-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="61a45-114">ICLRGCManager2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-114">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)  
 <span data-ttu-id="61a45-115">Proporciona el método [setgcstartuplimitsex (](iclrgcmanager2-setgcstartuplimitsex-method.md) , que permite a un host establecer el tamaño del segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="61a45-115">Provides the [SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="61a45-116">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-116">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)  
 <span data-ttu-id="61a45-117">Proporciona métodos que devuelven una versión específica de CLR, enumeran todos los CLR instalados, enumeran todos los tiempos de ejecución en proceso, devuelven la interfaz de activación y detectan la versión de CLR utilizada para compilar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="61a45-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="61a45-118">ICLRMetaHostPolicy (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-118">ICLRMetaHostPolicy Interface</span></span>](iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="61a45-119">Proporciona el método [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) que proporciona una interfaz CLR basada en los criterios de la Directiva, el ensamblado administrado, la versión y el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="61a45-119">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="61a45-120">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-120">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)  
 <span data-ttu-id="61a45-121">Proporciona métodos que devuelven información acerca de un Runtime específico, incluidos el estado de la versión, el directorio y la carga.</span><span class="sxs-lookup"><span data-stu-id="61a45-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="61a45-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)  
 <span data-ttu-id="61a45-123">Proporciona funciones estáticas globales básicas para firmar ensamblados con nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="61a45-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="61a45-124">Todos los métodos [ICLRStrongName](iclrstrongname-interface.md) devuelven valores HRESULT de com estándar.</span><span class="sxs-lookup"><span data-stu-id="61a45-124">All the [ICLRStrongName](iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="61a45-125">ICLRStrongName2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-125">ICLRStrongName2 Interface</span></span>](iclrstrongname2-interface.md)  
 <span data-ttu-id="61a45-126">Proporciona la capacidad de crear nombres seguros mediante el grupo SHA-2 de algoritmos de hash seguro (SHA-256, SHA-384 y SHA-512).</span><span class="sxs-lookup"><span data-stu-id="61a45-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="61a45-127">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="61a45-127">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)  
 <span data-ttu-id="61a45-128">Proporciona toda la funcionalidad de la [interfaz ICLRTask](iclrtask-interface.md); Además, proporciona métodos que permiten que las anulaciones de subprocesos se retrasen en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="61a45-128">Provides all the functionality of the [ICLRTask Interface](iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="61a45-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="61a45-129">Related Sections</span></span>  

 [<span data-ttu-id="61a45-130">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="61a45-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="61a45-131">Describe las interfaces de hospedaje proporcionadas con las versiones .NET Framework 1,0 y 1,1.</span><span class="sxs-lookup"><span data-stu-id="61a45-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="61a45-132">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="61a45-132">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="61a45-133">Describe las interfaces de hospedaje proporcionadas con las .NET Framework versiones 2,0, 3,0 y 3,5.</span><span class="sxs-lookup"><span data-stu-id="61a45-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="61a45-134">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="61a45-134">Hosting</span></span>](index.md)  
 <span data-ttu-id="61a45-135">Introduce el hospedaje en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61a45-135">Introduces hosting in the .NET Framework.</span></span>
