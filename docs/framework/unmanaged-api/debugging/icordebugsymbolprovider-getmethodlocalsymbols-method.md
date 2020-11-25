---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols (método)
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: c5a21436c939ddfca0219618efe64d9e0e40aef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730856"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="d3596-102">ICorDebugSymbolProvider::GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="d3596-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>

<span data-ttu-id="d3596-103">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="d3596-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3596-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3596-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3596-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3596-105">Parameters</span></span>  

 `nativeRVA`  
 <span data-ttu-id="d3596-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="d3596-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="d3596-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="d3596-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="d3596-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="d3596-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="d3596-109">enuncia Puntero a una matriz [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="d3596-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3596-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3596-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3596-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d3596-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3596-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3596-112">Requirements</span></span>  

 <span data-ttu-id="d3596-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3596-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3596-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3596-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3596-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3596-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3596-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3596-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3596-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3596-117">See also</span></span>

- [<span data-ttu-id="d3596-118">Método GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="d3596-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="d3596-119">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="d3596-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="d3596-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d3596-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
