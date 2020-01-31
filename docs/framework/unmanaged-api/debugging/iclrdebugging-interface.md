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
ms.openlocfilehash: 9a768535c3bf69b5127777de4cee27054943091d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793640"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="7c450-102">ICLRDebugging (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c450-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="7c450-103">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="7c450-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c450-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7c450-104">Methods</span></span>  
  
|<span data-ttu-id="7c450-105">Método</span><span class="sxs-lookup"><span data-stu-id="7c450-105">Method</span></span>|<span data-ttu-id="7c450-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c450-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c450-107">OpenVirtualProcess (método)</span><span class="sxs-lookup"><span data-stu-id="7c450-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="7c450-108">Obtiene la interfaz "ICorDebugProcess" que corresponde a un módulo de Common Language Runtime (CLR) cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7c450-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="7c450-109">CanUnloadNow (método)</span><span class="sxs-lookup"><span data-stu-id="7c450-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="7c450-110">Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="7c450-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c450-111">Notas</span><span class="sxs-lookup"><span data-stu-id="7c450-111">Remarks</span></span>  
 <span data-ttu-id="7c450-112">Puede obtener una instancia de la interfaz `ICLRDebugging` mediante la función [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="7c450-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c450-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7c450-113">Requirements</span></span>  
 <span data-ttu-id="7c450-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c450-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c450-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c450-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c450-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c450-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c450-117">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c450-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c450-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c450-118">See also</span></span>

- [<span data-ttu-id="7c450-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7c450-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7c450-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="7c450-120">Debugging</span></span>](index.md)
