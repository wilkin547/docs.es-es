---
description: 'Más información acerca de: ICorDebugManagedCallback:: LogMessage (método)'
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
ms.openlocfilehash: 199f1f5dca7889a62ef351b4a2731fdb360768d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660523"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="6d57b-103">ICorDebugManagedCallback::LogMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="6d57b-103">ICorDebugManagedCallback::LogMessage Method</span></span>

<span data-ttu-id="6d57b-104">Notifica al depurador que un subproceso administrado Common Language Runtime (CLR) ha llamado a un método en la <xref:System.Diagnostics.EventLog> clase para registrar un evento.</span><span class="sxs-lookup"><span data-stu-id="6d57b-104">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d57b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d57b-105">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d57b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d57b-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="6d57b-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que registró el evento.</span><span class="sxs-lookup"><span data-stu-id="6d57b-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="6d57b-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="6d57b-108">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="6d57b-109">de Un valor de la enumeración [LoggingLevelEnum (](logginglevelenum-enumeration.md) que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="6d57b-109">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="6d57b-110">de Puntero al nombre del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6d57b-110">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="6d57b-111">de Un puntero al mensaje que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="6d57b-111">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d57b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d57b-112">Requirements</span></span>  

 <span data-ttu-id="6d57b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d57b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d57b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d57b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d57b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d57b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d57b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d57b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d57b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d57b-117">See also</span></span>

- [<span data-ttu-id="6d57b-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d57b-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
