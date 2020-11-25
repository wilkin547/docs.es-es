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
ms.openlocfilehash: f24d49189ee81a80397b94ee4113c9514c083dbc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723992"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="dff26-102">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="dff26-102">ICorDebugManagedCallback::UnloadModule Method</span></span>

<span data-ttu-id="dff26-103">Notifica al depurador que se ha descargado un módulo de Common Language Runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="dff26-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dff26-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dff26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dff26-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="dff26-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.</span><span class="sxs-lookup"><span data-stu-id="dff26-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="dff26-107">de Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="dff26-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dff26-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dff26-108">Remarks</span></span>  

 <span data-ttu-id="dff26-109">El módulo no debe usarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="dff26-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff26-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dff26-110">Requirements</span></span>  

 <span data-ttu-id="dff26-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dff26-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff26-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dff26-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dff26-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dff26-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dff26-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff26-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff26-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dff26-115">See also</span></span>

- [<span data-ttu-id="dff26-116">Método LoadModule</span><span class="sxs-lookup"><span data-stu-id="dff26-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="dff26-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dff26-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
