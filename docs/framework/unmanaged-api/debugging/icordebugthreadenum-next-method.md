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
ms.openlocfilehash: c025afac1b53b23636a6160a475704011999d434
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379043"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="5c6a6-102">ICorDebugThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="5c6a6-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="5c6a6-103">Obtiene el número de instancias de ICorDebugThread especificadas de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="5c6a6-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c6a6-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c6a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c6a6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5c6a6-106">de El número de `ICorDebugThread` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="5c6a6-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="5c6a6-107">enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugThread` objeto que representa un subproceso.</span><span class="sxs-lookup"><span data-stu-id="5c6a6-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5c6a6-108">enuncia Puntero al número de `ICorDebugThread` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="5c6a6-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="5c6a6-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="5c6a6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c6a6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c6a6-110">Requirements</span></span>  
 <span data-ttu-id="5c6a6-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c6a6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6a6-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c6a6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c6a6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c6a6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c6a6-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6a6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
