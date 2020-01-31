---
title: ICorDebugManagedCallback::UnloadModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: 88ef9fd5a0aac19954a247d0215fe698ebe30d40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788329"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="7ef83-102">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="7ef83-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="7ef83-103">Notifica al depurador que se ha descargado un módulo de Common Language Runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="7ef83-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ef83-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ef83-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ef83-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7ef83-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7ef83-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.</span><span class="sxs-lookup"><span data-stu-id="7ef83-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="7ef83-107">de Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="7ef83-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ef83-108">Notas</span><span class="sxs-lookup"><span data-stu-id="7ef83-108">Remarks</span></span>  
 <span data-ttu-id="7ef83-109">El módulo no debe usarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="7ef83-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef83-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7ef83-110">Requirements</span></span>  
 <span data-ttu-id="7ef83-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ef83-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef83-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ef83-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ef83-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ef83-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ef83-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ef83-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef83-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ef83-115">See also</span></span>

- [<span data-ttu-id="7ef83-116">LoadModule (método)</span><span class="sxs-lookup"><span data-stu-id="7ef83-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="7ef83-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ef83-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
