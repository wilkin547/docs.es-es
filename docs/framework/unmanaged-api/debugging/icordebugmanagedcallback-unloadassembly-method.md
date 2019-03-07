---
title: ICorDebugManagedCallback::UnloadAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef4d7993269aa606aa6b22a1544bc2d04d9e6e93
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476534"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="a2524-102">ICorDebugManagedCallback::UnloadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="a2524-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="a2524-103">Notifica al depurador que se ha descargado un ensamblado de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="a2524-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2524-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2524-104">Syntax</span></span>  
  
```  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2524-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2524-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a2524-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a2524-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="a2524-107">[in] Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a2524-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2524-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2524-108">Remarks</span></span>  
 <span data-ttu-id="a2524-109">El ensamblado no debe utilizarse después de esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a2524-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2524-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2524-110">Requirements</span></span>  
 <span data-ttu-id="a2524-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2524-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2524-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2524-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2524-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2524-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2524-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2524-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2524-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2524-115">See also</span></span>
- [<span data-ttu-id="a2524-116">LoadAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="a2524-116">LoadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="a2524-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2524-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
