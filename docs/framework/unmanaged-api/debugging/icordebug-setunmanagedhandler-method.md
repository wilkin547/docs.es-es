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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c234b3953130f53d7e6b583cd92670149a70689b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168875"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="6d6ff-102">ICorDebug::SetUnmanagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="6d6ff-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="6d6ff-103">Especifica el objeto de controlador de eventos para eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="6d6ff-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d6ff-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d6ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d6ff-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="6d6ff-106">[in] Un puntero a un [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) objeto que representa el controlador de eventos para eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="6d6ff-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d6ff-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d6ff-107">Remarks</span></span>  
 <span data-ttu-id="6d6ff-108">El controlador de eventos de objeto para no administrada de eventos deben establecerse después de llamar a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) y antes de llamar a [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) o [DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d6ff-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="6d6ff-109">Sin embargo, para fines de herencia, no debe establecer el objeto de controlador de eventos para los eventos no administrados hasta que se produce el primer evento de depuración nativo.</span><span class="sxs-lookup"><span data-stu-id="6d6ff-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="6d6ff-110">En concreto, si `ICorDebug::CreateProcess` ha establecido la marca CREATE_SUSPENDED, no se pueden enviar los eventos hasta que se reanude el subproceso principal de depuración nativo.</span><span class="sxs-lookup"><span data-stu-id="6d6ff-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6ff-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d6ff-111">Requirements</span></span>  
 <span data-ttu-id="6d6ff-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6ff-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d6ff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d6ff-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d6ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d6ff-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6ff-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d6ff-116">See also</span></span>

- [<span data-ttu-id="6d6ff-117">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d6ff-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
