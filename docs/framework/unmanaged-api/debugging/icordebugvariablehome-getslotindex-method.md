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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093759"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="6a0e9-102">Método ICorDebugVariableHome::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="6a0e9-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="6a0e9-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="6a0e9-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a0e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a0e9-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a0e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a0e9-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="6a0e9-106">[out] Un puntero en el índice de ranura de una variable local.</span><span class="sxs-lookup"><span data-stu-id="6a0e9-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a0e9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a0e9-107">Return Value</span></span>  
 <span data-ttu-id="6a0e9-108">El método devuelve los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="6a0e9-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="6a0e9-109">Valor</span><span class="sxs-lookup"><span data-stu-id="6a0e9-109">Value</span></span>|<span data-ttu-id="6a0e9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a0e9-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="6a0e9-111">La llamada al método devuelve un valor de índice de ranura en `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="6a0e9-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="6a0e9-112">Actual [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instancia representa un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="6a0e9-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a0e9-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a0e9-113">Remarks</span></span>  
 <span data-ttu-id="6a0e9-114">El índice de ranura puede usarse para recuperar los metadatos de esta variable local.</span><span class="sxs-lookup"><span data-stu-id="6a0e9-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a0e9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a0e9-115">Requirements</span></span>  
 <span data-ttu-id="6a0e9-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a0e9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a0e9-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a0e9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a0e9-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a0e9-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6a0e9-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6a0e9-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a0e9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a0e9-120">See also</span></span>

- [<span data-ttu-id="6a0e9-121">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="6a0e9-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
