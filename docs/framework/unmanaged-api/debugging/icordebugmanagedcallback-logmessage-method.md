---
title: ICorDebugManagedCallback::LogMessage (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 4306c4ae44b0ae1ade2bf374981492fa1a4df76f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788366"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="1b6c5-102">ICorDebugManagedCallback::LogMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="1b6c5-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="1b6c5-103">Notifica al depurador que un subproceso administrado Common Language Runtime (CLR) ha llamado a un método en la clase <xref:System.Diagnostics.EventLog> para registrar un evento.</span><span class="sxs-lookup"><span data-stu-id="1b6c5-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b6c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b6c5-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b6c5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1b6c5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1b6c5-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que registró el evento.</span><span class="sxs-lookup"><span data-stu-id="1b6c5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="1b6c5-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="1b6c5-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="1b6c5-108">de Un valor de la enumeración [LoggingLevelEnum (](logginglevelenum-enumeration.md) que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="1b6c5-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="1b6c5-109">de Puntero al nombre del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1b6c5-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="1b6c5-110">de Un puntero al mensaje que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="1b6c5-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b6c5-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1b6c5-111">Requirements</span></span>  
 <span data-ttu-id="1b6c5-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b6c5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b6c5-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b6c5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b6c5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b6c5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b6c5-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b6c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6c5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b6c5-116">See also</span></span>

- [<span data-ttu-id="1b6c5-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b6c5-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
