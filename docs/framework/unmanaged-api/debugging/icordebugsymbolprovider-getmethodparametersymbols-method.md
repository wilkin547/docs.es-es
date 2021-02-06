---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getmethodparametersymbols ((método)'
title: ICorDebugSymbolProvider::GetMethodParameterSymbols (método)
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 6ca71c7427f89cf33c5710d26b56590dbea3d2e0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659756"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="26a84-103">ICorDebugSymbolProvider::GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="26a84-103">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>

<span data-ttu-id="26a84-104">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="26a84-104">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a84-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26a84-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26a84-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26a84-106">Parameters</span></span>  

 `nativeRVA`  
 <span data-ttu-id="26a84-107">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="26a84-107">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="26a84-108">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="26a84-108">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="26a84-109">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="26a84-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="26a84-110">enuncia Puntero a una matriz [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="26a84-110">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26a84-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="26a84-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26a84-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="26a84-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a84-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26a84-113">Requirements</span></span>  

 <span data-ttu-id="26a84-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a84-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a84-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26a84-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26a84-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26a84-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26a84-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26a84-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a84-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="26a84-118">See also</span></span>

- [<span data-ttu-id="26a84-119">Método GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="26a84-119">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="26a84-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="26a84-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="26a84-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="26a84-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
