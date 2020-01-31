---
title: ICorDebugVariableSymbol::GetSlotIndex (método)
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3510daffb55bdb22aa5f835bf27157e7c8428509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790893"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="cf693-102">ICorDebugVariableSymbol::GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="cf693-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="cf693-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="cf693-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf693-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf693-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf693-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="cf693-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="cf693-106">[out] Puntero al índice de ranura de la variable local.</span><span class="sxs-lookup"><span data-stu-id="cf693-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf693-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf693-107">Return Value</span></span>  
 <span data-ttu-id="cf693-108">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf693-108">`S_OK` if successful.</span></span> <span data-ttu-id="cf693-109">`E_FAIL` si la variable es un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="cf693-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf693-110">Notas</span><span class="sxs-lookup"><span data-stu-id="cf693-110">Remarks</span></span>  
 <span data-ttu-id="cf693-111">El índice de ranura administrado de una variable local puede utilizarse para recuperar información de metadatos de la variable</span><span class="sxs-lookup"><span data-stu-id="cf693-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf693-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cf693-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf693-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="cf693-113">Requirements</span></span>  
 <span data-ttu-id="cf693-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf693-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf693-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf693-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf693-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf693-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf693-117">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf693-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf693-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf693-118">See also</span></span>

- [<span data-ttu-id="cf693-119">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf693-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="cf693-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cf693-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
