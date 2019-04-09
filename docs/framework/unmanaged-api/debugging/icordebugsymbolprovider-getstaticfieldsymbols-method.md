---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols (método)
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18bfab7a666a4c715b2236f5101bcceacb5b2fed
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072693"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="c3593-102">ICorDebugSymbolProvider::GetStaticFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="c3593-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="c3593-103">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="c3593-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3593-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3593-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3593-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3593-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="c3593-106">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="c3593-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="c3593-107">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="c3593-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="c3593-108">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="c3593-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="c3593-109">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="c3593-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="c3593-110">[out] Un puntero a un [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) matriz que contiene los símbolos de campo estáticos solicitados.</span><span class="sxs-lookup"><span data-stu-id="c3593-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3593-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3593-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3593-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c3593-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3593-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3593-113">Requirements</span></span>  
 <span data-ttu-id="c3593-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3593-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3593-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3593-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3593-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3593-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c3593-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c3593-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3593-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3593-118">See also</span></span>

- [<span data-ttu-id="c3593-119">Método GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="c3593-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="c3593-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="c3593-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="c3593-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c3593-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
