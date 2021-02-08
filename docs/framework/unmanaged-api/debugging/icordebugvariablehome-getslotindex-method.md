---
description: 'Más información sobre: ICorDebugVariableHome:: Getslotindex ((método)'
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
ms.openlocfilehash: 7f6ee01c2bfcee4c78f8463a7cefac1f90a3295f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790651"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="49599-103">ICorDebugVariableHome:: Getslotindex ((método)</span><span class="sxs-lookup"><span data-stu-id="49599-103">ICorDebugVariableHome::GetSlotIndex Method</span></span>

<span data-ttu-id="49599-104">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="49599-104">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49599-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49599-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49599-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49599-106">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="49599-107">enuncia Puntero al índice de ranura de una variable local.</span><span class="sxs-lookup"><span data-stu-id="49599-107">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49599-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="49599-108">Return Value</span></span>  

 <span data-ttu-id="49599-109">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="49599-109">The method returns the following values.</span></span>  
  
|<span data-ttu-id="49599-110">Value</span><span class="sxs-lookup"><span data-stu-id="49599-110">Value</span></span>|<span data-ttu-id="49599-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="49599-111">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="49599-112">La llamada al método devolvió un valor de índice de ranura en `pSlotIndex` .</span><span class="sxs-lookup"><span data-stu-id="49599-112">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="49599-113">La instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) actual representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="49599-113">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49599-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="49599-114">Remarks</span></span>  

 <span data-ttu-id="49599-115">Se puede usar el índice de ranura para recuperar los metadatos de esta variable local.</span><span class="sxs-lookup"><span data-stu-id="49599-115">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49599-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49599-116">Requirements</span></span>  

 <span data-ttu-id="49599-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49599-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49599-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49599-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49599-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49599-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49599-120">**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49599-120">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49599-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="49599-121">See also</span></span>

- [<span data-ttu-id="49599-122">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="49599-122">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
