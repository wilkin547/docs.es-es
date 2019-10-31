---
title: ICorDebug::SetUnmanagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: 36d314211d95dff6648753f5d550a2cfd402a918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134046"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="8866e-102">ICorDebug::SetUnmanagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="8866e-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="8866e-103">Especifica el objeto de controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="8866e-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8866e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8866e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8866e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8866e-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="8866e-106">de Un puntero a un objeto [ICorDebugUnmanagedCallback (](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) que representa el controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="8866e-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8866e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8866e-107">Remarks</span></span>  
 <span data-ttu-id="8866e-108">El objeto de controlador de eventos para eventos no administrados debe establecerse después de una llamada a [ICorDebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) y antes de cualquier llamada a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="8866e-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="8866e-109">Sin embargo, para los fines heredados, no es necesario establecer el objeto de controlador de eventos para los eventos no administrados hasta que se genere el primer evento de depuración nativo.</span><span class="sxs-lookup"><span data-stu-id="8866e-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="8866e-110">En concreto, si `ICorDebug::CreateProcess` ha establecido la marca CREATE_SUSPENDED, los eventos de depuración nativos no se pueden enviar hasta que se reanude el subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="8866e-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8866e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8866e-111">Requirements</span></span>  
 <span data-ttu-id="8866e-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8866e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8866e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8866e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8866e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8866e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8866e-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8866e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8866e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8866e-116">See also</span></span>

- [<span data-ttu-id="8866e-117">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8866e-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
