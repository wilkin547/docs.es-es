---
description: 'Más información sobre: ICorProfilerCallback10:: EventPipeProviderCreated (método)'
title: 'ICorProfilerCallback10:: EventPipeProviderCreated (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10.EventPipeProviderCreated
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 6ce96bf301f1c559923df64edd9dd214c28db918
ms.sourcegitcommit: 44af69720863bd09bd7a4509bf1ec119466ba6e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "106231315"
---
# <a name="icorprofilercallback10eventpipeprovidercreated-method"></a><span data-ttu-id="accc9-103">ICorProfilerCallback10:: EventPipeProviderCreated (método)</span><span class="sxs-lookup"><span data-stu-id="accc9-103">ICorProfilerCallback10::EventPipeProviderCreated Method</span></span>

<span data-ttu-id="accc9-104">Notifica al generador de perfiles cada vez que se crea un proveedor de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="accc9-104">Notifies the profiler whenever an EventPipe provider is created.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="accc9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="accc9-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeProviderCreated([in] EVENTPIPE_PROVIDER provider);
```  
  
## <a name="parameters"></a><span data-ttu-id="accc9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="accc9-106">Parameters</span></span>

<span data-ttu-id="accc9-107">`provider` de Proveedor que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="accc9-107">`provider` [in] The provider that was created.</span></span>

## <a name="requirements"></a><span data-ttu-id="accc9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="accc9-108">Requirements</span></span>  

<span data-ttu-id="accc9-109">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="accc9-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="accc9-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="accc9-110">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="accc9-111">**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accc9-111">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="accc9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="accc9-112">See also</span></span>

- [<span data-ttu-id="accc9-113">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="accc9-113">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="accc9-114">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="accc9-114">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="accc9-115">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="accc9-115">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="accc9-116">ICorProfilerInfo12. EventPipeAddProviderToSession, método</span><span class="sxs-lookup"><span data-stu-id="accc9-116">ICorProfilerInfo12.EventPipeAddProviderToSession Method</span></span>](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
