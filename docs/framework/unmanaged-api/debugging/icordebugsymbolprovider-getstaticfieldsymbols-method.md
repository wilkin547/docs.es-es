---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols (método)
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
ms.openlocfilehash: 2428521b9b08060fd147a7c9b9054239bf957f69
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379375"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="5412d-102">ICorDebugSymbolProvider::GetStaticFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="5412d-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="5412d-103">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="5412d-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5412d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5412d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5412d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5412d-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="5412d-106">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="5412d-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="5412d-107">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="5412d-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="5412d-108">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="5412d-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="5412d-109">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="5412d-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="5412d-110">enuncia Puntero a una matriz [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) que contiene los símbolos de campo estático solicitados.</span><span class="sxs-lookup"><span data-stu-id="5412d-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5412d-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5412d-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5412d-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5412d-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5412d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5412d-113">Requirements</span></span>  
 <span data-ttu-id="5412d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5412d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5412d-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5412d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5412d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5412d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5412d-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5412d-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5412d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5412d-118">See also</span></span>

- [<span data-ttu-id="5412d-119">Método GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="5412d-119">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="5412d-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="5412d-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5412d-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5412d-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
