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
ms.openlocfilehash: 703f159c5bc6b73dcd0e770bdeb61f676aae034c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792371"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="305d9-102">ICorDebugProcess5::GetGCHeapInformation (Método)</span><span class="sxs-lookup"><span data-stu-id="305d9-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="305d9-103">Proporciona información general sobre el montón de recolección de elementos no utilizados, incluido si es Enumerable en este momento.</span><span class="sxs-lookup"><span data-stu-id="305d9-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="305d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="305d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="305d9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="305d9-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="305d9-106">enuncia Puntero a un valor de [COR_HEAPINFO](cor-heapinfo-structure.md) que proporciona información general sobre el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="305d9-106">[out] A pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="305d9-107">Notas</span><span class="sxs-lookup"><span data-stu-id="305d9-107">Remarks</span></span>  
 <span data-ttu-id="305d9-108">Se debe llamar al método `ICorDebugProcess5::GetGCHeapInformation` antes de enumerar las regiones del montón o del montón individual para asegurarse de que las estructuras de recolección de elementos no utilizados del proceso son válidas actualmente.</span><span class="sxs-lookup"><span data-stu-id="305d9-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="305d9-109">No se puede recorrer el montón de recolección de elementos no utilizados mientras una colección está en curso.</span><span class="sxs-lookup"><span data-stu-id="305d9-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="305d9-110">De lo contrario, la enumeración puede capturar estructuras de recolección de elementos no utilizados que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="305d9-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="305d9-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="305d9-111">Requirements</span></span>  
 <span data-ttu-id="305d9-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="305d9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="305d9-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="305d9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="305d9-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="305d9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="305d9-115">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="305d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305d9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="305d9-116">See also</span></span>

- [<span data-ttu-id="305d9-117">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="305d9-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="305d9-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="305d9-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
