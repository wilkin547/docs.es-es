---
title: ICorDebugProcess3::SetEnableCustomNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792468"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="f5a68-102">ICorDebugProcess3::SetEnableCustomNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="f5a68-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="f5a68-103">Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f5a68-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5a68-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a68-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f5a68-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="f5a68-106">de Tipo que especifica las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="f5a68-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="f5a68-107">[in] `true` para habilitar las notificaciones personalizadas del depurador; `false` para deshabilitar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="f5a68-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="f5a68-108">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="f5a68-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5a68-109">Notas</span><span class="sxs-lookup"><span data-stu-id="f5a68-109">Remarks</span></span>  
 <span data-ttu-id="f5a68-110">Cuando `fEnable` se establece en `true`, las llamadas al método <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> desencadenan una devolución de llamada [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f5a68-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="f5a68-111">Las notificaciones están deshabilitadas de forma predeterminada; por consiguiente, el depurador debe especificar los tipos de notificación que conoce y desea controlar.</span><span class="sxs-lookup"><span data-stu-id="f5a68-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="f5a68-112">Dado que el ámbito de la clase [ICorDebugClass](icordebug-interface.md) es el dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="f5a68-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="f5a68-113">A partir de la .NET Framework 4, la única notificación admitida es una notificación de dependencia entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f5a68-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a68-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f5a68-114">Requirements</span></span>  
 <span data-ttu-id="f5a68-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a68-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a68-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5a68-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5a68-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a68-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a68-118">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a68-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a68-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5a68-119">See also</span></span>

- [<span data-ttu-id="f5a68-120">ICorDebugProcess3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a68-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="f5a68-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f5a68-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f5a68-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="f5a68-122">Debugging</span></span>](index.md)
