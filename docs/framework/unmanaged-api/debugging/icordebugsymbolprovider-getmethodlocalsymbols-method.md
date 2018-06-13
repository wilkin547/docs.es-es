---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols (método)
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c590944c321050c9ecca330a2961a2a7b7f31e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420019"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="d6e1e-102">ICorDebugSymbolProvider::GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="d6e1e-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="d6e1e-103">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="d6e1e-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6e1e-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6e1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6e1e-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="d6e1e-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="d6e1e-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="d6e1e-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="d6e1e-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="d6e1e-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="d6e1e-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="d6e1e-109">[out] Un puntero a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matriz que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="d6e1e-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e1e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6e1e-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6e1e-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d6e1e-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e1e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6e1e-112">Requirements</span></span>  
 <span data-ttu-id="d6e1e-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6e1e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e1e-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e1e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e1e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e1e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e1e-116">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e1e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e1e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6e1e-117">See Also</span></span>  
 [<span data-ttu-id="d6e1e-118">GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="d6e1e-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)  
 [<span data-ttu-id="d6e1e-119">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6e1e-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="d6e1e-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d6e1e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
