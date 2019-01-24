---
title: ICorDebugManagedCallback::DebuggerError (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31a554fc57611f4abd5322fdc0c147e5dc110fb7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654950"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="34f01-102">ICorDebugManagedCallback::DebuggerError (Método)</span><span class="sxs-lookup"><span data-stu-id="34f01-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="34f01-103">Notifica al depurador que se ha producido un error al intentar controlar un evento de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="34f01-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34f01-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34f01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="34f01-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="34f01-106">[in] Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="34f01-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="34f01-107">[in] El valor HRESULT que se devolvió desde el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="34f01-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="34f01-108">[in] Un entero que especifica el error CLR.</span><span class="sxs-lookup"><span data-stu-id="34f01-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34f01-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34f01-109">Remarks</span></span>  
 <span data-ttu-id="34f01-110">El proceso puede colocarse en modo paso a través, según la naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="34f01-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="34f01-111">El `DebugError` devolución de llamada indica que se han deshabilitado los servicios de depuración debido a un error, por lo que los depuradores deben hacer que el mensaje de error disponible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="34f01-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="34f01-112">[ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) sea segura para la llamada, pero todos los demás métodos, incluidos [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), no debe llamarse.</span><span class="sxs-lookup"><span data-stu-id="34f01-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="34f01-113">El depurador debe usar las funciones del sistema operativo para terminar procesos.</span><span class="sxs-lookup"><span data-stu-id="34f01-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f01-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34f01-114">Requirements</span></span>  
 <span data-ttu-id="34f01-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34f01-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f01-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34f01-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34f01-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34f01-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34f01-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f01-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f01-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="34f01-119">See also</span></span>
- [<span data-ttu-id="34f01-120">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="34f01-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
