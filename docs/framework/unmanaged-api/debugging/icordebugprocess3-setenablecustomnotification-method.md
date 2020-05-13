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
ms.openlocfilehash: 523d9665ffd2637a0e856d74d4d3b3838cb5e83c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212131"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="a3455-102">ICorDebugProcess3::SetEnableCustomNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="a3455-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="a3455-103">Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="a3455-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3455-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3455-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3455-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3455-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="a3455-106">de Tipo que especifica las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a3455-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="a3455-107">[in] `true` para habilitar las notificaciones del depurador personalizadas; `false`para deshabilitar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="a3455-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="a3455-108">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a3455-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3455-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3455-109">Remarks</span></span>  
 <span data-ttu-id="a3455-110">Cuando `fEnable` se establece en `true` , las llamadas al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> método desencadenan una devolución de llamada [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a3455-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="a3455-111">Las notificaciones están deshabilitadas de forma predeterminada; por consiguiente, el depurador debe especificar los tipos de notificación que conoce y desea controlar.</span><span class="sxs-lookup"><span data-stu-id="a3455-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="a3455-112">Dado que el ámbito de la clase [ICorDebugClass](icordebug-interface.md) es el dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="a3455-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="a3455-113">A partir de la .NET Framework 4, la única notificación admitida es una notificación de dependencia entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a3455-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3455-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3455-114">Requirements</span></span>  
 <span data-ttu-id="a3455-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3455-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3455-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3455-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3455-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3455-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3455-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3455-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3455-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3455-119">See also</span></span>

- [<span data-ttu-id="a3455-120">ICorDebugProcess3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3455-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="a3455-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a3455-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a3455-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="a3455-122">Debugging</span></span>](index.md)
