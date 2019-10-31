---
title: 'ICorDebugVariableSymbol:: Getslotindex ((método)'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: a7a7ecf7d3e3d0d2125b03d3604c44138a2be0cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120973"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="f29f1-102">ICorDebugVariableSymbol:: Getslotindex ((método)</span><span class="sxs-lookup"><span data-stu-id="f29f1-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="f29f1-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="f29f1-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f29f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f29f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f29f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f29f1-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="f29f1-106">[out] Puntero al índice de ranura de la variable local.</span><span class="sxs-lookup"><span data-stu-id="f29f1-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f29f1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f29f1-107">Return Value</span></span>  
 <span data-ttu-id="f29f1-108">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f29f1-108">`S_OK` if successful.</span></span> <span data-ttu-id="f29f1-109">`E_FAIL` si la variable es un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="f29f1-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f29f1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f29f1-110">Remarks</span></span>  
 <span data-ttu-id="f29f1-111">El índice de ranura administrado de una variable local puede utilizarse para recuperar información de metadatos de la variable</span><span class="sxs-lookup"><span data-stu-id="f29f1-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f29f1-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f29f1-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f29f1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f29f1-113">Requirements</span></span>  
 <span data-ttu-id="f29f1-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f29f1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f29f1-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f29f1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f29f1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f29f1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f29f1-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f29f1-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29f1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f29f1-118">See also</span></span>

- [<span data-ttu-id="f29f1-119">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f29f1-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="f29f1-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f29f1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
