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
ms.openlocfilehash: 226b386c7a38c9a0b28b3bcc0420d14f6f4f4e7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678439"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="aa320-102">ICorDebugThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="aa320-102">ICorDebugThreadEnum::Next Method</span></span>

<span data-ttu-id="aa320-103">Obtiene el número de instancias de ICorDebugThread especificadas de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="aa320-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa320-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa320-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa320-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa320-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="aa320-106">de El número de `ICorDebugThread` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="aa320-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="aa320-107">enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugThread` objeto que representa un subproceso.</span><span class="sxs-lookup"><span data-stu-id="aa320-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="aa320-108">enuncia Puntero al número de `ICorDebugThread` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="aa320-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="aa320-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="aa320-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa320-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa320-110">Requirements</span></span>  

 <span data-ttu-id="aa320-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa320-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa320-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa320-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa320-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa320-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa320-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa320-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
