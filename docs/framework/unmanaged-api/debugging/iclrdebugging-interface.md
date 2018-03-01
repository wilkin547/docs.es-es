---
title: ICLRDebugging (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 325f6adf8fe3a357f903f0cb047a2255ef80e264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="be39e-102">ICLRDebugging (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="be39e-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="be39e-103">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="be39e-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be39e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="be39e-104">Methods</span></span>  
  
|<span data-ttu-id="be39e-105">Método</span><span class="sxs-lookup"><span data-stu-id="be39e-105">Method</span></span>|<span data-ttu-id="be39e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="be39e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be39e-107">OpenVirtualProcess (método)</span><span class="sxs-lookup"><span data-stu-id="be39e-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="be39e-108">Obtiene la interfaz "ICorDebugProcess" que corresponde a un módulo de runtime (CLR) de lenguaje común cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="be39e-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="be39e-109">CanUnloadNow (método)</span><span class="sxs-lookup"><span data-stu-id="be39e-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="be39e-110">Determina si una biblioteca que ha proporcionado un [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaz aún está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="be39e-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be39e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be39e-111">Remarks</span></span>  
 <span data-ttu-id="be39e-112">Puede obtener una instancia de la `ICLRDebugging` interfaz mediante el uso de la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="be39e-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be39e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be39e-113">Requirements</span></span>  
 <span data-ttu-id="be39e-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be39e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be39e-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be39e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be39e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be39e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be39e-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be39e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be39e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="be39e-118">See Also</span></span>  
 [<span data-ttu-id="be39e-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="be39e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="be39e-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="be39e-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
