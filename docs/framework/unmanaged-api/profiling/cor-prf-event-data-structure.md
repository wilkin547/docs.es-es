---
description: 'Más información acerca de: enumeración COR_PRF_EVENT_DATA'
title: Enumeración COR_PRF_EVENT_DATA
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENT_DATA
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 477f36476deb9c0d74e263703e36b134c91b5327
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805575"
---
# <a name="cor_prf_event_data-enumeration"></a><span data-ttu-id="f77db-103">Enumeración COR_PRF_EVENT_DATA</span><span class="sxs-lookup"><span data-stu-id="f77db-103">COR_PRF_EVENT_DATA Enumeration</span></span>

<span data-ttu-id="f77db-104">Describe los datos de evento para un evento EventPipe que se está escribiendo.</span><span class="sxs-lookup"><span data-stu-id="f77db-104">Describes the event data for an EventPipe event being written.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f77db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f77db-105">Syntax</span></span>  
  
```cpp  
typedef struct
{
    UINT64 ptr;
    UINT32 size;
    UINT32 reserved;
} COR_PRF_EVENT_DATA;
```  
  
## <a name="members"></a><span data-ttu-id="f77db-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="f77db-106">Members</span></span>  
  
|<span data-ttu-id="f77db-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f77db-107">Member</span></span>|<span data-ttu-id="f77db-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f77db-108">Description</span></span>|  
|------------|-----------------|  
|`ptr`|<span data-ttu-id="f77db-109">Puntero a los datos.</span><span class="sxs-lookup"><span data-stu-id="f77db-109">A pointer to the data.</span></span>|  
|`size`|<span data-ttu-id="f77db-110">Tamaño de los datos a los que apunta `ptr` .</span><span class="sxs-lookup"><span data-stu-id="f77db-110">The size of the data pointed to by `ptr`.</span></span>|  
|`reserved`|<span data-ttu-id="f77db-111">Un campo específico de implementación reservado.</span><span class="sxs-lookup"><span data-stu-id="f77db-111">An reserved implementation specific field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f77db-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f77db-112">Remarks</span></span>  

 <span data-ttu-id="f77db-113">El `COR_PRF_EVENT_DATA` método [ICorProfilerInfo12:: EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md) usa la estructura para providate la carga de datos para el evento que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="f77db-113">The `COR_PRF_EVENT_DATA` structure is used by the [ICorProfilerInfo12::EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md) method to providate the data payload for the event being written.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f77db-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f77db-114">Requirements</span></span>  

<span data-ttu-id="f77db-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="f77db-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="f77db-116">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f77db-116">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f77db-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f77db-117">See also</span></span>

- [<span data-ttu-id="f77db-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f77db-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="f77db-119">ICorProfilerInfo12::EventPipeWriteEvent</span><span class="sxs-lookup"><span data-stu-id="f77db-119">ICorProfilerInfo12::EventPipeWriteEvent</span></span>](icorprofilerinfo12-eventpipewriteevent-method.md)
