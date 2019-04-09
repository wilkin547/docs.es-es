---
title: Getinstancefieldsymbols (método)
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ea9afdd2c032e99d7feee6b2935161c70c56787
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187699"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="5c7ce-102">Getinstancefieldsymbols (método)</span><span class="sxs-lookup"><span data-stu-id="5c7ce-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="5c7ce-103">Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="5c7ce-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c7ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c7ce-104">Syntax</span></span>  
  
```  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c7ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c7ce-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="5c7ce-106">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="5c7ce-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="5c7ce-107">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="5c7ce-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="5c7ce-108">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="5c7ce-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="5c7ce-109">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="5c7ce-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="5c7ce-110">[out] Un puntero a un [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) matriz que contiene los símbolos de campo de instancia solicitada.</span><span class="sxs-lookup"><span data-stu-id="5c7ce-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c7ce-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c7ce-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c7ce-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5c7ce-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c7ce-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c7ce-113">Requirements</span></span>  
 <span data-ttu-id="5c7ce-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c7ce-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c7ce-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c7ce-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c7ce-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c7ce-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5c7ce-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c7ce-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c7ce-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c7ce-118">See also</span></span>

- [<span data-ttu-id="5c7ce-119">Método GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="5c7ce-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="5c7ce-120">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="5c7ce-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5c7ce-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5c7ce-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
