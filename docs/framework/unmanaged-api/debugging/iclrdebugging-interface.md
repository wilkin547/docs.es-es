---
title: ICLRDebugging (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6edee34c8560c989040475fee4a35c6bd2ddb3e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155719"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="97c60-102">ICLRDebugging (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="97c60-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="97c60-103">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="97c60-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97c60-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="97c60-104">Methods</span></span>  
  
|<span data-ttu-id="97c60-105">Método</span><span class="sxs-lookup"><span data-stu-id="97c60-105">Method</span></span>|<span data-ttu-id="97c60-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="97c60-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97c60-107">Método OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="97c60-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="97c60-108">Obtiene la interfaz "ICorDebugProcess" que corresponde a un módulo de runtime (CLR) de lenguaje común cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="97c60-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="97c60-109">Método CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="97c60-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="97c60-110">Determina si una biblioteca que se proporcionó mediante un [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaz todavía está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="97c60-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97c60-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97c60-111">Remarks</span></span>  
 <span data-ttu-id="97c60-112">Puede obtener una instancia de la `ICLRDebugging` interfaz mediante el uso de la [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="97c60-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97c60-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97c60-113">Requirements</span></span>  
 <span data-ttu-id="97c60-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97c60-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97c60-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97c60-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97c60-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97c60-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="97c60-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="97c60-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97c60-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="97c60-118">See also</span></span>

- [<span data-ttu-id="97c60-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="97c60-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="97c60-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="97c60-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
