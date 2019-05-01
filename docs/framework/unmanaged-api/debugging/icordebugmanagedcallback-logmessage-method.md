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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf83124af5ced7bb6458564430ceb319ce7d680a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995181"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="9e42b-102">ICorDebugManagedCallback::LogMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="9e42b-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="9e42b-103">Notifica al depurador que un subproceso de common language runtime (CLR) administrado ha llamado a un método el <xref:System.Diagnostics.EventLog> clase para registrar un evento.</span><span class="sxs-lookup"><span data-stu-id="9e42b-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e42b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e42b-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e42b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e42b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9e42b-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que registró el evento.</span><span class="sxs-lookup"><span data-stu-id="9e42b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="9e42b-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="9e42b-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="9e42b-108">[in] Un valor de la [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeración que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="9e42b-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="9e42b-109">[in] Un puntero al nombre del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e42b-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="9e42b-110">[in] Un puntero al mensaje que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="9e42b-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e42b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e42b-111">Requirements</span></span>  
 <span data-ttu-id="9e42b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e42b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e42b-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e42b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e42b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e42b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e42b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e42b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e42b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e42b-116">See also</span></span>

- [<span data-ttu-id="9e42b-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9e42b-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
