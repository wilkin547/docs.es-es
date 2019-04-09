---
title: ICorDebugManagedCallback::LogSwitch (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a011485453999b9d764716356eebb2a5462f7bb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078842"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="b809a-102">ICorDebugManagedCallback::LogSwitch (Método)</span><span class="sxs-lookup"><span data-stu-id="b809a-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="b809a-103">Notifica al depurador que un subproceso de common language runtime (CLR) administrado ha llamado a un método el <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b809a-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b809a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b809a-104">Syntax</span></span>  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b809a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b809a-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="b809a-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que crea, modifica o elimina un conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b809a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b809a-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="b809a-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="b809a-108">[in] Un valor que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="b809a-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="b809a-109">[in] Un valor de la [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeración que indica la operación se realiza en el conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b809a-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="b809a-110">[in] Un puntero al nombre del conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b809a-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="b809a-111">[in] Un puntero al nombre del elemento primario del conmutador de depuración y seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b809a-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b809a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b809a-112">Requirements</span></span>  
 <span data-ttu-id="b809a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b809a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b809a-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b809a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b809a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b809a-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b809a-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b809a-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b809a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b809a-117">See also</span></span>

- [<span data-ttu-id="b809a-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b809a-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
