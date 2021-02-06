---
description: 'Más información acerca de: ICorDebugManagedCallback:: LogSwitch ((método)'
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
ms.openlocfilehash: 658b2afbe7074062910670c6748dc579973715f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660471"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="da5f3-103">ICorDebugManagedCallback::LogSwitch (Método)</span><span class="sxs-lookup"><span data-stu-id="da5f3-103">ICorDebugManagedCallback::LogSwitch Method</span></span>

<span data-ttu-id="da5f3-104">Notifica al depurador que un subproceso administrado Common Language Runtime (CLR) ha llamado a un método en la <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un modificador de depuración o traza.</span><span class="sxs-lookup"><span data-stu-id="da5f3-104">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da5f3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da5f3-105">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da5f3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da5f3-106">Parameters</span></span>  

 `PAppDomain`  
 <span data-ttu-id="da5f3-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que creó, modificó o eliminó un modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da5f3-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="da5f3-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="da5f3-108">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="da5f3-109">de Valor que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="da5f3-109">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="da5f3-110">de Un valor de la enumeración [logswitchcallreason (](logswitchcallreason-enumeration.md) que indica la operación realizada en el modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da5f3-110">[in] A value of the [LogSwitchCallReason](logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="da5f3-111">de Puntero al nombre del modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da5f3-111">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="da5f3-112">de Puntero al nombre del elemento primario del modificador de depuración/seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da5f3-112">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da5f3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da5f3-113">Requirements</span></span>  

 <span data-ttu-id="da5f3-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da5f3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da5f3-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da5f3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da5f3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da5f3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da5f3-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da5f3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da5f3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="da5f3-118">See also</span></span>

- [<span data-ttu-id="da5f3-119">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="da5f3-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
