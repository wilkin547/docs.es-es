---
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 4a65b76f384cdad68cba75af524dbe672c309624
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976491"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="70449-102">Método ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="70449-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="70449-103">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="70449-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70449-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70449-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70449-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70449-105">Parameters</span></span>  
 <span data-ttu-id="70449-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="70449-106">cThreadIDs</span></span>  
 <span data-ttu-id="70449-107">[in] Número máximo de subprocesos cuyos identificadores se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="70449-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="70449-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="70449-108">pcThreadIds</span></span>  
 <span data-ttu-id="70449-109">[out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="70449-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="70449-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="70449-110">pThreadIDs</span></span>  
 <span data-ttu-id="70449-111">Matriz de identificadores de subproceso.</span><span class="sxs-lookup"><span data-stu-id="70449-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70449-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70449-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70449-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="70449-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70449-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70449-114">Requirements</span></span>  
 <span data-ttu-id="70449-115">**Plataformas:** Consulte [requisitos del sistema](../../get-started/system-requirements.md). **Encabezado:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="70449-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70449-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70449-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70449-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70449-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70449-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70449-118">See also</span></span>

- [<span data-ttu-id="70449-119">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="70449-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="70449-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="70449-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
