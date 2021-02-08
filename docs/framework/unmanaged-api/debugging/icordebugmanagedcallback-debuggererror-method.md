---
description: 'Más información acerca de: ICorDebugManagedCallback::D método ebuggerError'
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
ms.openlocfilehash: 2f73e07711f7d2ce865aab8f90862563e767fd16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791012"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="22a8b-103">ICorDebugManagedCallback::DebuggerError (Método)</span><span class="sxs-lookup"><span data-stu-id="22a8b-103">ICorDebugManagedCallback::DebuggerError Method</span></span>

<span data-ttu-id="22a8b-104">Notifica al depurador que se ha producido un error al intentar controlar un evento desde el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="22a8b-104">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a8b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22a8b-105">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22a8b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22a8b-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="22a8b-107">de Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="22a8b-107">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="22a8b-108">de Valor HRESULT devuelto por el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="22a8b-108">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="22a8b-109">de Un entero que especifica el error de CLR.</span><span class="sxs-lookup"><span data-stu-id="22a8b-109">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22a8b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22a8b-110">Remarks</span></span>  

 <span data-ttu-id="22a8b-111">El proceso se puede poner en modo de paso a través, dependiendo de la naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="22a8b-111">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="22a8b-112">La `DebugError` devolución de llamada indica que los servicios de depuración se han deshabilitado debido a un error, de modo que los depuradores deberían poner el mensaje de error a disposición del usuario.</span><span class="sxs-lookup"><span data-stu-id="22a8b-112">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="22a8b-113">Se puede llamar a [ICorDebugProcess:: getId](icordebugprocess-getid-method.md) con seguridad, pero no se debe llamar a todos los demás métodos, incluido [ICorDebug:: Terminate](icordebug-terminate-method.md).</span><span class="sxs-lookup"><span data-stu-id="22a8b-113">[ICorDebugProcess::GetID](icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="22a8b-114">El depurador debe usar las funciones del sistema operativo para finalizar los procesos.</span><span class="sxs-lookup"><span data-stu-id="22a8b-114">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22a8b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22a8b-115">Requirements</span></span>  

 <span data-ttu-id="22a8b-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22a8b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22a8b-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22a8b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22a8b-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22a8b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22a8b-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22a8b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a8b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="22a8b-120">See also</span></span>

- [<span data-ttu-id="22a8b-121">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="22a8b-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
