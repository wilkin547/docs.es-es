---
title: Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6405c61429d56b125fd0327824482bf702e41319
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380280"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="a269f-102">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="a269f-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="a269f-103">Esta sección describen las interfaces que no administrada de hosts pueden usar para integrar common language runtime (CLR) en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], .NET Framework 4.5 y versiones posteriores en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a269f-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="a269f-104">Estas interfaces proporcionan métodos para un host configurar y cargar el tiempo de ejecución en un proceso.</span><span class="sxs-lookup"><span data-stu-id="a269f-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="a269f-105">A partir de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], hospedaje todas las interfaces tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="a269f-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="a269f-106">Usar administración de la duración (`AddRef` y `Release`), encapsulación (contexto implícito) y `QueryInterface` desde COM.</span><span class="sxs-lookup"><span data-stu-id="a269f-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="a269f-107">No usan tipos COM como `BSTR`, `SAFEARRAY`, o `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="a269f-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="a269f-108">Hay no hay modelos de apartamento, agregación o activación del registro que usan el [función CoCreateInstance](https://go.microsoft.com/fwlink/?LinkId=142894).</span><span class="sxs-lookup"><span data-stu-id="a269f-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](https://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a269f-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a269f-109">In This Section</span></span>  
 [<span data-ttu-id="a269f-110">ICLRAppDomainResourceMonitor (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="a269f-111">Proporciona métodos que inspeccionar memoria y uso de CPU de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a269f-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="a269f-112">ICLRDomainManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="a269f-113">Permite que el host especificar el Administrador de dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="a269f-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="a269f-114">ICLRGCManager2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="a269f-115">Proporciona el [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) método, que permite a un host establecer el tamaño del segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados en los valores mayor `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="a269f-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="a269f-116">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="a269f-117">Proporciona métodos que devuelven una versión específica de CLR, enumerar todos los CLR instalados, enumerar todos los tiempos de ejecución en proceso, devuelven la interfaz de activación y detección la versión CLR utilizada para compilar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a269f-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="a269f-118">ICLRMetaHostPolicy (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="a269f-119">Proporciona el [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método que proporciona una interfaz CLR basándose en criterios de la directiva, ensamblado administrado, versión y archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a269f-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="a269f-120">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="a269f-121">Proporciona métodos que devuelven información acerca de un tiempo de ejecución específico, incluida la versión, el directorio y el estado de carga.</span><span class="sxs-lookup"><span data-stu-id="a269f-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="a269f-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="a269f-123">Proporciona funciones estáticas globales para básicas para firmar los ensamblados con nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="a269f-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="a269f-124">Todos los [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) métodos devuelven valores HRESULT de COM estándar.</span><span class="sxs-lookup"><span data-stu-id="a269f-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="a269f-125">ICLRStrongName2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="a269f-126">Proporciona la capacidad para crear nombres seguros mediante el grupo de SHA-2 de algoritmos de Hash seguro (SHA-256, SHA-384 y SHA-512).</span><span class="sxs-lookup"><span data-stu-id="a269f-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="a269f-127">ICLRTask2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a269f-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="a269f-128">Proporciona toda la funcionalidad de la [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); Además, proporciona métodos que permiten las anulaciones de subprocesos para que se retrasa en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a269f-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a269f-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a269f-129">Related Sections</span></span>  
 [<span data-ttu-id="a269f-130">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="a269f-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="a269f-131">Describe las interfaces de hospedaje proporcionadas con las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a269f-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="a269f-132">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="a269f-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="a269f-133">Describe las interfaces de hospedaje proporcionadas con las versiones de .NET Framework 2.0, 3.0 y 3.5.</span><span class="sxs-lookup"><span data-stu-id="a269f-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="a269f-134">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a269f-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="a269f-135">Presenta el hospedaje de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a269f-135">Introduces hosting in the .NET Framework.</span></span>
