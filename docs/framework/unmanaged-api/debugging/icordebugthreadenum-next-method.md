---
title: ICorDebugThreadEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 0c455706b0d644d2444e9fbdf49c5a5d4f5295a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122387"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="7ecd6-102">ICorDebugThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="7ecd6-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="7ecd6-103">Obtiene el número de instancias de ICorDebugThread especificadas de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="7ecd6-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ecd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ecd6-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ecd6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ecd6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7ecd6-106">de Número de instancias de `ICorDebugThread` que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="7ecd6-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="7ecd6-107">enuncia Matriz de punteros, cada uno de los cuales señala a un objeto `ICorDebugThread` que representa un subproceso.</span><span class="sxs-lookup"><span data-stu-id="7ecd6-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7ecd6-108">enuncia Puntero al número de instancias de `ICorDebugThread` devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="7ecd6-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="7ecd6-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="7ecd6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ecd6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ecd6-110">Requirements</span></span>  
 <span data-ttu-id="7ecd6-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ecd6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ecd6-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ecd6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ecd6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ecd6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ecd6-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ecd6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
