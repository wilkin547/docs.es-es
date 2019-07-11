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
ms.openlocfilehash: d3aa76b88d89e83c400b3f372d846c1a31add255
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761477"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="d41dd-102">ICorDebugManagedCallback::LoadAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d41dd-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="d41dd-103">Notifica al depurador que un ensamblado de common language runtime (CLR) se ha cargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d41dd-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d41dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d41dd-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d41dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d41dd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d41dd-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en la que se ha cargado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d41dd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="d41dd-107">[in] Un puntero a un objeto ICorDebugAssembly que representa el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d41dd-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d41dd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d41dd-108">Requirements</span></span>  
 <span data-ttu-id="d41dd-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d41dd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d41dd-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d41dd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d41dd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d41dd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d41dd-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d41dd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41dd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d41dd-113">See also</span></span>

- [<span data-ttu-id="d41dd-114">UnloadAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="d41dd-114">UnloadAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="d41dd-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d41dd-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
