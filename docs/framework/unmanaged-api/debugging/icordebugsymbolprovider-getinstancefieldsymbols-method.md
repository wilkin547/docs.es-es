---
title: "ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2ddb0b9e10314d027d342b34542129fbcdfb075
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="14866-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="14866-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="14866-103">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="14866-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14866-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14866-104">Syntax</span></span>  
  
```  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14866-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14866-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="14866-106">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="14866-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="14866-107">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="14866-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="14866-108">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="14866-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="14866-109">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="14866-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="14866-110">[out] Un puntero a un [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) matriz que contiene los símbolos de campo de instancia solicitada.</span><span class="sxs-lookup"><span data-stu-id="14866-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14866-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14866-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14866-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="14866-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14866-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14866-113">Requirements</span></span>  
 <span data-ttu-id="14866-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14866-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14866-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14866-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14866-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14866-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14866-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14866-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14866-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="14866-118">See Also</span></span>  
 [<span data-ttu-id="14866-119">GetStaticFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="14866-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)  
 [<span data-ttu-id="14866-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="14866-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="14866-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="14866-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
