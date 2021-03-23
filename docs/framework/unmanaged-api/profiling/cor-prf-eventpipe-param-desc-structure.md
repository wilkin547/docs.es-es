---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_PARAM_DESC'
title: Enumeración COR_PRF_EVENTPIPE_PARAM_DESC
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_DESC
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: b23897580092cc9f3f887a21e86f7111fecd9f19
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805797"
---
# <a name="cor_prf_eventpipe_param_desc-enumeration"></a><span data-ttu-id="be273-103">Enumeración COR_PRF_EVENTPIPE_PARAM_DESC</span><span class="sxs-lookup"><span data-stu-id="be273-103">COR_PRF_EVENTPIPE_PARAM_DESC Enumeration</span></span>

<span data-ttu-id="be273-104">Describe el nombre y el tipo de parámetro de un evento EventPipe.</span><span class="sxs-lookup"><span data-stu-id="be273-104">Describes the parameter name and type for an EventPipe event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="be273-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be273-105">Syntax</span></span>  
  
```cpp  
typedef struct
{
    UINT32       type;
    UINT32       elementType;
    const WCHAR *name;
} COR_PRF_EVENTPIPE_PARAM_DESC;
```  
  
## <a name="members"></a><span data-ttu-id="be273-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="be273-106">Members</span></span>  
  
|<span data-ttu-id="be273-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="be273-107">Member</span></span>|<span data-ttu-id="be273-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="be273-108">Description</span></span>|  
|------------|-----------------|  
|`type`|<span data-ttu-id="be273-109">Tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="be273-109">The type of the parameter.</span></span>|  
|`elementType`|<span data-ttu-id="be273-110">El tipo de elemento si este parámetro es un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="be273-110">The element type if this parameter is an array type.</span></span>|  
|`name`|<span data-ttu-id="be273-111">Una cadena de caracteres anchos que contiene el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="be273-111">A wide character string containing the name of the parameter.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be273-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="be273-112">Remarks</span></span>  

 <span data-ttu-id="be273-113">El `COR_PRF_EVENTPIPE_PARAM_DESC` método [ICorProfilerInfo12:: EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) usa la estructura para definir los tipos de parámetro del evento que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="be273-113">The `COR_PRF_EVENTPIPE_PARAM_DESC` structure is used by the [ICorProfilerInfo12::EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md) method to define the parameter types of the event being defined.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="be273-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be273-114">Requirements</span></span>  

<span data-ttu-id="be273-115">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="be273-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="be273-116">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be273-116">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="be273-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be273-117">See also</span></span>

- [<span data-ttu-id="be273-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="be273-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="be273-119">ICorProfilerInfo12::EventPipeDefineEvent</span><span class="sxs-lookup"><span data-stu-id="be273-119">ICorProfilerInfo12::EventPipeDefineEvent</span></span>](icorprofilerinfo12-eventpipedefineevent-method.md)
