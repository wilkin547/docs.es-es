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
ms.openlocfilehash: 6eea7f6c222b8e30376ec72ee0c193a68c23f0d0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723563"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="a7508-102">ICLRDebugging (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7508-102">ICLRDebugging Interface</span></span>

<span data-ttu-id="a7508-103">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="a7508-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7508-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a7508-104">Methods</span></span>  
  
|<span data-ttu-id="a7508-105">Método</span><span class="sxs-lookup"><span data-stu-id="a7508-105">Method</span></span>|<span data-ttu-id="a7508-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7508-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7508-107">Método OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="a7508-107">OpenVirtualProcess Method</span></span>](iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="a7508-108">Obtiene la interfaz "ICorDebugProcess" que corresponde a un módulo de Common Language Runtime (CLR) cargado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a7508-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="a7508-109">Método CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="a7508-109">CanUnloadNow Method</span></span>](iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="a7508-110">Determina si una biblioteca proporcionada por una interfaz [ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md) todavía está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="a7508-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7508-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7508-111">Remarks</span></span>  

 <span data-ttu-id="a7508-112">Puede obtener una instancia de la `ICLRDebugging` interfaz mediante la función [CLRCreateInstance](../hosting/clrcreateinstance-function.md) .</span><span class="sxs-lookup"><span data-stu-id="a7508-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7508-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7508-113">Requirements</span></span>  

 <span data-ttu-id="a7508-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7508-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7508-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7508-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7508-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7508-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7508-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7508-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7508-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7508-118">See also</span></span>

- [<span data-ttu-id="a7508-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a7508-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a7508-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="a7508-120">Debugging</span></span>](index.md)
