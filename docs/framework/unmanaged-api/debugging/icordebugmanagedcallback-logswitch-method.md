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
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130694"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="eb340-102">ICorDebugManagedCallback::LogSwitch (Método)</span><span class="sxs-lookup"><span data-stu-id="eb340-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="eb340-103">Notifica al depurador que un subproceso administrado Common Language Runtime (CLR) ha llamado a un método en la clase <xref:System.Diagnostics.Switch> para crear, modificar o eliminar un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="eb340-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb340-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb340-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb340-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb340-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="eb340-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que creó, modificó o eliminó un modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb340-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="eb340-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="eb340-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="eb340-108">de Valor que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="eb340-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="eb340-109">de Un valor de la enumeración [logswitchcallreason (](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) que indica la operación realizada en el modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb340-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="eb340-110">de Puntero al nombre del modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb340-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="eb340-111">de Puntero al nombre del elemento primario del modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb340-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb340-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb340-112">Requirements</span></span>  
 <span data-ttu-id="eb340-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb340-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb340-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb340-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb340-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb340-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb340-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb340-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb340-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb340-117">See also</span></span>

- [<span data-ttu-id="eb340-118">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb340-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
