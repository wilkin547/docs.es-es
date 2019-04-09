---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols (método)
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99f76bd19ef274c3d4207fdd071914b736314a3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148582"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="66633-102">ICorDebugSymbolProvider::GetMethodLocalSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="66633-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="66633-103">Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="66633-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66633-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66633-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66633-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66633-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="66633-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="66633-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="66633-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="66633-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="66633-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="66633-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="66633-109">[out] Un puntero a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matriz que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="66633-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66633-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66633-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66633-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="66633-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66633-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66633-112">Requirements</span></span>  
 <span data-ttu-id="66633-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66633-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66633-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66633-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66633-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66633-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="66633-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="66633-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="66633-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="66633-117">See also</span></span>

- [<span data-ttu-id="66633-118">Método GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="66633-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="66633-119">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="66633-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="66633-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="66633-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
