---
title: ICorDebugManagedCallback::LoadModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfca06c656f3274f4c5ddb06373a0296dc5e6905
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164546"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="02d9b-102">ICorDebugManagedCallback::LoadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="02d9b-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="02d9b-103">Notifica al depurador que se ha cargado correctamente un módulo de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="02d9b-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d9b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02d9b-104">Syntax</span></span>  
  
```  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d9b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02d9b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="02d9b-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en la que se ha cargado el módulo.</span><span class="sxs-lookup"><span data-stu-id="02d9b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="02d9b-107">[in] Un puntero a un objeto ICorDebugModule que representa el módulo CLR.</span><span class="sxs-lookup"><span data-stu-id="02d9b-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d9b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02d9b-108">Remarks</span></span>  
 <span data-ttu-id="02d9b-109">El `LoadModule` devolución de llamada proporciona un tiempo adecuado para examinar los metadatos para el módulo, establecer marcas de compilador de just-in-time (JIT), o habilitar o deshabilitar las devoluciones de llamada para el módulo de carga de clases.</span><span class="sxs-lookup"><span data-stu-id="02d9b-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d9b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02d9b-110">Requirements</span></span>  
 <span data-ttu-id="02d9b-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d9b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d9b-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02d9b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02d9b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d9b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d9b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d9b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d9b-115">See also</span></span>

- [<span data-ttu-id="02d9b-116">UnloadModule (método)</span><span class="sxs-lookup"><span data-stu-id="02d9b-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="02d9b-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02d9b-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
