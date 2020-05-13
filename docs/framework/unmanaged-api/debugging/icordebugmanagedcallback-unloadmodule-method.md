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
ms.openlocfilehash: 4b44a16d143c1daea1ea6c36eb096ab9a937b272
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210051"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="55e6e-102">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="55e6e-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="55e6e-103">Notifica al depurador que se ha descargado un módulo de Common Language Runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="55e6e-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e6e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55e6e-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e6e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55e6e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="55e6e-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.</span><span class="sxs-lookup"><span data-stu-id="55e6e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="55e6e-107">de Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="55e6e-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55e6e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55e6e-108">Remarks</span></span>  
 <span data-ttu-id="55e6e-109">El módulo no debe usarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="55e6e-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e6e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55e6e-110">Requirements</span></span>  
 <span data-ttu-id="55e6e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55e6e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e6e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55e6e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55e6e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55e6e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55e6e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e6e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e6e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55e6e-115">See also</span></span>

- [<span data-ttu-id="55e6e-116">Método LoadModule</span><span class="sxs-lookup"><span data-stu-id="55e6e-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="55e6e-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55e6e-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
