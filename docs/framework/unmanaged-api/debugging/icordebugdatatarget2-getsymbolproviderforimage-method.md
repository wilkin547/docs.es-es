---
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cdd2d0b6f6fbc8d3c2b1a14ca05a84d13c56331
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411108"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="d9052-102">Método ICorDebugDataTarget2::GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="d9052-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="d9052-103">Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.</span><span class="sxs-lookup"><span data-stu-id="d9052-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9052-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9052-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9052-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9052-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="d9052-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base de un módulo.</span><span class="sxs-lookup"><span data-stu-id="d9052-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="d9052-107">[out] Un puntero a la dirección de un [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="d9052-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9052-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9052-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9052-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d9052-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9052-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9052-110">Requirements</span></span>  
 <span data-ttu-id="d9052-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9052-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9052-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9052-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9052-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9052-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9052-114">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9052-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9052-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9052-115">See Also</span></span>  
 [<span data-ttu-id="d9052-116">ICorDebugDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9052-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="d9052-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d9052-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
