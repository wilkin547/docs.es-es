---
title: ICorDebugVariableSymbol::GetSlotIndex (método)
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 251a978e96ff396d0d9d9282ded7f8a25ae0ba0b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397092"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="63a3f-102">ICorDebugVariableSymbol::GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="63a3f-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="63a3f-103">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="63a3f-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63a3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63a3f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63a3f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63a3f-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="63a3f-106">[out] Puntero al índice de ranura de la variable local.</span><span class="sxs-lookup"><span data-stu-id="63a3f-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63a3f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63a3f-107">Return Value</span></span>  
 <span data-ttu-id="63a3f-108">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="63a3f-108">`S_OK` if successful.</span></span> <span data-ttu-id="63a3f-109">`E_FAIL` si la variable es un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="63a3f-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63a3f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63a3f-110">Remarks</span></span>  
 <span data-ttu-id="63a3f-111">El índice de ranura administrado de una variable local puede utilizarse para recuperar información de metadatos de la variable</span><span class="sxs-lookup"><span data-stu-id="63a3f-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63a3f-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="63a3f-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a3f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63a3f-113">Requirements</span></span>  
 <span data-ttu-id="63a3f-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63a3f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63a3f-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63a3f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63a3f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63a3f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63a3f-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63a3f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a3f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="63a3f-118">See also</span></span>

- [<span data-ttu-id="63a3f-119">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="63a3f-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="63a3f-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="63a3f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
