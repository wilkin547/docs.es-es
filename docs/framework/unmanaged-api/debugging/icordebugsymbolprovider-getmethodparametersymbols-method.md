---
title: "ICorDebugSymbolProvider::GetMethodParameterSymbols (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b0b55caec333bc1e69dae9eee59ba30b6671737
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="0767d-102">ICorDebugSymbolProvider::GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="0767d-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="0767d-103">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="0767d-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0767d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0767d-104">Syntax</span></span>  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0767d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0767d-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="0767d-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="0767d-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="0767d-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="0767d-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="0767d-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="0767d-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="0767d-109">[out] Un puntero a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matriz que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="0767d-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0767d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0767d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0767d-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0767d-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0767d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0767d-112">Requirements</span></span>  
 <span data-ttu-id="0767d-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0767d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0767d-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0767d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0767d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0767d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0767d-116">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0767d-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0767d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0767d-117">See Also</span></span>  
 [<span data-ttu-id="0767d-118">GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="0767d-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)  
 [<span data-ttu-id="0767d-119">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="0767d-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="0767d-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0767d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
