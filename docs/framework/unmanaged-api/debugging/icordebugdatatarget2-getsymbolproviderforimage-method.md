---
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e148adf3f9b00715d86d2e6f4a40430f099c935d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469266"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="c1c61-102">Método ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="c1c61-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="c1c61-103">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="c1c61-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1c61-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1c61-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1c61-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="c1c61-106">[in] Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base de un módulo.</span><span class="sxs-lookup"><span data-stu-id="c1c61-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="c1c61-107">[out] Un puntero a la dirección de un [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="c1c61-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1c61-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1c61-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1c61-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c1c61-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c61-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1c61-110">Requirements</span></span>  
 <span data-ttu-id="c1c61-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c61-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c61-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1c61-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1c61-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1c61-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1c61-114">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c61-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c61-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1c61-115">See also</span></span>
- [<span data-ttu-id="c1c61-116">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1c61-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="c1c61-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c1c61-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
