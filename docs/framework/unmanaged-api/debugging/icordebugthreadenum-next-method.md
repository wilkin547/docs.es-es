---
description: 'Más información sobre: ICorDebugThreadEnum (:: Next (método)'
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
ms.openlocfilehash: 2cfb651d65eaf0f5797444ea1bec587cebdde2f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658430"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="b528b-103">ICorDebugThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="b528b-103">ICorDebugThreadEnum::Next Method</span></span>

<span data-ttu-id="b528b-104">Obtiene el número de instancias de ICorDebugThread especificadas de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="b528b-104">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b528b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b528b-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b528b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b528b-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="b528b-107">de El número de `ICorDebugThread` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="b528b-107">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="b528b-108">enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugThread` objeto que representa un subproceso.</span><span class="sxs-lookup"><span data-stu-id="b528b-108">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b528b-109">enuncia Puntero al número de `ICorDebugThread` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="b528b-109">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="b528b-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="b528b-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b528b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b528b-111">Requirements</span></span>  

 <span data-ttu-id="b528b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b528b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b528b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b528b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b528b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b528b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b528b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b528b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
