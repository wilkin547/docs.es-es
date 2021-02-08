---
description: 'Más información sobre: ICorDebugVariableSymbol:: Getslotindex ((método)'
title: ICorDebugVariableSymbol::GetSlotIndex (método)
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3b5cba06a5e80ffa323d2e6521e9ec4666f6f5f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790560"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="f9ede-103">ICorDebugVariableSymbol::GetSlotIndex (método)</span><span class="sxs-lookup"><span data-stu-id="f9ede-103">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>

<span data-ttu-id="f9ede-104">Obtiene el índice de ranura administrado de una variable local.</span><span class="sxs-lookup"><span data-stu-id="f9ede-104">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9ede-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9ede-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9ede-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9ede-106">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="f9ede-107">[out] Puntero al índice de ranura de la variable local.</span><span class="sxs-lookup"><span data-stu-id="f9ede-107">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9ede-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f9ede-108">Return Value</span></span>  

 <span data-ttu-id="f9ede-109">`S_OK` si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f9ede-109">`S_OK` if successful.</span></span> <span data-ttu-id="f9ede-110">`E_FAIL` si la variable es un argumento de función.</span><span class="sxs-lookup"><span data-stu-id="f9ede-110">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9ede-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f9ede-111">Remarks</span></span>  

 <span data-ttu-id="f9ede-112">El índice de ranura administrado de una variable local puede utilizarse para recuperar información de metadatos de la variable</span><span class="sxs-lookup"><span data-stu-id="f9ede-112">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9ede-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f9ede-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9ede-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9ede-114">Requirements</span></span>  

 <span data-ttu-id="f9ede-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9ede-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9ede-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9ede-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9ede-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9ede-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9ede-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9ede-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ede-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9ede-119">See also</span></span>

- [<span data-ttu-id="f9ede-120">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f9ede-120">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="f9ede-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f9ede-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
