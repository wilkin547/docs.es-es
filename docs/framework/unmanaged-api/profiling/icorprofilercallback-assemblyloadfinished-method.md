---
title: ICorProfilerCallback::AssemblyLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: ce4a842bc71ff144e46efb0d6f7068dfca9d207d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500447"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="d5e81-102">ICorProfilerCallback::AssemblyLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="d5e81-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="d5e81-103">Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="d5e81-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e81-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5e81-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5e81-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5e81-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="d5e81-106">\[in] identifica el ensamblado que se cargó.</span><span class="sxs-lookup"><span data-stu-id="d5e81-106">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="d5e81-107">\[in] un valor HRESULT que indica si el ensamblado finalizó la carga correctamente.</span><span class="sxs-lookup"><span data-stu-id="d5e81-107">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5e81-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5e81-108">Remarks</span></span>  
 <span data-ttu-id="d5e81-109">El valor de `assemblyId` no es válido para una solicitud de información hasta que `AssemblyLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="d5e81-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="d5e81-110">Algunas partes de la carga del ensamblado podrían continuar después de la `AssemblyLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d5e81-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="d5e81-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="d5e81-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="d5e81-112">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga del ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d5e81-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5e81-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5e81-113">Requirements</span></span>  
 <span data-ttu-id="d5e81-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5e81-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e81-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5e81-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5e81-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5e81-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5e81-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e81-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e81-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="d5e81-118">See also</span></span>

- [<span data-ttu-id="d5e81-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5e81-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
