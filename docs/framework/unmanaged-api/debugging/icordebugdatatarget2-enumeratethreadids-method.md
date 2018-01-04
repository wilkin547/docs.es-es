---
title: "Método ICorDebugDataTarget2::EnumerateThreadIDs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9030f7f8453de98f535cf8212e55c7daee94e8e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="9e8dd-102">Método ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="9e8dd-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="9e8dd-103">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="9e8dd-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e8dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e8dd-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e8dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e8dd-105">Parameters</span></span>  
 <span data-ttu-id="9e8dd-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="9e8dd-106">cThreadIDs</span></span>  
 <span data-ttu-id="9e8dd-107">[in] Número máximo de subprocesos cuyos identificadores se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="9e8dd-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="9e8dd-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="9e8dd-108">pcThreadIds</span></span>  
 <span data-ttu-id="9e8dd-109">[out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="9e8dd-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="9e8dd-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="9e8dd-110">pThreadIDs</span></span>  
 <span data-ttu-id="9e8dd-111">Matriz de identificadores de subproceso.</span><span class="sxs-lookup"><span data-stu-id="9e8dd-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e8dd-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e8dd-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e8dd-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9e8dd-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e8dd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e8dd-114">Requirements</span></span>  
 <span data-ttu-id="9e8dd-115">**Plataformas:** vea [requisitos de sistema de](../../../../docs/framework/get-started/system-requirements.md). **Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e8dd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e8dd-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e8dd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e8dd-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8dd-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8dd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e8dd-118">See Also</span></span>  
 [<span data-ttu-id="9e8dd-119">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e8dd-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="9e8dd-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9e8dd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
