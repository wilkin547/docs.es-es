---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getstaticfieldsymbols ((método)'
title: ICorDebugSymbolProvider::GetStaticFieldSymbols (método)
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
ms.openlocfilehash: e95f77be86ef88a73ca4c833b242617a0d405e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659716"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="34d79-103">ICorDebugSymbolProvider::GetStaticFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="34d79-103">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>

<span data-ttu-id="34d79-104">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="34d79-104">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34d79-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34d79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="34d79-106">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="34d79-107">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="34d79-107">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="34d79-108">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="34d79-108">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="34d79-109">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="34d79-109">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="34d79-110">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="34d79-110">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="34d79-111">enuncia Puntero a una matriz [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) que contiene los símbolos de campo estático solicitados.</span><span class="sxs-lookup"><span data-stu-id="34d79-111">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34d79-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34d79-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34d79-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="34d79-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34d79-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34d79-114">Requirements</span></span>  

 <span data-ttu-id="34d79-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34d79-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34d79-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34d79-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34d79-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34d79-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34d79-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34d79-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d79-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="34d79-119">See also</span></span>

- [<span data-ttu-id="34d79-120">Método GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="34d79-120">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="34d79-121">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="34d79-121">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="34d79-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="34d79-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
