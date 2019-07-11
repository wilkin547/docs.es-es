---
title: Método ICorDebugVariableHome::GetSlotIndex
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 199c3ba5d5b9588db4c665070b4dec6266cefc2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760347"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="63f7f-102">Método ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="63f7f-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="63f7f-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="63f7f-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f7f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63f7f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63f7f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63f7f-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="63f7f-106">[out] Un puntero en el índice de ranura de una variable local.</span><span class="sxs-lookup"><span data-stu-id="63f7f-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63f7f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63f7f-107">Return Value</span></span>  
 <span data-ttu-id="63f7f-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="63f7f-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="63f7f-109">Valor</span><span class="sxs-lookup"><span data-stu-id="63f7f-109">Value</span></span>|<span data-ttu-id="63f7f-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="63f7f-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="63f7f-111">La llamada al método devuelve un valor de índice de ranura en `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="63f7f-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="63f7f-112">Actual [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancia representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="63f7f-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63f7f-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63f7f-113">Remarks</span></span>  
 <span data-ttu-id="63f7f-114">El índice de ranura puede usarse para recuperar los metadatos de esta variable local.</span><span class="sxs-lookup"><span data-stu-id="63f7f-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f7f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63f7f-115">Requirements</span></span>  
 <span data-ttu-id="63f7f-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63f7f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f7f-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63f7f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63f7f-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63f7f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63f7f-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f7f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f7f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="63f7f-120">See also</span></span>

- [<span data-ttu-id="63f7f-121">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63f7f-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
