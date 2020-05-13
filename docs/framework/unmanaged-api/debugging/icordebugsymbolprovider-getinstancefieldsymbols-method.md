---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 9ecc61ed6cac73a519f33e00cbfbfecc20ac2ebe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379642"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="13cae-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="13cae-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="13cae-103">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="13cae-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13cae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13cae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13cae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13cae-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="13cae-106">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="13cae-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="13cae-107">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="13cae-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="13cae-108">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="13cae-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="13cae-109">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="13cae-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="13cae-110">enuncia Puntero a una matriz [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) que contiene los símbolos de campo de instancia solicitados.</span><span class="sxs-lookup"><span data-stu-id="13cae-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13cae-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13cae-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13cae-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="13cae-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13cae-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13cae-113">Requirements</span></span>  
 <span data-ttu-id="13cae-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13cae-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13cae-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13cae-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13cae-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13cae-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13cae-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13cae-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cae-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13cae-118">See also</span></span>

- [<span data-ttu-id="13cae-119">Método GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="13cae-119">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="13cae-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="13cae-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="13cae-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="13cae-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
