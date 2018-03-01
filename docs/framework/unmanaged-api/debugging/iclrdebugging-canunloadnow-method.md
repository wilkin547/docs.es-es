---
title: "ICLRDebugging::CanUnloadNow (Método)"
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
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b781db409991b07463002008a834dfb7ac32c9e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="74622-102">ICLRDebugging::CanUnloadNow (Método)</span><span class="sxs-lookup"><span data-stu-id="74622-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="74622-103">Determina si una biblioteca que ha proporcionado un [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaz aún está en uso o se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="74622-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74622-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74622-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74622-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74622-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="74622-106">[in] La dirección base de un módulo en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="74622-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74622-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74622-107">Return Value</span></span>  
 <span data-ttu-id="74622-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="74622-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="74622-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74622-109">HRESULT</span></span>|<span data-ttu-id="74622-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="74622-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74622-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74622-111">S_OK</span></span>|<span data-ttu-id="74622-112">El módulo al que hace referencia `hmodule` se puede descargar.</span><span class="sxs-lookup"><span data-stu-id="74622-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="74622-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="74622-113">S_FALSE</span></span>|<span data-ttu-id="74622-114">El módulo al que hace referencia `hmodule` aún está en uso.</span><span class="sxs-lookup"><span data-stu-id="74622-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="74622-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="74622-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="74622-116">El módulo indicado no es un módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="74622-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="74622-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="74622-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74622-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74622-118">Remarks</span></span>  
 <span data-ttu-id="74622-119">Este método comprueba si todas las instancias de `ICorDebug*` interfaces publicadas y ningún subproceso se encuentra dentro de una llamada a la [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="74622-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74622-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74622-120">Requirements</span></span>  
 <span data-ttu-id="74622-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74622-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74622-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74622-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74622-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74622-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74622-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74622-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74622-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="74622-125">See Also</span></span>  
 [<span data-ttu-id="74622-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="74622-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="74622-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="74622-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
