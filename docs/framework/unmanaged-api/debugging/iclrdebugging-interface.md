---
description: 'Más información acerca de: interfaz ICLRDebugging'
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
ms.openlocfilehash: 647b6f7634ef3b9f6ec6080aaff19476c027952a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723342"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="a499d-103">ICLRDebugging (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a499d-103">ICLRDebugging Interface</span></span>

<span data-ttu-id="a499d-104">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="a499d-104">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a499d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a499d-105">Methods</span></span>  
  
|<span data-ttu-id="a499d-106">Método</span><span class="sxs-lookup"><span data-stu-id="a499d-106">Method</span></span>|<span data-ttu-id="a499d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a499d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a499d-108">Método OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="a499d-108">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="a499d-109">Obtiene la interfaz "ICorDebugProcess" que corresponde a un módulo de Common Language Runtime (CLR) cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a499d-109">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="a499d-110">Método CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="a499d-110">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="a499d-111">Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="a499d-111">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a499d-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a499d-112">Remarks</span></span>  

 <span data-ttu-id="a499d-113">Puede obtener una instancia de la `ICLRDebugging` interfaz mediante la función [CLRCreateInstance](../hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="a499d-113">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a499d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a499d-114">Requirements</span></span>  

 <span data-ttu-id="a499d-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a499d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a499d-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a499d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a499d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a499d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a499d-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a499d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a499d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a499d-119">See also</span></span>

- [<span data-ttu-id="a499d-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a499d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a499d-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="a499d-121">Debugging</span></span>](index.md)
