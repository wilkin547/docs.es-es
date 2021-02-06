---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getinstancefieldsymbols ((método)'
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 379d943743bb1fe21edbcca2265b4d8613d4f4b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659899"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="04d25-103">ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="04d25-103">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>

<span data-ttu-id="04d25-104">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="04d25-104">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d25-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04d25-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04d25-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04d25-106">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="04d25-107">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="04d25-107">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="04d25-108">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="04d25-108">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="04d25-109">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="04d25-109">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="04d25-110">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="04d25-110">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="04d25-111">enuncia Puntero a una matriz [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) que contiene los símbolos de campo de instancia solicitados.</span><span class="sxs-lookup"><span data-stu-id="04d25-111">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04d25-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04d25-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04d25-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="04d25-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04d25-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04d25-114">Requirements</span></span>  

 <span data-ttu-id="04d25-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04d25-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d25-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04d25-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04d25-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04d25-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04d25-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04d25-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d25-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="04d25-119">See also</span></span>

- [<span data-ttu-id="04d25-120">Método GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="04d25-120">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="04d25-121">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="04d25-121">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="04d25-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="04d25-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
