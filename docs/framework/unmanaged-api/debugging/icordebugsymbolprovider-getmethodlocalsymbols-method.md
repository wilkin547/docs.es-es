---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols (método)
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99f76bd19ef274c3d4207fdd071914b736314a3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953340"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="b45fe-102">ICorDebugSymbolProvider::GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="b45fe-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="b45fe-103">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="b45fe-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b45fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b45fe-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b45fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b45fe-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="b45fe-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="b45fe-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="b45fe-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="b45fe-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="b45fe-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="b45fe-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="b45fe-109">[out] Un puntero a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matriz que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="b45fe-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b45fe-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b45fe-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b45fe-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b45fe-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b45fe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b45fe-112">Requirements</span></span>  
 <span data-ttu-id="b45fe-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b45fe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b45fe-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b45fe-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b45fe-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b45fe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b45fe-116">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b45fe-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b45fe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b45fe-117">See also</span></span>

- [<span data-ttu-id="b45fe-118">GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="b45fe-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="b45fe-119">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b45fe-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b45fe-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b45fe-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
