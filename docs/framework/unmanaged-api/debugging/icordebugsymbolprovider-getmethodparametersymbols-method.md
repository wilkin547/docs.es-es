---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols (método)
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 051002b547aaa9745ae4efb516211123089c3128
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379596"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="7643e-102">ICorDebugSymbolProvider::GetMethodParameterSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="7643e-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="7643e-103">Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.</span><span class="sxs-lookup"><span data-stu-id="7643e-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7643e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7643e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7643e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7643e-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="7643e-106">[in] Dirección virtual relativa nativa del método.</span><span class="sxs-lookup"><span data-stu-id="7643e-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="7643e-107">[in] Número de símbolos locales solicitado.</span><span class="sxs-lookup"><span data-stu-id="7643e-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="7643e-108">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="7643e-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="7643e-109">enuncia Puntero a una matriz [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) que contiene los símbolos locales del método.</span><span class="sxs-lookup"><span data-stu-id="7643e-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7643e-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7643e-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7643e-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7643e-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7643e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7643e-112">Requirements</span></span>  
 <span data-ttu-id="7643e-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7643e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7643e-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7643e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7643e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7643e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7643e-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7643e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7643e-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7643e-117">See also</span></span>

- [<span data-ttu-id="7643e-118">Método GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="7643e-118">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="7643e-119">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="7643e-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="7643e-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7643e-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
