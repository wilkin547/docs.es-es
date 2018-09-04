---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4680187de7318a6438bf6a5e6bd7c5f3acd05c2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43555493"
---
# <a name="startupflags-enumeration"></a><span data-ttu-id="a062f-102">STARTUP_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a062f-102">STARTUP_FLAGS Enumeration</span></span>
<span data-ttu-id="a062f-103">Contiene valores que indican el comportamiento de inicio de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a062f-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="a062f-104">De manera predeterminada, la recolección de elementos no utilizados es no simultánea y solo se carga la biblioteca de clases base en el área neutral con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="a062f-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a062f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a062f-105">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="a062f-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="a062f-106">Members</span></span>  
  
|<span data-ttu-id="a062f-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="a062f-107">Member</span></span>|<span data-ttu-id="a062f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a062f-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="a062f-109">Especifica que se debería utilizar la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="a062f-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="a062f-110">Si el llamador solicita la compilación para servidor y la recolección de elementos no utilizados simultánea en un equipo con un solo procesador, se ejecuta, en su lugar, la versión para estación de trabajo y la recolección no simultánea de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a062f-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="a062f-111">**Nota:** no se admite la colección de elementos no utilizados simultánea en aplicaciones que se ejecutan WOW64 x86 emulador en sistemas de 64 bits que implementan la arquitectura Intel Itanium (denominada anteriormente IA-64).</span><span class="sxs-lookup"><span data-stu-id="a062f-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="a062f-112">Para obtener más información sobre el uso de WOW64 en sistemas Windows de 64 bits, consulte [aplicaciones de la ejecución de 32 bits](/windows/desktop/WinProg64/running-32-bit-applications).</span><span class="sxs-lookup"><span data-stu-id="a062f-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="a062f-113">Especifica que se producirá la optimización del cargador.</span><span class="sxs-lookup"><span data-stu-id="a062f-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="a062f-114">Especifica que ningún ensamblado se carga como neutral con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="a062f-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="a062f-115">Especifica que todos los ensamblados se cargan como neutrales con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="a062f-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="a062f-116">Especifica que todos los ensamblados de nombre seguro se cargan como neutrales con respecto al dominio.</span><span class="sxs-lookup"><span data-stu-id="a062f-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="a062f-117">Especifica que la directiva de versión de CLR no se aplicará a la versión pasada.</span><span class="sxs-lookup"><span data-stu-id="a062f-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="a062f-118">Se cargará la versión exacta especificada de CLR.</span><span class="sxs-lookup"><span data-stu-id="a062f-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="a062f-119">El proceso intermedio ("shim") no evalúa directivas para determinar la última versión compatible.</span><span class="sxs-lookup"><span data-stu-id="a062f-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="a062f-120">Especifica que se establecerá el motor en tiempo de ejecución preferido, pero en realidad no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="a062f-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="a062f-121">Especifica que se usará la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="a062f-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="a062f-122">Especifica que la recolección de elementos no utilizados mantendrá la dirección virtual usada.</span><span class="sxs-lookup"><span data-stu-id="a062f-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="a062f-123">Especifica que no se permitirá combinar una interfaz de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="a062f-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="a062f-124">Especifica que la suplantación no debería fluir de forma predeterminada por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="a062f-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="a062f-125">Especifica que no se debería confirmar la pila de subprocesos completa cuando el subproceso inicia el funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="a062f-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="a062f-126">Especifica que las suplantaciones administradas y las suplantaciones logradas a través de la invocación de plataforma fluirán por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="a062f-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="a062f-127">De forma predeterminada, solo las suplantaciones administradas fluirán por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="a062f-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="a062f-128">Especifica que la recolección de elementos no utilizados usará el espacio menos confirmado cuando quede poca memoria del sistema.</span><span class="sxs-lookup"><span data-stu-id="a062f-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="a062f-129">Consulte `gcTrimCommitOnLowMemory` en [optimización de hospedaje Web compartido](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="a062f-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="a062f-130">Especifica que el seguimiento de eventos para Windows (ETW) está habilitado para los eventos de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a062f-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="a062f-131">Comenzando con Windows Vista, el seguimiento de eventos siempre está habilitado, por lo que esta marca no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="a062f-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="a062f-132">Consulte [controlar el registro de .NET Framework](../../../../docs/framework/performance/controlling-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a062f-132">See [Controlling .NET Framework Logging](../../../../docs/framework/performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="a062f-133">Especifica que la supervisión de recursos de dominio de aplicación está habilitada.</span><span class="sxs-lookup"><span data-stu-id="a062f-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="a062f-134">Consulte la <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> propiedad y [ \<appDomainResourceMonitoring > elemento](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span><span class="sxs-lookup"><span data-stu-id="a062f-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a062f-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a062f-135">Requirements</span></span>  
 <span data-ttu-id="a062f-136">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a062f-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a062f-137">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a062f-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a062f-138">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a062f-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a062f-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a062f-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a062f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a062f-140">See Also</span></span>  
 [<span data-ttu-id="a062f-141">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="a062f-141">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
