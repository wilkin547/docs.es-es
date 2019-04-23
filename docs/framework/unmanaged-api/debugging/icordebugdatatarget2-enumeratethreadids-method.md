---
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70b3b57b51faed51aa7d5a70a3b785e0f719321b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215851"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="f1541-102">Método ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f1541-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="f1541-103">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="f1541-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1541-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1541-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1541-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1541-105">Parameters</span></span>  
 <span data-ttu-id="f1541-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f1541-106">cThreadIDs</span></span>  
 <span data-ttu-id="f1541-107">[in] Número máximo de subprocesos cuyos identificadores se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="f1541-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="f1541-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="f1541-108">pcThreadIds</span></span>  
 <span data-ttu-id="f1541-109">[out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="f1541-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="f1541-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f1541-110">pThreadIDs</span></span>  
 <span data-ttu-id="f1541-111">Matriz de identificadores de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f1541-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1541-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1541-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1541-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f1541-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1541-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1541-114">Requirements</span></span>  
 <span data-ttu-id="f1541-115">**Plataformas:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md). **Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1541-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1541-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1541-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1541-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1541-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1541-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1541-118">See also</span></span>

- [<span data-ttu-id="f1541-119">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1541-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="f1541-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f1541-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
