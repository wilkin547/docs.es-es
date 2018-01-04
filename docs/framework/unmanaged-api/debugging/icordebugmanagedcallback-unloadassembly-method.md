---
title: "ICorDebugManagedCallback::UnloadAssembly (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 731615729f680bae4c4b8517de4a3e522d4acae2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="b9628-102">ICorDebugManagedCallback::UnloadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="b9628-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="b9628-103">Notifica al depurador que se ha descargado un ensamblado de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="b9628-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9628-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9628-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9628-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9628-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b9628-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9628-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="b9628-107">[in] Un puntero a un objeto ICorDebugAssembly que representa el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9628-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9628-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9628-108">Remarks</span></span>  
 <span data-ttu-id="b9628-109">El ensamblado no debe utilizarse después de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b9628-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9628-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9628-110">Requirements</span></span>  
 <span data-ttu-id="b9628-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9628-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9628-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9628-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9628-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9628-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9628-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9628-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9628-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9628-115">See Also</span></span>  
 [<span data-ttu-id="b9628-116">LoadAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="b9628-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)  
 [<span data-ttu-id="b9628-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9628-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
