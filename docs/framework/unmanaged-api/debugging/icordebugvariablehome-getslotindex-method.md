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
ms.openlocfilehash: 0bffd2db0a4a061a8629ff50a03a319feec6d836
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396552"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="90a37-102">ICorDebugVariableHome:: Getslotindex ((método)</span><span class="sxs-lookup"><span data-stu-id="90a37-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="90a37-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="90a37-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a37-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90a37-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90a37-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90a37-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="90a37-106">enuncia Puntero al índice de ranura de una variable local.</span><span class="sxs-lookup"><span data-stu-id="90a37-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90a37-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="90a37-107">Return Value</span></span>  
 <span data-ttu-id="90a37-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="90a37-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="90a37-109">Valor</span><span class="sxs-lookup"><span data-stu-id="90a37-109">Value</span></span>|<span data-ttu-id="90a37-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="90a37-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="90a37-111">La llamada al método devolvió un valor de índice de ranura en `pSlotIndex` .</span><span class="sxs-lookup"><span data-stu-id="90a37-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="90a37-112">La instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) actual representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="90a37-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90a37-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90a37-113">Remarks</span></span>  
 <span data-ttu-id="90a37-114">Se puede usar el índice de ranura para recuperar los metadatos de esta variable local.</span><span class="sxs-lookup"><span data-stu-id="90a37-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a37-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90a37-115">Requirements</span></span>  
 <span data-ttu-id="90a37-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90a37-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90a37-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90a37-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90a37-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90a37-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90a37-119">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90a37-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a37-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="90a37-120">See also</span></span>

- [<span data-ttu-id="90a37-121">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="90a37-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
