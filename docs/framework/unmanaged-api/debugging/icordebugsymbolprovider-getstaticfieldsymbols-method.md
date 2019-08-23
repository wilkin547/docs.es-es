---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols (método)
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bd3442adf58250a423438666ec1092bab61958b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955552"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="3d202-102">ICorDebugSymbolProvider::GetStaticFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="3d202-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="3d202-103">Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.</span><span class="sxs-lookup"><span data-stu-id="3d202-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d202-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d202-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d202-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d202-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="3d202-106">[in] Número de bytes en la matriz `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="3d202-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="3d202-107">[in] Matriz de bytes que contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="3d202-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="3d202-108">[in] Número de símbolos solicitado.</span><span class="sxs-lookup"><span data-stu-id="3d202-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3d202-109">[out] Puntero al número de símbolos recuperados por el método.</span><span class="sxs-lookup"><span data-stu-id="3d202-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="3d202-110">enuncia Puntero a una matriz [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) que contiene los símbolos de campo estático solicitados.</span><span class="sxs-lookup"><span data-stu-id="3d202-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d202-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d202-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d202-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3d202-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d202-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d202-113">Requirements</span></span>  
 <span data-ttu-id="3d202-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d202-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d202-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="3d202-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d202-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d202-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d202-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d202-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d202-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d202-118">See also</span></span>

- [<span data-ttu-id="3d202-119">GetInstanceFieldSymbols (método)</span><span class="sxs-lookup"><span data-stu-id="3d202-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="3d202-120">ICorDebugSymbolProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d202-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3d202-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3d202-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
