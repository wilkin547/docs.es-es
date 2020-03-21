---
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 500d36b414be686071990a6e1b40dd8759d02ae9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178936"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="33bfc-102">Método ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="33bfc-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="33bfc-103">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="33bfc-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33bfc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33bfc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33bfc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33bfc-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="33bfc-106">[en] Un [valor CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa la dirección base de un módulo.</span><span class="sxs-lookup"><span data-stu-id="33bfc-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="33bfc-107">[fuera] Un puntero a la dirección de un [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="33bfc-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33bfc-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33bfc-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33bfc-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="33bfc-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33bfc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33bfc-110">Requirements</span></span>  
 <span data-ttu-id="33bfc-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33bfc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33bfc-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33bfc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33bfc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33bfc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33bfc-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33bfc-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bfc-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33bfc-115">See also</span></span>

- [<span data-ttu-id="33bfc-116">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33bfc-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="33bfc-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="33bfc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
