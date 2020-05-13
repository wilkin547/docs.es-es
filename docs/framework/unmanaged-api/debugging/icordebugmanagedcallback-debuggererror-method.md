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
ms.openlocfilehash: 8f3697f8b193319ebb7b155ad79b8ec25a0a2266
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205269"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="14d3e-102">ICorDebugManagedCallback::DebuggerError (Método)</span><span class="sxs-lookup"><span data-stu-id="14d3e-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="14d3e-103">Notifica al depurador que se ha producido un error al intentar controlar un evento desde el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="14d3e-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14d3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14d3e-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14d3e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14d3e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="14d3e-106">de Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="14d3e-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="14d3e-107">de Valor HRESULT devuelto por el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="14d3e-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="14d3e-108">de Un entero que especifica el error de CLR.</span><span class="sxs-lookup"><span data-stu-id="14d3e-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14d3e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="14d3e-109">Remarks</span></span>  
 <span data-ttu-id="14d3e-110">El proceso se puede poner en modo de paso a través, dependiendo de la naturaleza del error.</span><span class="sxs-lookup"><span data-stu-id="14d3e-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="14d3e-111">La `DebugError` devolución de llamada indica que los servicios de depuración se han deshabilitado debido a un error, de modo que los depuradores deberían poner el mensaje de error a disposición del usuario.</span><span class="sxs-lookup"><span data-stu-id="14d3e-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="14d3e-112">Se puede llamar a [ICorDebugProcess:: getId](icordebugprocess-getid-method.md) con seguridad, pero no se debe llamar a todos los demás métodos, incluido [ICorDebug:: Terminate](icordebug-terminate-method.md).</span><span class="sxs-lookup"><span data-stu-id="14d3e-112">[ICorDebugProcess::GetID](icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="14d3e-113">El depurador debe usar las funciones del sistema operativo para finalizar los procesos.</span><span class="sxs-lookup"><span data-stu-id="14d3e-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14d3e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14d3e-114">Requirements</span></span>  
 <span data-ttu-id="14d3e-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14d3e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14d3e-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14d3e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14d3e-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14d3e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14d3e-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14d3e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d3e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14d3e-119">See also</span></span>

- [<span data-ttu-id="14d3e-120">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14d3e-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
