---
title: "ICorDebugProcess5::EnableNGENPolicy (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5::EnableNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dca0df7b0be643d53bb5b9a03bd3abbb186d69dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="c99ff-102">ICorDebugProcess5::EnableNGENPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="c99ff-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="c99ff-103">Establece un valor que determina la forma en que una aplicación carga imágenes nativas mientras se ejecuta bajo un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="c99ff-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c99ff-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c99ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c99ff-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="c99ff-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constante que determina la forma en que una aplicación carga imágenes nativas mientras se ejecuta bajo un depurador administrado.</span><span class="sxs-lookup"><span data-stu-id="c99ff-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c99ff-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c99ff-107">Remarks</span></span>  
 <span data-ttu-id="c99ff-108">Si la directiva está configurada correctamente, el método devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="c99ff-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="c99ff-109">Si `ePolicy` está fuera del intervalo de los valores enumerados definidos por [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="c99ff-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="c99ff-110">Si no se puede actualizar la directiva de Native Image Generator (Ngen.exe), el método devuelve `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="c99ff-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="c99ff-111">El `ICorDebugProcess5::EnableNGenPolicy` método puede llamarse en cualquier momento durante la duración del proceso.</span><span class="sxs-lookup"><span data-stu-id="c99ff-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="c99ff-112">La directiva está en vigor para los módulos que se cargan después de establece la directiva.</span><span class="sxs-lookup"><span data-stu-id="c99ff-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c99ff-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c99ff-113">Requirements</span></span>  
 <span data-ttu-id="c99ff-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c99ff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c99ff-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c99ff-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c99ff-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c99ff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c99ff-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c99ff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99ff-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c99ff-118">See Also</span></span>  
 [<span data-ttu-id="c99ff-119">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c99ff-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="c99ff-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c99ff-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c99ff-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="c99ff-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
