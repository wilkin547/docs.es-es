---
title: ICorDebugProcess5::GetGCHeapInformation (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 43054a71445193bae7a74e0ed6785cccd1d02dc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670997"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="1699f-102">ICorDebugProcess5::GetGCHeapInformation (Método)</span><span class="sxs-lookup"><span data-stu-id="1699f-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>

<span data-ttu-id="1699f-103">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es Enumerable en este momento.</span><span class="sxs-lookup"><span data-stu-id="1699f-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1699f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1699f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1699f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1699f-105">Parameters</span></span>  

 `pHeapInfo`  
 <span data-ttu-id="1699f-106">enuncia Puntero a un valor de [COR_HEAPINFO](cor-heapinfo-structure.md) que proporciona información general sobre el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1699f-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1699f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1699f-107">Remarks</span></span>  

 <span data-ttu-id="1699f-108">Se `ICorDebugProcess5::GetGCHeapInformation` debe llamar al método antes de enumerar las regiones del montón o del montón individual para asegurarse de que las estructuras de recolección de elementos no utilizados del proceso son válidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="1699f-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="1699f-109">No se puede recorrer el montón de recolección de elementos no utilizados mientras una colección está en curso.</span><span class="sxs-lookup"><span data-stu-id="1699f-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="1699f-110">De lo contrario, la enumeración puede capturar estructuras de recolección de elementos no utilizados que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="1699f-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1699f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1699f-111">Requirements</span></span>  

 <span data-ttu-id="1699f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1699f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1699f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1699f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1699f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1699f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1699f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1699f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1699f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1699f-116">See also</span></span>

- [<span data-ttu-id="1699f-117">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1699f-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="1699f-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1699f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
