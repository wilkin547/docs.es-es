---
description: 'Más información acerca de: ICorDebugManagedCallback:: UnloadModule ((método)'
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
ms.openlocfilehash: d8d37b28d7a7d11000c259f1bcde3138634b2498
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754061"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="3e1ee-103">ICorDebugManagedCallback::UnloadModule (Método)</span><span class="sxs-lookup"><span data-stu-id="3e1ee-103">ICorDebugManagedCallback::UnloadModule Method</span></span>

<span data-ttu-id="3e1ee-104">Notifica al depurador que se ha descargado un módulo de Common Language Runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="3e1ee-104">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e1ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e1ee-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e1ee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e1ee-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="3e1ee-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.</span><span class="sxs-lookup"><span data-stu-id="3e1ee-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="3e1ee-108">de Un puntero a un objeto ICorDebugModule que representa el módulo.</span><span class="sxs-lookup"><span data-stu-id="3e1ee-108">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e1ee-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3e1ee-109">Remarks</span></span>  

 <span data-ttu-id="3e1ee-110">El módulo no debe usarse después de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="3e1ee-110">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e1ee-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e1ee-111">Requirements</span></span>  

 <span data-ttu-id="3e1ee-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e1ee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e1ee-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e1ee-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e1ee-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e1ee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e1ee-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e1ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e1ee-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e1ee-116">See also</span></span>

- [<span data-ttu-id="3e1ee-117">Método LoadModule</span><span class="sxs-lookup"><span data-stu-id="3e1ee-117">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="3e1ee-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e1ee-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
