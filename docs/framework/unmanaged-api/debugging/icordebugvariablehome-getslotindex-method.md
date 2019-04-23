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
ms.openlocfilehash: b819f1f02870a8a85a531d7d341cbaf488a1ccd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093759"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="a64e6-102">Método ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="a64e6-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="a64e6-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="a64e6-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a64e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a64e6-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a64e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a64e6-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="a64e6-106">[out] Un puntero en el índice de ranura de una variable local.</span><span class="sxs-lookup"><span data-stu-id="a64e6-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a64e6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a64e6-107">Return Value</span></span>  
 <span data-ttu-id="a64e6-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="a64e6-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="a64e6-109">Valor</span><span class="sxs-lookup"><span data-stu-id="a64e6-109">Value</span></span>|<span data-ttu-id="a64e6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a64e6-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="a64e6-111">La llamada al método devuelve un valor de índice de ranura en `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="a64e6-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="a64e6-112">Actual [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancia representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="a64e6-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a64e6-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a64e6-113">Remarks</span></span>  
 <span data-ttu-id="a64e6-114">El índice de ranura puede usarse para recuperar los metadatos de esta variable local.</span><span class="sxs-lookup"><span data-stu-id="a64e6-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a64e6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a64e6-115">Requirements</span></span>  
 <span data-ttu-id="a64e6-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a64e6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a64e6-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a64e6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a64e6-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a64e6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a64e6-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a64e6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64e6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a64e6-120">See also</span></span>

- [<span data-ttu-id="a64e6-121">ICorDebugVariableHome (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a64e6-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
