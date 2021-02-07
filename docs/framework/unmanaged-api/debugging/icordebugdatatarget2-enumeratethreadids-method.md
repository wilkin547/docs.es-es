---
description: 'Más información sobre: método icordebugdatatarget2:: EnumerateThreadIDs (método)'
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 5bbda67e6c6de81e9de566a68f772f324d79b92f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710561"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="bd664-103">Método ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="bd664-103">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>

<span data-ttu-id="bd664-104">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="bd664-104">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd664-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd664-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd664-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd664-106">Parameters</span></span>  

 <span data-ttu-id="bd664-107">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="bd664-107">cThreadIDs</span></span>  
 <span data-ttu-id="bd664-108">[in] Número máximo de subprocesos cuyos identificadores se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="bd664-108">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="bd664-109">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="bd664-109">pcThreadIds</span></span>  
 <span data-ttu-id="bd664-110">[out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="bd664-110">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="bd664-111">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="bd664-111">pThreadIDs</span></span>  
 <span data-ttu-id="bd664-112">Matriz de identificadores de subproceso.</span><span class="sxs-lookup"><span data-stu-id="bd664-112">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd664-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bd664-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd664-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bd664-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd664-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd664-115">Requirements</span></span>  

 <span data-ttu-id="bd664-116">**Plataformas:** Consulte [requisitos del sistema](../../get-started/system-requirements.md). **Encabezado:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="bd664-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd664-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd664-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd664-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd664-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd664-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd664-119">See also</span></span>

- [<span data-ttu-id="bd664-120">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="bd664-120">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="bd664-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="bd664-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
