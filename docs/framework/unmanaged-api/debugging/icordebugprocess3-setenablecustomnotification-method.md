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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58e50a0c02f15590e5bbbcadaabeaa7e3886b74b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736817"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="16906-102">ICorDebugProcess3::SetEnableCustomNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="16906-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="16906-103">Habilita y deshabilita las notificaciones del depurador personalizados del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="16906-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16906-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16906-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16906-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16906-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="16906-106">[in] El tipo que especifica las notificaciones del depurador personalizados.</span><span class="sxs-lookup"><span data-stu-id="16906-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="16906-107">[in] `true` para habilitar las notificaciones del depurador personalizados; `false` para deshabilitar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="16906-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="16906-108">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="16906-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16906-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16906-109">Remarks</span></span>  
 <span data-ttu-id="16906-110">Cuando `fEnable` está establecido en `true`, las llamadas a la <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> desencadenador método un [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="16906-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="16906-111">Las notificaciones están deshabilitadas de forma predeterminada; por lo tanto, el depurador debe especificar cualquier tipo de notificación que conozca y desea controlar.</span><span class="sxs-lookup"><span data-stu-id="16906-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="16906-112">Dado que el [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) ámbito de clase por dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="16906-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="16906-113">A partir de .NET Framework 4, la única notificación compatible es una notificación de dependencia entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="16906-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16906-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16906-114">Requirements</span></span>  
 <span data-ttu-id="16906-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16906-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16906-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16906-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16906-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16906-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16906-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16906-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16906-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="16906-119">See also</span></span>

- [<span data-ttu-id="16906-120">ICorDebugProcess3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16906-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [<span data-ttu-id="16906-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="16906-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="16906-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="16906-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
