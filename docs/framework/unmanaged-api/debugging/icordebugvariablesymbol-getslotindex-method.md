---
title: ICorDebugVariableSymbol::GetSlotIndex (método)
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09b50af49f8379539773d2000a6c1f8222fee875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563839"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="3253b-102">ICorDebugVariableSymbol::GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="3253b-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="3253b-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="3253b-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3253b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3253b-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3253b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3253b-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="3253b-106">[out] Puntero al índice de ranura de la variable local.</span><span class="sxs-lookup"><span data-stu-id="3253b-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3253b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3253b-107">Return Value</span></span>  
 <span data-ttu-id="3253b-108">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="3253b-108">`S_OK` if successful.</span></span> <span data-ttu-id="3253b-109">`E_FAIL` si la variable es un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="3253b-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3253b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3253b-110">Remarks</span></span>  
 <span data-ttu-id="3253b-111">El índice de ranura administrado de una variable local puede utilizarse para recuperar información de metadatos de la variable</span><span class="sxs-lookup"><span data-stu-id="3253b-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3253b-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3253b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3253b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3253b-113">Requirements</span></span>  
 <span data-ttu-id="3253b-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3253b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3253b-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3253b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3253b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3253b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3253b-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3253b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3253b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3253b-118">See also</span></span>
- [<span data-ttu-id="3253b-119">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3253b-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="3253b-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3253b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
