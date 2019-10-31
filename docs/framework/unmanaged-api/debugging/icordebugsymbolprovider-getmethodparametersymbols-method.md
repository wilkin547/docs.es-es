---
title: 'ICorDebugSymbolProvider:: Getmethodparametersymbols ((método)'
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 1f7da156e5a164dc753e2283bc7ab24d18983173
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138839"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="d07c5-102">ICorDebugSymbolProvider:: Getmethodparametersymbols ((método)</span><span class="sxs-lookup"><span data-stu-id="d07c5-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="d07c5-103">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="d07c5-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d07c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d07c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d07c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d07c5-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="d07c5-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="d07c5-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="d07c5-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="d07c5-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="d07c5-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="d07c5-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="d07c5-109">enuncia Puntero a una matriz [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="d07c5-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d07c5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d07c5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d07c5-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d07c5-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d07c5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d07c5-112">Requirements</span></span>  
 <span data-ttu-id="d07c5-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d07c5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d07c5-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d07c5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d07c5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d07c5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d07c5-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d07c5-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07c5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d07c5-117">See also</span></span>

- [<span data-ttu-id="d07c5-118">GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="d07c5-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="d07c5-119">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d07c5-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="d07c5-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d07c5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
