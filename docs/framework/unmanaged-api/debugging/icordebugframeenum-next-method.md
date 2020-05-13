---
title: ICorDebugFrameEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: 4652e4b34d614ad3b7b852925fcc63309bdd1498
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209466"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="1cf07-102">ICorDebugFrameEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="1cf07-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="1cf07-103">Obtiene el número especificado de instancias de ICorDebugFrame, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="1cf07-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cf07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cf07-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cf07-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1cf07-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1cf07-106">de El número de `ICorDebugFrame` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="1cf07-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="1cf07-107">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="1cf07-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1cf07-108">enuncia Puntero al número de `ICorDebugFrame` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="1cf07-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="1cf07-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="1cf07-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cf07-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cf07-110">Requirements</span></span>  
 <span data-ttu-id="1cf07-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cf07-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cf07-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cf07-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cf07-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cf07-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cf07-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cf07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
