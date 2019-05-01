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
ms.openlocfilehash: 50b682a7b3a4aadf7559120745265ef266cf2870
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948751"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="f7628-102">ICorDebugProcess5::GetGCHeapInformation (Método)</span><span class="sxs-lookup"><span data-stu-id="f7628-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="f7628-103">Proporciona información general sobre el montón de elementos no utilizados, incluido si está actualmente enumerable.</span><span class="sxs-lookup"><span data-stu-id="f7628-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7628-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7628-104">Syntax</span></span>  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7628-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7628-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="f7628-106">[out] Un puntero a un [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) valor que proporciona información general sobre el montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f7628-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7628-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7628-107">Remarks</span></span>  
 <span data-ttu-id="f7628-108">El `ICorDebugProcess5::GetGCHeapInformation` método debe llamarse antes de enumerar el montón o regiones individuales de montón para asegurarse de que la recolección de elementos de las estructuras en el proceso actualmente son válidas.</span><span class="sxs-lookup"><span data-stu-id="f7628-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="f7628-109">No se desplazará el montón de elementos no utilizados mientras una colección está en curso.</span><span class="sxs-lookup"><span data-stu-id="f7628-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="f7628-110">En caso contrario, la enumeración puede capturar las estructuras de la colección de elementos no utilizados que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="f7628-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7628-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7628-111">Requirements</span></span>  
 <span data-ttu-id="f7628-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7628-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7628-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7628-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7628-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7628-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7628-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7628-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7628-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7628-116">See also</span></span>

- [<span data-ttu-id="f7628-117">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7628-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="f7628-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f7628-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
