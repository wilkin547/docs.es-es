---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_PROVIDER_CONFIG'
title: Enumeración COR_PRF_EVENTPIPE_PROVIDER_CONFIG
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PROVIDER_CONFIG
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 2a7a5e720e9468b44e6504d24a3b9ad836e13693
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805849"
---
# <a name="cor_prf_eventpipe_provider_config-enumeration"></a><span data-ttu-id="65aa7-103">Enumeración COR_PRF_EVENTPIPE_PROVIDER_CONFIG</span><span class="sxs-lookup"><span data-stu-id="65aa7-103">COR_PRF_EVENTPIPE_PROVIDER_CONFIG Enumeration</span></span>

<span data-ttu-id="65aa7-104">Describe los campos necesarios para configurar un proveedor de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="65aa7-104">Describes the fields necessary to configure an EventPipe provider.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="65aa7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65aa7-105">Syntax</span></span>  
  
```cpp  
typedef struct
{
    const WCHAR* providerName;
    UINT64       keywords;
    UINT32       loggingLevel;
    const WCHAR* filterData;
} COR_PRF_EVENTPIPE_PROVIDER_CONFIG;
```  
  
## <a name="members"></a><span data-ttu-id="65aa7-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="65aa7-106">Members</span></span>  
  
|<span data-ttu-id="65aa7-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="65aa7-107">Member</span></span>|<span data-ttu-id="65aa7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="65aa7-108">Description</span></span>|  
|------------|-----------------|  
|`providerName`|<span data-ttu-id="65aa7-109">Nombre del proveedor que se va a habilitar.</span><span class="sxs-lookup"><span data-stu-id="65aa7-109">The name of the provider to enable.</span></span>|  
|`keywords`|<span data-ttu-id="65aa7-110">Palabras clave que se van a habilitar en el proveedor.</span><span class="sxs-lookup"><span data-stu-id="65aa7-110">The keywords to enable on the provider.</span></span>|  
|`loggingLevel`|<span data-ttu-id="65aa7-111">Nivel que se va a habilitar en el proveedor.</span><span class="sxs-lookup"><span data-stu-id="65aa7-111">The level to enable on the provider.</span></span>|  
|`filterData`|<span data-ttu-id="65aa7-112">Una cadena de caracteres anchos que contiene el filterdata que se va a usar al habilitar el proveedor.</span><span class="sxs-lookup"><span data-stu-id="65aa7-112">A wide character string containing the filterdata to use when enabling the provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65aa7-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="65aa7-113">Remarks</span></span>  

 <span data-ttu-id="65aa7-114">El `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` método [ICorProfilerInfo12:: EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md) usa la estructura para indicar la configuración del proveedor que se va a agregar a la sesión.</span><span class="sxs-lookup"><span data-stu-id="65aa7-114">The `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` structure is used by the [ICorProfilerInfo12::EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md) method to indicate the configuration for the provider being added to the session.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="65aa7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65aa7-115">Requirements</span></span>  

<span data-ttu-id="65aa7-116">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="65aa7-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="65aa7-117">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65aa7-117">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65aa7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65aa7-118">See also</span></span>

- [<span data-ttu-id="65aa7-119">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="65aa7-119">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="65aa7-120">ICorProfilerInfo12::EventPipeAddProviderToSession</span><span class="sxs-lookup"><span data-stu-id="65aa7-120">ICorProfilerInfo12::EventPipeAddProviderToSession</span></span>](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
