---
description: 'Más información acerca de: enumeración STARTUP_FLAGS'
title: STARTUP_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
ms.openlocfilehash: 2136f1c43545342f2cdc7cde884999a2f2c11bdd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679347"
---
# <a name="startup_flags-enumeration"></a><span data-ttu-id="5300d-103">STARTUP_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5300d-103">STARTUP_FLAGS Enumeration</span></span>

<span data-ttu-id="5300d-104">Contiene valores que indican el comportamiento de inicio de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5300d-104">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="5300d-105">De manera predeterminada, la recolección de elementos no utilizados es no simultánea y solo se carga la biblioteca de clases base en el área neutral con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="5300d-105">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5300d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5300d-106">Syntax</span></span>  
  
```cpp  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="5300d-107">Members</span><span class="sxs-lookup"><span data-stu-id="5300d-107">Members</span></span>  
  
|<span data-ttu-id="5300d-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="5300d-108">Member</span></span>|<span data-ttu-id="5300d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5300d-109">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="5300d-110">Especifica que se debería utilizar la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="5300d-110">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="5300d-111">Si el llamador solicita la compilación para servidor y la recolección de elementos no utilizados simultánea en un equipo con un solo procesador, se ejecuta, en su lugar, la versión para estación de trabajo y la recolección no simultánea de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5300d-111">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="5300d-112">**Nota:**  No se admite la recolección de elementos no utilizados simultánea en aplicaciones que ejecutan el emulador WOW64 x86 en sistemas de 64 bits que implementan la arquitectura Intel Itanium (denominada anteriormente IA-64).</span><span class="sxs-lookup"><span data-stu-id="5300d-112">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="5300d-113">Para obtener más información sobre el uso de WOW64 en sistemas Windows de 64 bits, vea [ejecutar aplicaciones de 32 bits](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="5300d-113">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="5300d-114">Especifica que se producirá la optimización del cargador.</span><span class="sxs-lookup"><span data-stu-id="5300d-114">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="5300d-115">Especifica que ningún ensamblado se carga como neutral con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="5300d-115">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="5300d-116">Especifica que todos los ensamblados se cargan como neutrales con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="5300d-116">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="5300d-117">Especifica que todos los ensamblados de nombre seguro se cargan como neutrales con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="5300d-117">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="5300d-118">Especifica que la directiva de versión de CLR no se aplicará a la versión pasada.</span><span class="sxs-lookup"><span data-stu-id="5300d-118">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="5300d-119">Se cargará la versión exacta especificada de CLR.</span><span class="sxs-lookup"><span data-stu-id="5300d-119">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="5300d-120">El proceso intermedio ("shim") no evalúa directivas para determinar la última versión compatible.</span><span class="sxs-lookup"><span data-stu-id="5300d-120">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="5300d-121">Especifica que se establecerá el motor en tiempo de ejecución preferido, pero en realidad no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="5300d-121">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="5300d-122">Especifica que se usará la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="5300d-122">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="5300d-123">Especifica que la recolección de elementos no utilizados mantendrá la dirección virtual usada.</span><span class="sxs-lookup"><span data-stu-id="5300d-123">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="5300d-124">Especifica que no se permitirá combinar una interfaz de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="5300d-124">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="5300d-125">Especifica que la suplantación no debería fluir de forma predeterminada por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="5300d-125">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="5300d-126">Especifica que no se debería confirmar la pila de subprocesos completa cuando el subproceso inicia el funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="5300d-126">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="5300d-127">Especifica que las suplantaciones administradas y las suplantaciones logradas a través de la invocación de plataforma fluirán por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="5300d-127">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="5300d-128">De forma predeterminada, solo las suplantaciones administradas fluirán por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="5300d-128">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="5300d-129">Especifica que la recolección de elementos no utilizados usará el espacio menos confirmado cuando quede poca memoria del sistema.</span><span class="sxs-lookup"><span data-stu-id="5300d-129">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="5300d-130">Vea `gcTrimCommitOnLowMemory` en [optimización para el hospedaje web compartido](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="5300d-130">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="5300d-131">Especifica que el seguimiento de eventos para Windows (ETW) está habilitado para los eventos de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5300d-131">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="5300d-132">A partir de Windows Vista, el seguimiento de eventos siempre está habilitado, de modo que esta marca no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="5300d-132">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="5300d-133">Consulte [control del registro de .NET Framework](../../performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="5300d-133">See [Controlling .NET Framework Logging](../../performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="5300d-134">Especifica que la supervisión de recursos de dominio de aplicación está habilitada.</span><span class="sxs-lookup"><span data-stu-id="5300d-134">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="5300d-135">Vea la <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> propiedad y el [ \<appDomainResourceMonitoring> elemento](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span><span class="sxs-lookup"><span data-stu-id="5300d-135">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5300d-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5300d-136">Requirements</span></span>  

 <span data-ttu-id="5300d-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5300d-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5300d-138">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5300d-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5300d-139">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5300d-139">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5300d-140">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5300d-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5300d-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="5300d-141">See also</span></span>

- [<span data-ttu-id="5300d-142">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="5300d-142">Hosting Enumerations</span></span>](hosting-enumerations.md)
