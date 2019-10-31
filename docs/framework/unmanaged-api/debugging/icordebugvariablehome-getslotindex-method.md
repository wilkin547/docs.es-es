---
title: 'ICorDebugVariableHome:: Getslotindex ((método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: dfc2e91599e7f05d90d56af07b71313e9eecaa51
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121055"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="b5cf7-102">ICorDebugVariableHome:: Getslotindex ((método)</span><span class="sxs-lookup"><span data-stu-id="b5cf7-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="b5cf7-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="b5cf7-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5cf7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5cf7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5cf7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5cf7-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="b5cf7-106">enuncia Puntero al índice de ranura de una variable local.</span><span class="sxs-lookup"><span data-stu-id="b5cf7-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5cf7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b5cf7-107">Return Value</span></span>  
 <span data-ttu-id="b5cf7-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="b5cf7-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="b5cf7-109">Valor</span><span class="sxs-lookup"><span data-stu-id="b5cf7-109">Value</span></span>|<span data-ttu-id="b5cf7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5cf7-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="b5cf7-111">La llamada al método devolvió un valor de índice de ranura en `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="b5cf7-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="b5cf7-112">La instancia de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) actual representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="b5cf7-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5cf7-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5cf7-113">Remarks</span></span>  
 <span data-ttu-id="b5cf7-114">Se puede usar el índice de ranura para recuperar los metadatos de esta variable local.</span><span class="sxs-lookup"><span data-stu-id="b5cf7-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5cf7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5cf7-115">Requirements</span></span>  
 <span data-ttu-id="b5cf7-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5cf7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5cf7-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5cf7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5cf7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5cf7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5cf7-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5cf7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5cf7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5cf7-120">See also</span></span>

- [<span data-ttu-id="b5cf7-121">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5cf7-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
