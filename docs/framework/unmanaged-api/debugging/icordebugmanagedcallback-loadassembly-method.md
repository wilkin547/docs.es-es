---
title: ICorDebugManagedCallback::LoadAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5760287e01257e3f0fc99a18ba20f2f2a1b2b3af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988161"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="7fd19-102">ICorDebugManagedCallback::LoadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="7fd19-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="7fd19-103">Notifica al depurador que un ensamblado de common language runtime (CLR) se ha cargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7fd19-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fd19-104">Syntax</span></span>  
  
```  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fd19-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7fd19-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7fd19-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en la que se ha cargado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7fd19-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="7fd19-107">[in] Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7fd19-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fd19-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fd19-108">Requirements</span></span>  
 <span data-ttu-id="7fd19-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fd19-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fd19-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fd19-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fd19-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fd19-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fd19-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fd19-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd19-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fd19-113">See also</span></span>

- [<span data-ttu-id="7fd19-114">UnloadAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="7fd19-114">UnloadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="7fd19-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fd19-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
