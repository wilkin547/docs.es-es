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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e94034fcdcd8d86f34c61af30a7729a80c913fac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767339"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="23abb-102">ICorDebugProcess5::GetGCHeapInformation (Método)</span><span class="sxs-lookup"><span data-stu-id="23abb-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="23abb-103">Proporciona información general sobre el montón de elementos no utilizados, incluido si está actualmente enumerable.</span><span class="sxs-lookup"><span data-stu-id="23abb-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23abb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23abb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23abb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23abb-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="23abb-106">[out] Un puntero a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) valor que proporciona información general sobre el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="23abb-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23abb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23abb-107">Remarks</span></span>  
 <span data-ttu-id="23abb-108">El `ICorDebugProcess5::GetGCHeapInformation` método debe llamarse antes de enumerar el montón o regiones individuales de montón para asegurarse de que la recolección de elementos de las estructuras en el proceso actualmente son válidas.</span><span class="sxs-lookup"><span data-stu-id="23abb-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="23abb-109">No se desplazará el montón de elementos no utilizados mientras una colección está en curso.</span><span class="sxs-lookup"><span data-stu-id="23abb-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="23abb-110">En caso contrario, la enumeración puede capturar las estructuras de la colección de elementos no utilizados que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="23abb-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23abb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23abb-111">Requirements</span></span>  
 <span data-ttu-id="23abb-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23abb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23abb-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23abb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23abb-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23abb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23abb-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23abb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23abb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="23abb-116">See also</span></span>

- [<span data-ttu-id="23abb-117">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23abb-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="23abb-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="23abb-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
