---
title: "ICorDebugProcess3::SetEnableCustomNotification (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess3.SetEnableCustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ccd1f4b6be56202d5efea1d2e38dce554835218
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="6fe7f-102">ICorDebugProcess3::SetEnableCustomNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="6fe7f-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="6fe7f-103">Habilita y deshabilita notificaciones del depurador personalizadas del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fe7f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fe7f-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6fe7f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fe7f-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="6fe7f-106">[in] El tipo que especifica las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="6fe7f-107">[in] `true` para habilitar las notificaciones del depurador personalizadas; `false` para deshabilitar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="6fe7f-108">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fe7f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6fe7f-109">Remarks</span></span>  
 <span data-ttu-id="6fe7f-110">Cuando `fEnable` está establecido en `true`, llama a la <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> desencadenador método un [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="6fe7f-111">Las notificaciones están deshabilitadas de forma predeterminada; por lo tanto, el depurador debe especificar cualquier tipo de notificación que conozca y desea controlar.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="6fe7f-112">Dado que la [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) clase tiene un ámbito de dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="6fe7f-113">A partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], el solo notificación compatible es una notificación de dependencia entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="6fe7f-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fe7f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fe7f-114">Requirements</span></span>  
 <span data-ttu-id="6fe7f-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fe7f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fe7f-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fe7f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fe7f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fe7f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fe7f-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fe7f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe7f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fe7f-119">See Also</span></span>  
 [<span data-ttu-id="6fe7f-120">ICorDebugProcess3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fe7f-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [<span data-ttu-id="6fe7f-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6fe7f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6fe7f-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="6fe7f-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
