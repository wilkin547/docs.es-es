---
title: Método ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 31a839076b34901ae1a8f3b43021f64f77629fc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713852"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="02a87-102">Método ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="02a87-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>

<span data-ttu-id="02a87-103">Devuelve una lista de identificadores de subprocesos activos.</span><span class="sxs-lookup"><span data-stu-id="02a87-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02a87-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02a87-105">Parameters</span></span>  

 <span data-ttu-id="02a87-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="02a87-106">cThreadIDs</span></span>  
 <span data-ttu-id="02a87-107">[in] Número máximo de subprocesos cuyos identificadores se pueden devolver.</span><span class="sxs-lookup"><span data-stu-id="02a87-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="02a87-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="02a87-108">pcThreadIds</span></span>  
 <span data-ttu-id="02a87-109">[out] Puntero a un `ULONG32` que indica el número real de identificadores de subproceso escritos en la matriz `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="02a87-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="02a87-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="02a87-110">pThreadIDs</span></span>  
 <span data-ttu-id="02a87-111">Matriz de identificadores de subproceso.</span><span class="sxs-lookup"><span data-stu-id="02a87-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02a87-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02a87-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02a87-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="02a87-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02a87-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02a87-114">Requirements</span></span>  

 <span data-ttu-id="02a87-115">**Plataformas:** Consulte [requisitos del sistema](../../get-started/system-requirements.md). **Encabezado:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="02a87-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02a87-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02a87-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02a87-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02a87-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a87-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02a87-118">See also</span></span>

- [<span data-ttu-id="02a87-119">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="02a87-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="02a87-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="02a87-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
