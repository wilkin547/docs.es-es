---
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: b4510e6858045281a2a663095972b84c40df3a22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122163"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="20dc8-102">Método ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="20dc8-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="20dc8-103">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="20dc8-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20dc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20dc8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20dc8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20dc8-105">Parameters</span></span>  
 <span data-ttu-id="20dc8-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="20dc8-106">cThreadIDs</span></span>  
 <span data-ttu-id="20dc8-107">[in] Número máximo de subprocesos cuyos identificadores se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="20dc8-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="20dc8-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="20dc8-108">pcThreadIds</span></span>  
 <span data-ttu-id="20dc8-109">[out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="20dc8-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="20dc8-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="20dc8-110">pThreadIDs</span></span>  
 <span data-ttu-id="20dc8-111">Matriz de identificadores de subproceso.</span><span class="sxs-lookup"><span data-stu-id="20dc8-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20dc8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20dc8-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20dc8-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="20dc8-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20dc8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20dc8-114">Requirements</span></span>  
 <span data-ttu-id="20dc8-115">**Plataformas:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md). **Encabezado:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="20dc8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20dc8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20dc8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20dc8-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20dc8-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20dc8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="20dc8-118">See also</span></span>

- [<span data-ttu-id="20dc8-119">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20dc8-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="20dc8-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="20dc8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
