---
title: "ICorDebugVariableHome::GetSlotIndex (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ff62b79fbbb0896941730797473209872e6bfc2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="1b9b7-102">ICorDebugVariableHome::GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="1b9b7-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="1b9b7-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b9b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b9b7-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b9b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b9b7-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="1b9b7-106">[out] Un puntero para el índice de ranura de una variable local.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b9b7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b9b7-107">Return Value</span></span>  
 <span data-ttu-id="1b9b7-108">El método devuelve los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="1b9b7-109">Valor</span><span class="sxs-lookup"><span data-stu-id="1b9b7-109">Value</span></span>|<span data-ttu-id="1b9b7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b9b7-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="1b9b7-111">La llamada al método devuelve un valor de índice de ranura en `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="1b9b7-112">Actual [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancia representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b9b7-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b9b7-113">Remarks</span></span>  
 <span data-ttu-id="1b9b7-114">El índice de ranura se puede utilizar para recuperar los metadatos de esta variable local.</span><span class="sxs-lookup"><span data-stu-id="1b9b7-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b9b7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b9b7-115">Requirements</span></span>  
 <span data-ttu-id="1b9b7-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b9b7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b9b7-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b9b7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b9b7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b9b7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b9b7-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b9b7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9b7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b9b7-120">See Also</span></span>  
 [<span data-ttu-id="1b9b7-121">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b9b7-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
