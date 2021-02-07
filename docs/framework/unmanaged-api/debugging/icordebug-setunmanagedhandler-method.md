---
description: 'Más información acerca de: ICorDebug:: SetUnmanagedHandler ((método)'
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
ms.openlocfilehash: ffd4eb7ff0056a2468ec53eb3534434c2c8d556a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754334"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="5f196-103">ICorDebug::SetUnmanagedHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="5f196-103">ICorDebug::SetUnmanagedHandler Method</span></span>

<span data-ttu-id="5f196-104">Especifica el objeto de controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="5f196-104">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f196-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f196-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f196-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f196-106">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="5f196-107">de Un puntero a un objeto [ICorDebugUnmanagedCallback (](icordebugunmanagedcallback-interface.md) que representa el controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="5f196-107">[in] A pointer to an [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f196-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5f196-108">Remarks</span></span>  

 <span data-ttu-id="5f196-109">El objeto de controlador de eventos para eventos no administrados debe establecerse después de una llamada a [ICorDebug:: Initialize](icordebug-initialize-method.md) y antes de cualquier llamada a [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="5f196-109">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="5f196-110">Sin embargo, para los fines heredados, no es necesario establecer el objeto de controlador de eventos para los eventos no administrados hasta que se genere el primer evento de depuración nativo.</span><span class="sxs-lookup"><span data-stu-id="5f196-110">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="5f196-111">En concreto, si `ICorDebug::CreateProcess` ha establecido la marca CREATE_SUSPENDED, los eventos de depuración nativos no se pueden enviar hasta que se reanude el subproceso principal.</span><span class="sxs-lookup"><span data-stu-id="5f196-111">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f196-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f196-112">Requirements</span></span>  

 <span data-ttu-id="5f196-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f196-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f196-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f196-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f196-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f196-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f196-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f196-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f196-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f196-117">See also</span></span>

- [<span data-ttu-id="5f196-118">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f196-118">ICorDebug Interface</span></span>](icordebug-interface.md)
